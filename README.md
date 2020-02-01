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

###### Result
~~~java
a = 20
b = 10
num1 = 10
num2 = 20
~~~

##### Reason
~~~java
在 swap 方法中，a、b 的值进行交换，并不会影响到 num1、num2。因为，a、b 中的值，
只是从 num1、num2 的复制过来的。也就是说，a、b 相当于 num1、num2 的副本，
副本的内容无论怎么修改，都不会影响到原件本身
~~~

#### example 2

~~~java
    public static void main(String[] args) {
        int[] arr = { 1, 2, 3, 4, 5 };
        System.out.println(arr[0]);
        change(arr);
        System.out.println(arr[0]);
    }

    public static void change(int[] array) {
        // 将数组的第一个元素变为0
        array[0] = 0;
    }
~~~

###### Result
~~~java
1
0
~~~

##### Reason
~~~java
array 被初始化 arr 的拷贝也就是一个对象的引用，也就是说 array 和 arr 指向的是同一个数组对象。 
因此，外部对引用对象的改变会反映到所对应的对象上
~~~
