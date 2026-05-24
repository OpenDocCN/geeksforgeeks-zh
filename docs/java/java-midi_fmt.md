# Java MIDI 简介

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-midi/

乐器数字接口(MIDI)标准定义了用于电子音乐设备(例如电子键盘乐器和个人计算机)的通信协议。在现场演奏期间，MIDI数据可以通过特殊电缆传输，也可以存储在标准类型的文件中供以后回放或编辑。
midi文件包含以事件形式表示音乐的数据。每个事件都描述了要播放的音符—持续时间、音调、速度、通道等。`javax.sound.midi`包为midi数据的I/O、排序和合成提供了接口和类。
MIDI既是硬件规范，也是软件规范。
`javax.sound.midi`软件包用于创建和使用midi事件，以Java制作简单的原声。

## Java声音API对MIDI设备的表示

*   `MidiDevice`接口：`MidiDevice`接口包括用于打开和关闭设备的API。它还包括一个名为`MidiDevice.Info`的内部类，提供设备文本描述的信息，包括设备名称、供应商和版本。
*   发射器和接收器：设备发送数据的方式是通过它“拥有”的一个或多个发射器(`Transmitter`)对象。类似地，设备接收数据的方式是通过其一个或多个接收器(`Receiver`)对象。发射器对象实现`Transmitter`接口，接收器实现`Receiver`接口。
    每个发射器一次只能连接到一个接收器，反之亦然。

## MIDI系统的基本组件

*   合成器(`Synthesizer`)：这是播放midi原声的设备。它可以是软件合成器，也可以是真正的midi兼容乐器。
*   音序器(`Sequencer`)：音序器(通过序列`Sequence`)接收Midi数据，并命令不同的乐器演奏音符。它根据开始时间、持续时间和要播放的频道来安排事件。
*   通道(`Channel`)：Midi最多支持16个不同的通道。我们可以向这些通道中的任何一个发送midi事件，这些通道随后由音序器同步。
*   轨道(`Track`)：是Midi事件的序列。
*   序列(`Sequence`)：是包含多个轨道和时序信息的数据结构。音序器接收序列并播放它。

## 重要类和方法

*   `MidiSystem`：这个类提供了对已安装MIDI资源的访问，如音序器、合成器、输入/输出端口。所有方法都是静态的，这个类不能被实例化。
*   `MidiSystem.getSequencer()` – 返回连接到合成器/接收器的音序器接口的实例。
*   `Sequencer.open()` – 打开`Sequencer`，使其可以获取系统资源。
*   `Sequencer.setSequence(Sequence sequence)` – 设置音序器运行的当前序列。
*   `Sequencer.setTempoInBPM(float BPM)` – 以每分钟节拍为单位设置回放速度。
*   `Sequencer.start()` – 开始播放当前加载序列中的MIDI数据。
*   `Sequencer.isRunning()` – 指示`Sequencer`当前是否正在运行。
*   `Sequence` – `Sequence`类实例保存表示一个或多个轨道和定时信息的数据结构。
*   `Sequence.PPQ` – 基于速度的计时类型，分辨率以每四分之一音符的脉冲(节拍)表示。
*   `Sequence.createTrack()` – 创建一个空轨道。
*   `Track` – 包含按时间顺序排列的midi事件的类别。
*   `Track.add(MidiEvent event)` – 向轨道添加新事件。
*   `MidiEvent(MidiMessage message, long tick)` – 包含带时间戳的midi消息的midi事件对象。
*   `ShortMessage()` – 一个最多有两个数据字节的短消息对象(从`MidiMessage`扩展而来)。
*   `ShortMessage.setMessage(int command, int channel, int data1, int data2)` – 设置一个最多有两个数据字节(`data1`和`data2`)的`ShortMessage`对象。

## MIDI命令

| code | order |
| --- | --- |
| 144 | 注意开事件 |
| 128 | 注意关事件 |
| 192 | 更改程序以更改默认乐器等 |
| 176 | 控制器事件 |

下面的程序说明了MIDI在Java中的用法：

### 程序1：简单记录的实现

```java
// Java program showing the implementation of a simple record
import javax.sound.midi.*;
import java.util.*;

public class MyMidiPlayer {

    public static void main(String[] args)
    {

        System.out.println("Enter the number of notes to be played: ");
        Scanner in = new Scanner(System.in);
        int numOfNotes = in.nextInt();

        MyMidiPlayer player = new MyMidiPlayer();
        player.setUpPlayer(numOfNotes);
    }

    public void setUpPlayer(int numOfNotes)
    {

        try {

            // A static method of MidiSystem that returns
            // a sequencer instance.
            Sequencer sequencer = MidiSystem.getSequencer();
            sequencer.open();

            // Creating a sequence.
            Sequence sequence = new Sequence(Sequence.PPQ, 4);

            // PPQ(Pulse per ticks) is used to specify timing
            // type and 4 is the timing resolution.

            // Creating a track on our sequence upon which
            // MIDI events would be placed
            Track track = sequence.createTrack();

            // Adding some events to the track
            for (int i = 5; i < (4 * numOfNotes) + 5; i += 4)
            {

                // Add Note On event
                track.add(makeEvent(144, 1, i, 100, i));

                // Add Note Off event
                track.add(makeEvent(128, 1, i, 100, i + 2));
            }

            // Setting our sequence so that the sequencer can
            // run it on synthesizer
            sequencer.setSequence(sequence);

            // Specifies the beat rate in beats per minute.
            sequencer.setTempoInBPM(220);

            // Sequencer starts to play notes
            sequencer.start();

            while (true) {

                // Exit the program when sequencer has stopped playing.
                if (!sequencer.isRunning()) {
                    sequencer.close();
                    System.exit(1);
                }
            }
        }
        catch (Exception ex) {

            ex.printStackTrace();
        }
    }

    public MidiEvent makeEvent(int command, int channel,
                               int note, int velocity, int tick)
    {

        MidiEvent event = null;

        try {

            // ShortMessage stores a note as command type, channel,
            // instrument it has to be played on and its speed.
            ShortMessage a = new ShortMessage();
            a.setMessage(command, channel, note, velocity);

            // A midi event is comprised of a short message(representing
            // a note) and the tick at which that note has to be played
            event = new MidiEvent(a, tick);
        }
        catch (Exception ex) {

            ex.printStackTrace();
        }
        return event;
    }
}
```

```java
Input: Enter the number of notes to be played:

Output: 15 sound notes with increasing pitch are played

Input: Enter the number of notes to be played:

Output: 25 sound notes with increasing pitch are played

(Note: Number of notes should not exceed 31 for reasons cited later)
```

**为什么音符数量限制在31个？**
由于`ShortMessage`的`data1`和`data2`字段为字节类型，在使用`setMessage(int command, int channel, int note, int velocity)`时，`note`和`velocity`不得超过127。

### 程序2：使用命令代码192更改仪器类型

```java
// Java program showing how to change the instrument type
import javax.sound.midi.*;
import java.util.*;

public class MyMidiPlayer1 {

    public static void main(String[] args)
    {

        MyMidiPlayer1 player = new MyMidiPlayer1();

        Scanner in = new Scanner(System.in);
        System.out.println("Enter the instrument to be played");
        int instrument = in.nextInt();
        System.out.println("Enter the note to be played");
        int note = in.nextInt();

        player.setUpPlayer(instrument, note);
    }

    public void setUpPlayer(int instrument, int note)
    {

        try {

            Sequencer sequencer = MidiSystem.getSequencer();
            sequencer.open();
            Sequence sequence = new Sequence(Sequence.PPQ, 4);
            Track track = sequence.createTrack();

            // Set the instrument type
            track.add(makeEvent(192, 1, instrument, 0, 1));

            // Add a note on event with specified note
            track.add(makeEvent(144, 1, note, 100, 1));

            // Add a note off event with specified note
            track.add(makeEvent(128, 1, note, 100, 4));

            sequencer.setSequence(sequence);
            sequencer.start();

            while (true) {

                if (!sequencer.isRunning()) {
                    sequencer.close();
                    System.exit(1);
                }
            }
        }
        catch (Exception ex) {

            ex.printStackTrace();
        }
    }

    public MidiEvent makeEvent(int command, int channel,
                               int note, int velocity, int tick)
    {

        MidiEvent event = null;

        try {

            ShortMessage a = new ShortMessage();
            a.setMessage(command, channel, note, velocity);

            event = new MidiEvent(a, tick);
        }
        catch (Exception ex) {

            ex.printStackTrace();
        }
        return event;
    }
}
```

```java
Input : Enter the instrument to be played

Enter the note to be played

Output : Sound note is played

Input : Enter the instrument to be played

Enter the note to be played

Output : Sound note is played
```

**注意：** 代码不会在在线IDE上运行，因为代码需要几秒钟的运行时间来回放，而IDE不允许。