Module 7

#7A Intro to Inheritance

The concept of inheritance
- design and programming concept of building on existing classes to crate new more specialized classes

EX: 
---------------------------------------------------------------
Class 1 # (parent, super, base)
|        \
class 2   class 3  # (child, sub, derived)
|
class 4 # (direct subclass of class 2, indirect subclass of class 1)
---------------------------------------------------------------

Each subclass has exactly 1 immediate parent.
Some Object oriented languages allow multiple parents but not java

When we define new subclasses, only need to add the delta code to child class

Ex: Extending an existing class

Class: Rectangle (length, width)
  Methods:   rectangle(), 
             rectanble(l,w), 
             setWidth(w)
             setLenght(l)
             setSides(l,w)
             getLength()
             getWidth()

sub class: EnchancedRectangle  # has everything from Rectangle + getArea
  Methods:   getArea()

Only need to write new code for getArea, can call/reuse other stuff


EX: Extending an Existing Class  #  extends keyword tells java it is a subclass of Rectangle

---------------------------------------------------------------

public class EnhancedRectangle extends Rectangle 
{
  public double getArea() 
  {
    return getLength() * getWidth();
  }
}

---------------------------------------------------------------

EX: Inheritance Example 2

---------------------------------------------------------------

public class RectangleInheritanceDemo
{
  public static void main( String[] args )
  {
    EnhancedRectangle anEnchancedRectangle = new EnhancedRectangle();

    // Set attributes for enhanced rectangle
    enhancedRectangle.setSides( 40, 30 );

    // Display attributes and area
    System.out.println();
    System.out.println( "Enhanced rectangle length is " + anEnhancedRectangle.getLength() );
    System.out.println( "Enhanced rectangle width is " + anEnhancedRectangle.getWidth() );
    System.out.println( "Enhanced rectangle area is " + anEnhancedRectangle.getArea() );
  }
}

---------------------------------------------------------------

Program Output:

---------------------------------------------------------------

Enhanced rectangle length is 40.0
Enhanced rectangle width is 30.0
Enhanced rectangle area is 1200.0

---------------------------------------------------------------

Programming Excersise:

Write a program called InheritanceProgrammingExcerise that creates 2 enhanced rectangles and displays their length, width, and area. Set the first rectangle's length to 40 and its width to 30. Set the second rectangle's length to 60 and width to 50. (code for Rectangle and Enhanced Rectangle provided in lecture).


Code:
---------------------------------------------------------------

public class EnhancedRectangleDemo
{
  public static void main( String[] args )
  {

    // Create Rectangles
    EnhancedRectangle rectangle1 = new EnhancedRectangle();
    EnhancedRectangle rectangle2 = new EnhancedRectangle();

    // Set Attributes
    rectangle1.setSides( 40, 30 );
    rectangle2.setSides( 60, 50 );

    // Display attributes and area
    System.out.println();
    System.out.println( "Enhanced rectangle 1 length is " + rectangle1.getLength() );
    System.out.println( "Enhanced rectangle 1 width is " + rectangle1.getWidth() );
    System.out.println( "Enhanced rectangle 1 area is " + rectangle1.getArea() );

    System.out.println( "Enhanced rectangle 2 length is " + rectangle2.getLength() );
    System.out.println( "Enhanced rectangle 2 width is " + rectangle2.getWidth() );
    System.out.println( "Enhanced rectangle 2 area is " + rectangle2.getArea() );

    
    } // end main
} // end class


---------------------------------------------------------------

Result:

---------------------------------------------------------------

Enhanced rectangle 1 length is 40.0
Enhanced rectangle 1 width is 30.0
Enhanced rectangle 1 area is 1200.0
Enhanced rectangle 2 length is 60.0
Enhanced rectangle 2 width is 50.0
Enhanced rectangle 2 area is 3000.0

---------------------------------------------------------------

#7B Inheritance & Class Member Visibility

- Visibility of class members - whether public, private, or protected plays important role
- Visibility of base class directly affects sub classes

Rules:
- base class members with public are inherited by subclasses, direct accessible to sub classes
- Also accessible to any classes with access to those subclasses

- Base class members with protected are inherited by subclass and direct accessible by sub class only

- base class with private are not inherited by subclasses and not directly accessible to subclasses or any other classes

- base class with unspecified visibility are only accessible by classes in same package


EX:

class Rectangle
{
  public double length;   // all classes have access
  public double widtg;    // all classes have access

  public void setSides( double l, double w )   // all classes have access
  {
    lenght = l;
    width = w;
  }
}

(public visibility = can be invoked by users of class, lengtha and width members (vars) )

extend class so we can calculate area and perimeter of rectangles:


class EnhancedRectangle extends Rectangle
{
  public double getArea()         // all classes have access
  {
    return length * width;        // subclass has irect access to attributes
    }
  public double getPerimiter()    // all classes have access
  {
    return 2 * ( length + width );
   }
}



- so users of Rectangle and EnhanceRectangle have access to all members
- earlier we learned not a recommeded practice to make data members public unless members are constants  meant to be shared with users in class
- so design not so great
- just done to illustrate public relationship

version with protected visibility:
- users of Rectangle class can't access length and width attributes by name

public class Rectangle
{
  protected double lenght;                     // subclasses have access
  protected double width;        

  public void setSides( double l, double w )   // all classes have access
  {
    lenght = l;
    width = w;
  }
}

class EnhancedRectangle extends Rectangle
{
  public double getArea()         // all classes have access
  {
    return length * width;        // subclass has irect access to attributes
    }
  public double getPerimiter()    // all classes have access
  {
    return 2 * ( length + width );
   }
}

** when a base class is :: extended :: protected values are inherited by subclass and can be directly accessed by name

protected members of base class also have protected visbiity in subclass, so users of Rectangle class cannot access values by name.


## inheritance and private visibility
- with private visibility, users of Rectangle class cannot access length and width by name
- subclasses of Rectangle cannot access them either, once private always private
- user getter mthods (get length, get width) must be used instead
- Strict encapsulation
- most favorable

public class Rectangle
{
  private double lenght;                     // only accessibly in Rectangle
  private double width;        

  public void setSides( double l, double w )   // all classes have access
  {
    lenght = l;
    width = w;
  }
}

class EnhancedRectangle extends Rectangle
{
  public double getArea()         // all classes have access
  {
    return length * width;        // subclass has irect access to attributes
    }
  public double getPerimiter()    // all classes have access
  {
    return 2 * ( length + width );
   }
}

#7C Calling Base Class Constructors

- some classes may have zero or more constructors
- if none, java will provide default (no arugs) one when subclass is created
- rules are same as any java class
- if subclass has any defined constructor, java will not auto provide one
- so far, we have not provided any constructors in this unit so java has auto provided and called them

Invoking Base Class Constructors
- when base class constructors require arguments, subclasses must take responsibility for invoking proper base class constructor and passing the appropriate args
- this must be done in the FIRST EXECUTABLE STATEMENT in the subclass construtor by using :: super :: keyword

Ex: (base class has constructor, extend class does not, constructor " = " )

public class Base
{
  private int data;

  public int getData()
  {
    return data;
  }

  public Base()
  {
    data = 0;
  }
}

EX: 

public class Derived extends Base
{
  private int subData;

  public iunt getSubData()
  {
    return subData;
  }
}


// look back at this lesson again

Programming Excersise:

Write a program called BaseClassExercise that uses the Base and Derived class code from last ex. It should initialize the Derived data member to 20 and the Base data member to 10 when a Derived object is nstantiated.

Poss solution:

public class BaseClassExercise
{
  public static void main( String [] args )
  {
    Derived d = new Derived( 10, 20 );

    System.out.println();
    System.out.println( "Base data is " + d.getData() );
    System.out.println( "Derived data is " + d.getSubData() );
  }
}



#7D Method Overriding and Preventingn Inheritence

say class BaseClass has public void display()

but class SubClass extends BaseClass also has a method public void display()
- subclass will override

Override rules:
1. Signature of overriding method must be exactly the same as signature of inherited (method name, number and type of args)
2. Visibility of overriding method cannot be more restricted than that of the inherited method.

Method overriding can be indicated in design notation 

[ Date                             ]
| -month, int                      |
| -day, int                        |
| -year, int                       |
------------------------------------
| + setDate(m: int d: int, y:int)  |
[ + getDate(): String              ]

             // \\
              | | 
[ LongDate                                ]
| -monName: String                        |
-------------------------------------------
| + LongDate( mn: String, d: int, y: int) |
[ + getDate(): String                     ]

repeating method elemnt in subclass inidcates it will be overwritten

If diagram didn't have + getDate(): String, it would indiacate no overwriting will occur, just inherits methods

Preventing method from overwritting: 
- use final in def
- public final void display()

so if subclass attempts to override it, compliateion error will occur

prevent class from being extended - also use final in class def
java compiler will see it cannot be extended, error

Progamming Exercise:
Robot



#7F Casting Objects



