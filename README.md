# JavaReference

#### 首先说两个专业术语

* 按值调用(call by value)
  * 方法接收的是调用者提供的值

* 引用调用（call by reference)
  * 方法接收的是调用者提供的变量地址

###### Java 程序设计语言总是采用按值调用(call by value) 方法得到的是所有参数值的一个拷贝


#### example 1

~~~java
public static void main(String[] args) {
    int num1 = 10;
    int num2 = 20;

    swap(num1, num2);

    System.out.println("num1 = " + num1);
    System.out.println("num2 = " + num2);
}

public static void swap(int a, int b) {
    int temp = a;
    a = b;
    b = temp;

    System.out.println("a = " + a);
    System.out.println("b = " + b);
}
~~~

##### Result
~~~java
a = 20
b = 10
num1 = 10
num2 = 20
~~~
