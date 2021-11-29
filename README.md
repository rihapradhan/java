# What is Reflection?
Reflection is the ability of a program to analyze itself. The java.lang.reflect package provides the ability to obtain the information about the fields, constructors, methods, and modifiers of a class. Normally such information is needed to build software tools that enable us to to work with Java Beans components. The tools use reflection to determine dynamically the characteristics of a component.

# Why is reflection useful?
Java reflection is useful because it supports dynamic retrieval of information about classes and data structures by name, and allows for their manipulation within an executing Java program This feature is extremely powerful and has no equivalent in other conventional languages such as C, C++, Fortran, or Pascal.

# Drawbacks of Reflection
Reflection is a powerful tool to inspect the code. It helps in debugging. Its can be used to modify the runtime behavior of the application running in JVM. But it should not be used often because it is comes with some disadvantages.

### Performance Overhead 
Because reflection involves types that are dynamically resolved certain Java virtual machine optimizations cannot be performed. Consequently, reflective operations have slower performance than their non-reflective counterparts. 
### Security Restrictions
Reflection requires a runtime permission which may not be present when running under a security manager. This is in an important consideration for code which has to run in a restricted security context, such as in an Applet. 
### Exposure of Internals
Since reflection allows code to perform operations that would be illegal in non-reflective code, like accessing private fields and methods, the use of reflection can result in unexpected side-effects, which may render code dysfunctional and may destroy portability.

# Setting up to use Reflection 
The reflection classes, such as Method, are found in java.lang.reflect. There are three steps that must be followed to use these classes. The first step is to obtain a java.lang.Class object for the class that you want to manipulate. java.lang.class is used to represent classes and interfaces in a running Java program.

**1.** One way of obtaining a Class object is to say: Class c class.forName("java.lang.String");
to get the Class object for String. Another approach is to use:
class c = int.class;
to obtain Class information on fundamental types. The latter approach accesses the predefined TYPE field of the wrapper (such as Integer) for the fundamental type.

**2.** The second step is to call a method such as getDeclaredMethods, to get a list of all the methods declared by the class.

**3.** The third step is to use the reflection API to manipulate the information.

For example, the sequence: Class c = Class. forName("java.util.Stack");

Method m[ ] = c.getDeclaredMethods ();

System.out.println (m[0].toString());

> This will display a textual representation of the first method declared in String.**


# Examples of Reflection

### 1. A program to count the number of instances of a class using class variable (i.e. static variable)

class SampleClass {

// Set count to zero initially.

static int count = 0; 

public SampleClass() {

// increment the count on each call to the constructor via any instance

count = count + 1;

System.out.println("Created object number: " + count);
  }
}

public class ObjectCount Demo {

public static void main(String[] args) { 
SampleClass stuffl = new SampleClass();
SampleClass stuff2 = new SampleClass();
  }
 }




