# Polymorphism & Composition Homework - Quiz

# Polymorphism

1. What does the word 'polymorphism' mean?
It means one thing being instantiated in to many different forms
2. What does it mean when we apply polymorphism to OO design? Give a simple Java example.
It means we can make many different forms of the same thing, based on it's fundamentals. 

```import java.util.*;

public class Network {
    private String name;
    private ArrayList<IConnect> devices;

    public Network(String name){
        this.devices = new ArrayList<IConnect>();
        this.name = name;
    }

    public String getName(){
        return name;
    }

    public int deviceCount(){
        return devices.size();
    }

    public void connect(IConnect device){
        devices.add(device);
    }

    public void disconnectAll(){
        devices.clear();
    }
}```

3. What can we use to implement polymorphism in Java?
We can use abstract classes and Interfaces to implement polymorphism
4. How many 'forms' can an object take when using polymorphism?
As many as you require.
5. Give an example of when you could use polymorphism.
You could use polymorphism when creating a fruit class. Polymorphism would help you create many different kinds of fruit based off of their fundamentals.


# Composition

6. What do we mean by 'composition' in reference to object-oriented programming?
It means you can make a brand new class based off of another class.
7. When would you use composition? Provide a simple example in Java.
We would use composition when we want a number of objects to do the same thing, but make sure their output is relevant to what they are. 

```public class Printer extends PrintingDevice implements IOutput {
    private int dpi;
    private int printSpeed;

    public Printer(String make, String model, int dpi, int printSpeed) {
        super(make, model);
        this.dpi = dpi;
        this.printSpeed = printSpeed;
    }

    public int getDpi() {
        return this.dpi;
    }

    public int getPrintSpeed() {
        return this.printSpeed;
    }

    private String print(String data) {
        return "printing: " + data;
    }

    public String outputData(String data) {
        return this.print(data);
    }
}```

8. What is/are the advantage(s) of using composition?
We can add functionality to multiple objects using compisition, allowing us to use existing code
9. When an object is destroyed, what happens to all the objects it is composed of?
The other objects are also destroyed