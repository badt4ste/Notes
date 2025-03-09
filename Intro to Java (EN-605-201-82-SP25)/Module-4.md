Module 4
# 4A - Defining Class Methods

A java method is a set of code that performs a well-defined f
2 types:
    class
    instance

Class method:
so far all were single method called main
    main directs overall flow of execution in programs
    static keyword == class methods
    class methods aka static methods
    Java can have any number of class methods in addition to main

defining a class method:
access_mode static return_type method_name( arg1, arg2, ...) {

}
    specify access mode: public, private or protected
        for now, just use public
    static
    type of value (if any returned)
        can be primitive or non-primitive types (arrays, objects)
        No value - void
    name of method (Java variable rules, camelcase)
    Args: () unless required arguments, then specify type of args

Method Ex1:
    public static voi displayMessage() {
        system.out.println( "Hello World!" );
    }    
 // note: no args, just displays message which doesn't return value

 Method Ex2:
    public static void performSum( int x, int y){
        int sum = x + y;
    }

## Invoking a Method
    
    public class InvokeMethodDemo {
        public static void main( String [] args) {
            displayMessage();
            displayMessage();
        }
        public static void displayMessage() {
            System.out.println( "Hello World!");
        }

    }

^^^ invokes displayMessage > skips to that method, executes, and then returns to main
# 4B Scope of Method's Args and Variables
A method's arguments and any variables defined inside the method are local to the method
    variables can only be referenced from within the method
    several methods can use identical variable names but they will be different items

# 4C Passing Args to Methods
2 important things to remember:
    1: number and type of each arguments method expects in definition
    2: pass by value for primitive arg types 

Ex1:
public class PassingArgumentsDemo {
    public static void main ( String [] args ) {
        displayArgs ( 10, 20F );
    }

    public static oid displayArgs( int x, float y) {
        system.out.println( "First arg is " + x);
        system.out.println( "Second arg is " + y);
    }
}

Ex2:
public class ArgumentPassingDemo2 {
    public static void main( String [] args ) {
        int x = 5;

        System.out.println();
        changeValue( x );

        System.out.println( "x = " + x);
    }
    public static void changeValue( int x) {
        System.out.println( "Value passed = " + x);
        x = 99;
    }

}

# 4D Returning Values From Class Methods
must specify return type in definition

public static int addThem( int xm int y ) {
    int sum = x + y;

    return sum;
}

must also include return statement

Example: 
public class ReturningValueDemo1 {
    public static void main( String [] args ) {
        int x = 5;
        int y = 7;
        int z = addThem( x, y );

        System.out.println("z = " + z );
    }
    public static int addThem( int x, int y ) {
        int sum = x + y;
        return sum;
    }
}

Example 2 (simplify prior example):
public class ReturningValuesDemo2 {
    public static void main( String [] args ) {
        int x = 5;
        int y = 7;
    System.out.println( "Sum = " + addThem( x, y ) );

    }
    public static int addThem( int x, int y ) {
        return x + y;
    }
}

# 4E
Be aware of Method arg types

make sure arguments expected vs actually used
 if they dont match, won't compile
 if Java can safely convert it may *

 EX: divide method declares int x, int y
  method "divide" takes int and can't return floats

  public class TypeCheckDemo2 {
    public static void main( String [] args ) {
        float i = 46.7F;
        float j = 3.1F;

        System.out.println( "result = " divide( i, j ) );
    }
    public static float divide ( int x, int y ) {
        return (float)x/y;
    }
  }

  # 4F
  Built in math class methods

  sqrt( arg ) - calcs and returns squre root of arg, ends up as double
  pow( arg 1, arg 2) - calculates arg1 raised to power of arg2
  random() - generates psuedo-random number in range 0.0 to 1.0. return is type double

  may need to cast to change output for other things

  EX: Pow
  
  public class PowerMethodDemo {

    public static void main ( String [] args ) {
        int j = 2;
        int i = 3;

        System.out.println( "result = " + Math.pow( j, i ));
    }
  }

  = 8.0

  one way to change double to int:

  add (int) before Math.pow
   this 'casts' answer to int

  another would be assign 3rd variable as int y;
  print int y (no decimal then)
  

  // Math is built in class, have to specify class and method (Math.pow)
