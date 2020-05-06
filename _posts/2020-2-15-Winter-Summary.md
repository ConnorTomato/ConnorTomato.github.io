---
title: 2020寒假总结
date: 2020-2-15-10:00:00
categories:
- Term Summary
tags:
- Term Summary
---

> ### ✏️寒假总结

#### 1.编程学习

- 

  ▶️翁恺老师的OOP（67/67）

- 

  ▶️浙大数据结构（64/173）

  > 数据结构是看到图了，没有急着往后看，在LC上先刷一定数量二叉树题接着学习.

- 

  📔《Java核心技术卷Ⅰ》（709/709）

  > 这是Java入门书，里面很多知识点没有实操过，远没有掌握，Java学习遇到困难会在着重翻开几章重新看

- 

  📝LeetCode每日一题

  > 2月3号开始坚持每天刷一道算法题的，在每周日就重新把一周做过的题重新写or复习一遍，很慢！

------

#### 2.寒假读书

- 工具书：《Java核心技术卷Ⅰ》
- 《三体》三部
- 《飘》
- 《算法图解》

------

#### 3.学习之外

1. 假期每天一定练一小时字（2461min）
2. 过年之前的三周还在健身：33KM+324min的撸铁
3. 刷了《西部世界》两季+《爱情公寓5》
4. 电影《当幸福来敲门》、《模仿游戏》、漫威整个电影宇宙

> **漫威电影宇宙第一阶段：**
>
> 《钢铁侠》（2008）
>
> 《无敌浩克》（2008）
>
> 《钢铁侠2》（2010）
>
> 《雷神》（2011）
>
> 《美国队长》（2011）
>
> 《复仇者联盟》（2012）。
>
> **第二阶段：**
>
> 《钢铁侠3》（2013）
>
> 《雷神2：黑暗世界》（2013）
>
> 《美国队长2：冬日战士》（2014）
>
> 《银河护卫队》（2014）
>
> 《复仇者联盟2：奥创纪元》（2015）
>
> 《蚁人》（2015年7月）
>
> **第三阶段：**
>
> 《美国队长3：内战》（2016年）、
>
> 《奇异博士》（2016年11月）、
>
> 《银河护卫队2》（2017年5月）、
>
> 《蜘蛛侠：英雄归来》
>
> 《雷神3：诸神黄昏》
>
> 《黑豹》
>
> 《复仇者联盟3：无限战争》
>
> 《蚁人2：黄蜂女现身》

------



> #### **我的第一周**

##### **1.Java学习**

> 开始第二阶段的翁恺的OOP（18/67）
> 《Java核心技术卷1》（100/709）

- 类是构造对象的模板或蓝图。
  由类构造对象的过程称为创建类的实例。
- 局部变量：在方法、构造方法或者语句块中定义的变量被称为局部变量。变量声明和初始化都是在方法中，方法结束后，变量就会自动销毁。
  成员变量：成员变量是定义在类中，方法体之外的变量。这种变量在创建对象的时候实例化。成员变量可以被类中方法、构造方法和特定类的语句块访问。
  类变量：类变量也声明在类中，方法体之外，但必须声明为static类型。

------

##### **2.作业：java——复数加减乘除计算**

> 在Creation_Operation 封装

```java
import java.util.Scanner;
public class Creation_Operation {
        double real_number = 0;
        double imaginary_num = 0;
        //*获取数据
    Creation_Operation(){
        Scanner in = new Scanner(System.in);
        real_number = in.nextDouble();
        imaginary_num = in.nextDouble();
        complex(real_number,imaginary_num);
    }

    Creation_Operation(double real_number,double imaginary_num){
        this.imaginary_num = imaginary_num;
        this.real_number = real_number;
    }
    private void complex(double real_number,double imaginary_num){
        this.real_number = real_number;
        this.imaginary_num = imaginary_num;
    }

        //*加法
     Creation_Operation add(Creation_Operation a) {
         double addone = real_number + a.real_number;
         double addtwo = imaginary_num + a.imaginary_num;
         Creation_Operation result = new Creation_Operation(addone,addtwo);
         return result;
    }
        //*减法
    Creation_Operation  sub(Creation_Operation a){
        double subone = real_number - a.real_number;
        double subtwo = imaginary_num - a.imaginary_num;
        Creation_Operation result = new Creation_Operation(subone,subtwo);
        return  result;
    }
        //*乘法
    Creation_Operation  mul(Creation_Operation a){
        double mulone = real_number * a.real_number - imaginary_num * a.imaginary_num;
        double multwo = real_number * a.imaginary_num + imaginary_num * a.real_number;
        Creation_Operation result =new Creation_Operation(mulone,multwo);
        return  result;
    }
        //*除法
    Creation_Operation div(Creation_Operation a){
        double divone = (real_number * a.real_number+ imaginary_num * a.imaginary_num ) / (a.real_number * a.real_number + a.imaginary_num * a.imaginary_num);
        double divtwo = (imaginary_num * a.real_number - real_number *a.imaginary_num) / (a.real_number * a.real_number + a.imaginary_num * a.imaginary_num);
        Creation_Operation result =new  Creation_Operation(divone,divtwo);
        return  result;
    }
        //*打印
    public void print(){
        if(imaginary_num>0)
            System.out.println(real_number + "+"+imaginary_num+"i");
        else if(imaginary_num == 0)
            System.out.println(real_number + " ");
        else
            System.out.println(real_number + " "+imaginary_num+"i");


    }
}
```

> Main中数据测试

```java
public class Main{
    public static void main(String[]args){
        Creation_Operation Testone = new Creation_Operation();
        Creation_Operation Testtwo = new Creation_Operation();

        Creation_Operation result_add = Testone.add(Testtwo);
        Creation_Operation result_sub = Testone.sub(Testtwo);
        Creation_Operation result_mul = Testone.mul(Testtwo);
        Creation_Operation result_div = Testone.div(Testtwo);

        result_add.print();
        result_sub.print();
        result_mul.print();
        result_div.print();
    }
}
```

[![批注 2020-01-12 115958](https://user-images.githubusercontent.com/57027969/72218155-cc65f800-3572-11ea-95df-dd9537e35726.png)](https://user-images.githubusercontent.com/57027969/72218155-cc65f800-3572-11ea-95df-dd9537e35726.png)

------

##### **3.学习外的生活**

- 开始阅读《三体》（未开始）.
- 早起练字（Everyday).
- 7KM跑步+哑铃弯举（今天周日）

------

[![我是分界线啊](https://camo.githubusercontent.com/503dd74a3b7e341aa1d38bc99a2a6813430197f5/68747470733a2f2f706963312e7a68696d672e636f6d2f38302f76322d64393230376138306437326230306161656239646533396362343362323966365f68642e6a7067)](https://camo.githubusercontent.com/503dd74a3b7e341aa1d38bc99a2a6813430197f5/68747470733a2f2f706963312e7a68696d672e636f6d2f38302f76322d64393230376138306437326230306161656239646533396362343362323966365f68642e6a7067)

------

#### 👴🏻的第二周

**1.学习进度**

[![批注 2020-01-19 213350](https://user-images.githubusercontent.com/57027969/72682336-e40b2680-3b06-11ea-9b9b-ae6187edb263.png)](https://user-images.githubusercontent.com/57027969/72682336-e40b2680-3b06-11ea-9b9b-ae6187edb263.png)

总结：

> - 听力6篇
> - 练字共424min==7h4min
> - 《核心技术1》（178/709）
> - OOP(31/67)
> - 整理了笔记到Github
> - 大物学习到第三章

------

**2.学习外的生活**

> - 一周跑步21KM
> - 撸铁265min==4h25min
> - 看完《三体1》

------

**3.一些🖊话**

> 每天都有自己的学习计划，但不可能每天完美执行你的安排，总有一些AC事给耽误了，周六聚会周日出去玩，在需要改变你的预期计划时，调整心态，顺延你的task。

------

#### **My third week**

1.记录（*这有一张图片，可以查看*）

[![批注 2020-01-26 185501](https://user-images.githubusercontent.com/57027969/73135381-55555700-407c-11ea-8156-cfedb5ab7e9d.png)](https://user-images.githubusercontent.com/57027969/73135381-55555700-407c-11ea-8156-cfedb5ab7e9d.png)

·总结

> - 听力8篇
> - 跑步5km+撸铁59min ——————————（健身房关了，开了我也不敢去dog）
> - OOP(52/67)
> - 数据结构（21/143）
> - 《三体2》（1/3）
> - 练字450min=7h30min
> - 大物开第四章

------

**2.Java学习**
《核心技术》看到了接口，还没有看懂
Java题在写翁恺MOOC上的作业

> 题目内容：
>
> 设计一个表示分数的类Fraction。这个类用两个int类型的变量分别表示分子和分母。
>
> 这个类的构造函数是：
>
> Fraction(int a, int b)
>
> ```
> 构造一个a/b的分数。
> ```
>
> 这个类要提供以下的功能：
>
> double toDouble();
>
> ```
> 将分数转换为double
> ```
>
> Fraction plus(Fraction r);
>
> ```
> 将自己的分数和r的分数相加，产生一个新的Fraction的对象。注意小学四年级学过两个分数如何相加的哈。
> ```
>
> Fraction multiply(Fraction r);
>
> ```
> 将自己的分数和r的分数相乘，产生一个新的Fraction的对象。
> ```
>
> void print();
>
> ```
> 将自己以“分子/分母”的形式输出到标准输出，并带有回车换行。如果分数是1/1，应该输出1。当分子大于分母时，不需要提出整数部分，即31/30是一个正确的输出。
> ```
>
> 注意，在创建和做完运算后应该化简分数为最简形式。如2/4应该被化简为1/2。
> import java.util.Scanner;

**Main主函数**

```java
public class Main {


    public static void main(String[] args) {

        Scanner in = new Scanner(System.in);

        Fraction a = new Fraction(in.nextInt(), in.nextInt());

        Fraction b = new Fraction(in.nextInt(),in.nextInt());

        a.print();

        b.print();

        a.plus(b).print();

        a.multiply(b).plus(new Fraction(5,6)).print();

        a.print();

        b.print();

        in.close();

    }


}
```

**数据操作**

```java
public class Fraction {
        private int a = 0;
        private int b = 1;
        //*构造函数
        Fraction(int a,int b){
            this.a = a;
            this.b = b;
        }

        double toDouble(){
            return a/b;
        }
    
        //*分数加法

        Fraction plus(Fraction r){
            Fraction new1 =new Fraction(0,1);
            new1.a = (this.a * r.b) +(this.b * r.a);
            new1.b = this.b * r.b;
            return  new1;
        }
        //* 乘法

        Fraction multiply(Fraction r){
            Fraction new1 =new Fraction(0,1);
            new1.a = this.a * r.a;
            new1.b = this.b * r.b;
            return  new1;

        }
        //*最大公约数，约分

        int gcd(int a,int b){
            if(a%b==0)
                return  b;
            else
                return gcd(b,a%b);
        }


        //*打印

    void print(){
            if(a==b)
                System.out.println("1");
            else{
                int gys=gcd(a,b);
                a = a / gys;
                b = b / gys;
                System.out.println(a+"/"+b);

            }
        }
}
```



------

**3.方法论**

> 罗斯福Blister Intensuty：一张思维导图

## [![批注 2020-01-26 200506](https://user-images.githubusercontent.com/57027969/73135324-a57fe980-407b-11ea-911c-444768402490.png)](https://user-images.githubusercontent.com/57027969/73135324-a57fe980-407b-11ea-911c-444768402490.png)

#### 我的第四周

| Monday                        | Tuesday              | Wednesday                | Thursday             | Friday    | Weekend            |
| ----------------------------- | -------------------- | ------------------------ | -------------------- | --------- | ------------------ |
| 练字50min                     | 练字49min            | 练字61min                | 练字65min            | 练字67min | 练字106min         |
| 《三体2》读到“自然选择号”逃离 | 开启《三体3》        | Java书跳过异常开始第八章 | 大物4-2              |           | 数据结构（33/143） |
| Java书（240/709）             | OOP（67/67）【完结】 | 整理Github笔记           | 复习链表操作         |           | 《三体3》阶梯计划  |
| OOP（57/67）                  |                      |                          | 数据结构跳过了栈开树 |           | 听力2篇高淇java    |

### 总结：

1. 练字398min = 6h38min.
2. 翁恺OOP学习完.
3. Java书（309/709）
4. 数据结构（33/143）
   [5.Github笔记整理](https://github.com/ConnorTomato/Notes/blob/master/Java_Notes/《Java核心技术-卷1》.md)
5. 保持每日一题

------

**数据结构实操：**

- [[单向链表4个操作\]](https://github.com/ConnorTomato/Data-Structure/blob/master/链表/单向链表4个操作.c)
- [[合并两个有序链表\]](https://github.com/ConnorTomato/Data-Structure/blob/master/链表/LeetCode合并两个有序链表.c)

**做题**：

- 每天会在CF或LeetCode做一道.

------

| 周一                | 周二               | 周三                  | 周四              | 周五               | 周末               |
| ------------------- | ------------------ | --------------------- | ----------------- | ------------------ | ------------------ |
| 练字：61min         | 练字：57min        | 练字：55min           | 练字：57min       | 练字58min          | 练字:115min        |
| 《三体3》执剑人交接 | 《三体3》进入四维  | 《三体3》云天明讲故事 | 《三体》读完      | 数据结构（50/143） | 数据结构（54/143） |
| 构（40/143）        | 数据结构（43/143） | 数据结构（47/143）    | Java书（353/709） | Java链表           | Java书（405/709）  |

-  每日一道LeetCode链表题.
-  学会手写实现二叉树基本操作

------

总结：

1. 练字：406min = 6h46min。
2. 《三体》全集阅读完毕。
3. 数据结构（54/143）
4. Java书跳过事件开启第13章。
5. 每天一道链表。

| 周一              | 周二           | 周三               | 周四              | 周五            | 周末        |
| ----------------- | -------------- | ------------------ | ----------------- | --------------- | ----------- |
| 练字：49min       | 练字：57min    | 练字：54min        | 练字：60min       | 练字：71min     | 练字:114min |
| 复习Java预习高数  | 《飘》（9/62） | 数据结构（64/143） | 预习高数          | 预习高数        | 预习高数X2  |
| Java书（581/709） | 预习高数       | java书（625/709）  | Java书（653/709） | Java书看完      | 《飘》读毕  |
|                   |                | 《飘》（31/62）    | 《飘》（37/62）   | 《飘》（52/62） | 写作业      |

-  每日二道LeetCode 链表＋树 题.
-  每天阅读一小时

------

总结：

1. 练字：455min = 6h35min。

2. 《Java核心技术卷一》、《飘》读完。

   > Java书看完只是知道一些概念，后期部分Java集合、并发’接口、lambda表达式都没有掌握

3. 数据结构（64/143）

   > 下一个知识点是图了，之前栈、树的只会基本操作，停一段时间刷题理解巩固

   ------

   ##### 下周大体计划：

   - 以后周日：回顾复习一周刷的题、重写一遍已学的数据结构
   - 开《算法图解》补一下基础

------

## 