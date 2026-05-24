# 在 C++ 中训练支持向量机识别面部特征

> 原文:[https://www . geesforgeks . org/train-a-support-vector-machine-to-recognition-face-features-in-c/](https://www.geeksforgeeks.org/train-a-support-vector-machine-to-recognize-facial-features-in-c/)

让我们看看如何训练一个支持向量机模型，保存训练好的模型，并使用 OpenCV 测试模型以检查其预测精度的百分比。

## 数据组织:

使用`imagenetscraper` 和`autocrop` ，我们从网上收集数据，裁剪面并批量调整它们的大小。收集的数据需要有意义地组织起来，这样我们就可以通过编程和手动方式访问它。使用下面的文件夹结构-

```cpp
FFR_dataset/
|-- Age
|   |-- adult
|   |-- child
|   |-- old
|   |-- teen
|-- Emotion
|   |-- anger
|   |-- contempt
|   |-- happy
|   |-- neutral
|   |-- sad
|   |-- surprise
|-- Gender
    |-- female
    |-- male 
```

我们在代码中使用相同的目录名来访问它们以**训练**、**保存**和**预测**识别结果。每个文件夹中至少需要 50 张图像来训练模型，以获得良好的预测结果。训练更多的图像可以改善结果，但不建议这样做，因为执行起来需要很多时间，而且不会带来显著的改善。

### 履行

通过使用官方 opencv repo 中提供的样本对 SVM 进行 HOG 训练，我们实现了 c++ 代码来训练、保存和预测多张人脸图像上的面部特征。

有三种特征类型- *年龄*、*情感*和*性别*。四个年龄段，六种情绪，两种性别类型。因此 *n 类*分类器被实现来识别面部数据上的每个特征。

**步骤#1:** 对于每个特征类型(即年龄、情绪或性别)，循环运行“n”次。

```cpp
// CTrainTestHOG::Run(int run_times)
for (auto ft : m_FeatureList) {
    DEBUGLW("\tFeature type=[%s]\n", ft.first.c_str());

    std::vector<float> predictionAccuracyList;
    predictionAccuracyList.reserve(run_times);

    for (int run = 0; run < run_times; ++ run) {
        DEBUGLW("\t\tRun=[%d]\n", run);
        vector<Mat> trainData, predData;
        vector<int> trainLabels, predLabels;

        this->get_ft_dataset(ft.first, trainData, predData,
                                  trainLabels, predLabels);
        // ... train, predict and measure the SVM model.
    }
}
```

**步骤#2:** 每次运行时，迭代特征类型中的特征值，将图像变成向量或数组，即从文件夹中获取所有图像性别- >男，性别- >女。

```cpp
// CTrainTestHOG::get_ft_dataset()
std::set<cv::String>& featureValueList = m_FeatureList.find(ft)->second;

for (auto fv : featureValueList) {
    DEBUGLW("\t\t\tFeature value=[%s]\n", fv.c_str());
    std::vector<cv::Mat> _trainData;
    std::vector<cv::Mat> _predData;
    std::vector<int> _trainLabels;
    std::vector<int> _predLabels;

    errCode = this->get_ftfv_dataset(ft, fv, _trainData, _predData,
                                       _trainLabels, _predLabels);
    if (errCode != EXIT_SUCCESS)
        break;
    trainData.insert(trainData.end(), _trainData.begin(), _trainData.end());
    predData.insert(predData.end(), _predData.begin(), _predData.end());
    trainLabels.insert(trainLabels.end(), _trainLabels.begin(), _trainLabels.end());
    predLabels.insert(predLabels.end(), _predLabels.begin(), _predLabels.end());
}
```

**步骤#3 至#6:**

*   将矢量中的图像裁剪为面矩形，并用新的面列表更新图像矢量。
*   执行任何预处理任务，例如在人脸列表中的每个图像上调整到较小的尺寸(64，64)。
*   对预处理后的人脸图像进行矢量随机洗牌，引入随机输入数据。
*   将数据集分为训练数据(80%)和预测数据(20%)。

```cpp
//  CTrainTestHOG::get_ftfv_dataset()
std::vector<cv::Mat> imgList;
this->get_images(folderName, imgList);
this->get_cropped_faces(imgList);
this->get_preprocessed_faces(imgList);

//-- return on empty img list to prevent seg fault
if (imgList.empty()) {
    errCode = EXIT_FAILURE;
    DEBUGLE("Error img list is empty!\n");
    break;
}
DEBUGLD("\t\t\timgList.size()=[%ld]\n", imgList.size());

std::random_shuffle(imgList.begin(), imgList.end());

// 80% for training
int trainPart = imgList.size() * 0.8;

// 20% for predicting
int predPart = imgList.size() - trainPart;
DEBUGLD("\t\t\ttrainPart=[%d], predPart=[%d]\n", trainPart, predPart);

trainData.reserve(trainPart);
predData.reserve(predPart);

ft_t::iterator ft_iter = m_FeatureList.find(ft);
fv_t::iterator fv_iter = ft_iter->second.find(fv);
int label = std::distance(ft_iter->second.begin(),  fv_iter);
DEBUGLD("\t\t\tlabel=[%d]\n", label);

int i = 0;
for (; i < trainPart; ++ i) {
    trainData.push_back(imgList.at(i));
    trainLabels.push_back(label);
}
DEBUGLD("\t\t\ti=[%d], trainData.size()=[%ld], 
        trainLabels.size()
        = [% ld]\n ", i, trainData.size(), 
                       trainLabels.size());

for (; i < imgList.size(); ++ i) {
    predData.push_back(imgList.at(i));
    predLabels.push_back(label);
}
DEBUGLD("\t\t\ti=[%d], predData.size()=[%ld], 
        predLabels.size()
        = [% ld]\n ", i, predData.size(), predLabels.size());
```

**步骤#7 :** 计算训练数据中每个图像的 HOG。

```cpp
// CTrainTestHOG::computeHOGs()
HOGDescriptor hog;
vector<Mat> hogMats;
vector<float> descriptors;
for (auto img : imgHogList) {
    hog.winSize = img.size() / 8 * 8;
    hog.compute(img, descriptors);
    cv::Mat descriptors_mat(Mat(descriptors).clone());
    hogMats.push_back(descriptors_mat);
}
imgHogList.swap(hogMats);
```

**步骤#8 :** 将训练数据向量转换为 opencv Mat 对象训练 SVM。

```cpp
//  CTrainTestHOG::convert_to_ml()
for (size_t i = 0; i < train_samples.size(); ++ i) {
    CV_Assert(train_samples[i].cols == 1 || train_samples[i].rows == 1);
    if (train_samples[i].cols == 1) {
        cv::transpose(train_samples[i], tmp);
        tmp.copyTo(trainData.row((int)i));
    }
    else if (train_samples[i].rows == 1) {
        train_samples[i].copyTo(trainData.row((int)i));
    }
}
```

**步骤#9 :** 将训练数据 Mat 对象与训练数据的标签向量一起传递给 svm 训练函数。

```cpp
//  CTrainTestHOG::Run()
trainLabels.resize(ml_train_data.rows);
// train svm
DEBUGLW("\t\tTraining SVM - begin\n");
m_pSVM->train(ml_train_data, ROW_SAMPLE, trainLabels);
DEBUGLW("\t\tTraining SVM - end\n");
```

**步骤#10:** 保存训练好的模型。

```cpp
//-- step 10, CTrainTestHOG::Run()
cv::String svmModelFileName = cv::format("%s/cv4_svm_%s_model.xml",
                                         getenv(FFR_DATASET_PATH),
                                         ft.first.c_str());

m_pSVM->save(svmModelFileName.c_str());
DEBUGLW("\t\tSaved SVM model=[%s]\n",
        svmModelFileName.c_str());
```

**步骤#11:** 通过计算每个预测图像的 HOG 来预测模型，将预测数据集转换为 opencv mat 对象，并使用标签向量调用 svm predict 来存储结果。

```cpp
//-- step 11, CTrainTestHOG::Run()
// test the model
// compute HOG for each pre-processed face
errCode = this->computeHOGs(predData);
if (errCode != EXIT_SUCCESS) {
    DEBUGLE("Error in computing HOGs for the feature "
            "type=[%s]\n",
            ft.first.c_str());
    break;
}

// convert HOG feature vectors to SVM data
Mat ml_pred_data;
vector<int> resultLabels;
errCode = this->convert_to_ml(predData, ml_pred_data);
if (errCode != EXIT_SUCCESS) {
    DEBUGLE("Error in converting to ml for the "
            "feature type=[%s]\n",
            ft.first.c_str());
    break;
}
predLabels.resize(ml_pred_data.rows);
// resultLabels.resize(ml_pred_data.rows);
// test svm
DEBUGLW("\t\tTesting SVM - begin\n");
Mat responses_mat;
m_pSVM->predict(ml_pred_data, responses_mat);
for (size_t i = 0; i < ml_pred_data.rows; ++ i) {
    resultLabels.push_back(responses_mat.at<int>(i));
}
DEBUGLW("\t\tTesting SVM - end\n");
```

**步骤#12 和#13:** 通过比较预期预测标签和预测标签，计算其准确度的百分比。

```cpp
//  CTrainTestHOG::Run()
// check the accuracy
float accuracy = 0.0f;
this->get_prediction_accuracy(predLabels, resultLabels, accuracy);
DEBUGLW("\t\tPrediction accuracy=[%lf]\n", accuracy);
predictionAccuracyList.push_back(accuracy);

//-- step 13, CTrainTestHOG::Run()
// check the mean accuracy of 'n' runs
float sum_of_accuracies = std::accumulate(
    predictionAccuracyList.begin(),
    predictionAccuracyList.end(), 0.0);
float mean_accuracy = sum_of_accuracies / predictionAccuracyList.size();
DEBUGLW("\t\tMean prediction accuracy=[%lf]\n",
        mean_accuracy);
```

使用下面的命令行参数运行可执行文件。

```cpp
./train_hog --test --in= --out= <path_to_output>--show</path_to_output>
```

**输入:**
![Harry Potter sample input image](https://github.com/manid2/ProgramsForFun/raw/master/LearnOpenCV/ModifiedSamples/data/harry_potter_test_img_1.jpg)

**输出:**
![Harry Potter result output image](img/a8df3748fcdcbce93b257964ec6546f1.png)

[使用 OpenCV 2.4](https://github.com/manid2/FacialFeaturesRecognizer/blob/cv2.4/results_log.txt)
[的 HOG SVM 的结果日志使用 OpenCV 4.0](https://github.com/manid2/ProgramsForFun/blob/master/LearnOpenCV/ModifiedSamples/cv4_hog_svm_success_log.txt) 的 HOG SVM 的结果日志

**注意:**由于图像中的三个人都是长发，所以它检测到的性别是“女性”，这是一个假阳性。在机器学习算法中，由于输入样本图像具有不明确的特征，假阳性总是常见的。