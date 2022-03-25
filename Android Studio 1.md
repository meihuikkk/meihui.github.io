# The XML Layout File
## Orientation
- The widgets are stacked in sequence according to the orientation
    - two possile orientations: ```horizontal``` and ```vertical``` (default is ```horizontal```)<br/>
## TextView Widget
```
<TextView
    android:id="@+id/myTextView"
    android:layout_width = "wrap_content
    android:layout_height = "match_parent"
    android:layout_gravity="center"
    android:gravity="end"
    android:text="second" />
```
- the ```id``` attribute enables ue to give a unique ID to each widget in the XML layout file, with which they can be accessed <br/>
- the ```text``` attribute specifices the text that the widget should contain

## Button Widget
```
<Button
    android:id="@+id/myButton
    android:layout_width-"match_parent>
    android:layout_height="wrap_content"
    android:text="Click me"
```
## Attributes in the Widget
### Sizing the Widget
- ```wrap_content```: sizes the widget tp fit the content
- ```match_parent```: sizes the widget to fit the screen size //screen here is the parent
### Widget Alignment
- align **a widget** within a layout -> ```layout_gravity``` //child to parent
- align **contents of a widget** within the widget itself -> ```gravity``` //parent to child

## Random Class
- ```nextInt()```: gives out an integer between 0 and $2^{32}$ (exclusive)
- ```nextInt(n)```: gives out an iteger between 0 and n (exclusive)
- ```nextDouble()```: gives out a double 0.0 and 1.0
### Using date as seed to generate random numbers
```
Data d = new Date()
Random e = new Random(d.getTime());
```
<br/>
<br/>

# Nested Classes
A class definition contains class definition <br/>
Both of the inner and outer classes are called nested classes<br/>
The inner classes logically depends on the outer class and are used tgt with the outer class.
```
public class OuterClass{

    class InterClass{

    }
}
```
## Inner Class
- A nested class that is **not declared static** is called an **Inner Class** <br/>
- You need **an instance of the outer class** to **instantiate** an inner class, this outer class is called the **enclosing class**
- The inner class **have access to all methods and variables** of its enclosing outer class.
### Instantiation of the innerclass:
``` 
OuterClass outerObject = new OuterClass();
OuterClass.InnerClass innerObject = outerObject.new InnerClass();
```
### Example
```
package com.example.lib01;

public class OuterClass {
    int a;
    OuterClass(){
        a = 10;
    }
    void outerPrintA(){
        System.out.println(a);
    }

    class InnerClass{
        int c;
        InnerClass(){
            c = 100;
        }
        void innerPrintA(){
            a = 100;
            System.out.println(a);
        }
        OuterClass giveBackOuter(){
            return OuterClass.this;
        }
    }
}
```

```
package com.example.lib01;

public class MyClass {
    public static void main(String[] args){
        OuterClass outerObject = new OuterClass();
        //Instantiate InnerClass using instance of the outer class
        OuterClass.InnerClass innerObject = outerObject.new InnerClass();
        outerObject.outerPrintA(); //output is 10
        //Show that the Inner Class can access variables in OuterClass
        innerObject.innerPrintA();//output is 100
        //Show that InnerClass stores a reference to OuterClass
        innerObject.giveBackOuter();
        //inner class can access and modify variables in OuterClass
        outerObject.outerPrintA();//output is 100
    }
}
```
<br/>

## Static Nested Class
- A nested class declared to be static
    - It can only access **static variables and methods** in the outer class












