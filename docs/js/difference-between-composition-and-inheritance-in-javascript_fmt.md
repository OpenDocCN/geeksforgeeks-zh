# JavaScript 中合成和继承的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-composition-and-inheritance-in-javascript/](https://www.geeksforgeeks.org/difference-between-composition-and-inheritance-in-javascript/)

[**JavaScript 合成:**](https://www.geeksforgeeks.org/what-are-the-class-compositions-in-javascript/) 合成意为组合。JavaScript 中的一切都被当作一个对象，甚至 JavaScript 中的函数也被当作一个高级对象。这样的对象本质上是相当复杂的，要把大的复杂的对象变得简单，很多小的对象是组合在一起的。因此，我们可以说，对于这样的大型复杂对象，合成是更干净、可重用和更好的解决方案。

**例:**

## Javascript

```html
<script>
  const Motor = {
    accelerate(motorspeed, incrementSpeed) {
      return motorspeed + incrementSpeed;
    },
    decelerate(motorspeed, decrementSpeed) {
      return motorspeed - decrementSpeed;
    },
  };

  const StopMotor = {
    stop(motorspeed) {
      this.motorspeed = 0;
      return 0;
    },
  };

  const Brand = {
    model: "Maxpro",
  };

  const Treadmill = function (Design, Motor, StopMotor) {
    const brand = Object.create(Design);
    const motor = Object.create(Motor);
    const stopmotor = Object.create(StopMotor);
    const props = {
      motorspeed: 0,
      model: brand.model,
    };

    return {
      set(name, value) {
        props[name] = value;
      },
      get(name) {
        return props[name];
      },
      log(name) {
        console.log(`${name}: ${props[name]}`);
      },
      slowDown() {
        props.motorspeed = motor.decelerate(props.motorspeed, 5);
      },
      speedUp() {
        props.motorspeed = motor.accelerate(props.motorspeed, 10);
      },
      stop() {
        props.motorspeed = stopmotor.stop(props.motorspeed);
      },
    };
  };

  const Treadmill1 = Treadmill(Brand, Motor, StopMotor);

  // One can increase & decrease the motorspeed
  // according to their preferences
  Treadmill1.speedUp();
  Treadmill1.log("motorspeed");
  Treadmill1.slowDown();
  Treadmill1.log("motorspeed");
  Treadmill1.stop();
  Treadmill1.log("motorspeed");
  Treadmill1.log("model");

  // Let us change the model of Treadmill1 to Powermax
  Treadmill1.set("model", "PowerMax");
  Treadmill1.log("model");
</script>
```

**输出:**

```
"motorspeed: 10"
"motorspeed: 5"
"motorspeed: 0"
"model: Maxpro"
"model: PowerMax"
```

可以看出，上面的代码比下面的代码干净得多，因为这里机器的功能和特性都是分开的。因此，该类可以根据自己的需求实现合适的功能。`Treadmill1` 可以在需要时实现跑步机的功能。现在，`Treadmill1` 可以提高它的马达速度，降低它的马达速度，甚至可以根据需要改变它的型号名称。当谈到合成时，继承会自动得到帮助。

**JavaScript 继承:** 继承是获得父类的一些或全部特性(功能)，然后提供一个关系结构，这似乎有点乏味，不像类组合那样分别实现每个功能，这样每个类都可以根据自己的需求使用功能。说到 JavaScript 中的继承，Mixin 起着至关重要的作用。Mixin 实际上是混合，可以是任何东西，也就是说，将东西与东西混合在一起。为了正确理解这个概念，让我们举一个健身房/健身器的例子，这是一个健身机器混合。马达速度用于增加、减少和停止机器，下面描述的情况是继承的，因为 `Treadmill1` 被分配了对象及其跑步机的所有属性。因此，现在 `Treadmill1` 可以执行跑步机的所有功能，即可以提高电机速度，降低电机速度，甚至可以在我们的情况下设置属性，这是 `Maxpro` 之前的品牌和 `PowerMax` 之后的品牌。

**例:**

## Javascript

```html
<script>
  const machineMixin = {
    set(name, value) {
      this[name] = value;
    },
    get(name) {
      return this[name];
    },
    motorspeed: 0,
    inclinespeed() {
      this.motorspeed += 10;
      console.log(`Inclinedspeed is: ${this.motorspeed}`);
    },
    declinespeed() {
      this.motorspeed -= 5;
      console.log(`Declinedspeed is: ${this.motorspeed}`);
    },
    stopmachine() {
      this.motorspeed = 0;
      console.log(`Now the speed is: ${this.motorspeed}`);
    },
  };

  const Treadmill = { brand: "Maxpro", motorspeed: 0 };
  const Treadmill1 = Object.assign({}, Treadmill, machineMixin);

  // You can increase the speed of Treadmill1
  Treadmill1.inclinespeed();

  // You can even decrease the speed of Treadmill1
  Treadmill1.declinespeed();

  // Let's just stop the machine
  Treadmill1.stopmachine();

  // It's Time to access the brand of treadmill1
  console.log(Treadmill1.get("brand"));

  // let's change the brand of Treadmill1
  Treadmill1.brand = "PowerMax";
  console.log(Treadmill1.get("brand"));
</script>
```

**输出:**

```
"Inclinedspeed is: 10"
"Declinedspeed is: 5"
"Now the speed is: 0"
"Maxpro"
"PowerMax"
```

在上面的输出中，可以清楚地看到，所有操作都是由 `Treadmill1` 执行的，该 `Treadmill1` 被分配了一个拥有 `machineMixin` 的 `Treadmill` 对象。首先，在应用 `inclinespeed()` 方法后，电机速度为 0，在执行降低速度 5 的 `declinespeed()` 方法后，电机速度增加 5，最后执行 `stopmachine()` 操作，通过使电机速度为零来停止机器。品牌由 `Maxpro` 改为 `PowerMax`，展现了继承的力量。下面是 Composition 和 Inheritance 之间的对照表。

| **Composition** | **Inheritance** |
| --- | --- |
| Follows has a relationship | Follows is a relationship |
| Allows code-reuse. | Inheritance does not allow code reuse. |
| In composition, you will no longer need to extend the class. | In inheritance, you will need to extend the class. |
| You won't need Mixin in composition. | Mixin plays a major role in inheritance. |
| The composition is flexible. | Inheritance is less flexible than composition. |

**结论:** 两种继承和合成产生相同的结果，但是实现的方式很重要。组合实现方式比继承更容易理解和实现。

读者请注意！现在不要停止学习。以学生友好的价格获得所有重要的 JavaScript 课程，并为行业做好准备。