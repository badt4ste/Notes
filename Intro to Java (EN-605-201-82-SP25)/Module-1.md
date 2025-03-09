### 1A Computing Concepts
What's a computer?
- (very basic overview slides)

### 1B Java History & Architecture
Developed by Sun Microsystems (california), aquired by Oracle in 2010. First released in 1996

Primary motivation behind dev of Java was dev a reliable language to program embedded applications, intelligent toasters, stereo equipt, etc

embedded: app where programs can be loaded upon boot or embedded in chips
C++ had reliability issues, Java is similar but less dangerous

Used to be called Oak (named by James Gosling b/c of tree outside his office). There was already a language trademarked as Oak. Java literally came from coffee

CPU executes simple program instrucitons written in machine lang, each type of computer has it's own language

Advantages of Java over others
- portability (because of special compiler)
- reliability
- distributed
- secure

### 1C Structure of Java program
a java program is a collection of constructs called classes
beginning - only single class
overall structure 

myFirstJavaProgram

public class programName
{
    .. all the program parts here
}

NOTE : braces always come in pairs
NOTE : public and class must always be lowercase
NOTE : program name is all one work no spaces. Can have underscore, letters, dollar sign
NOTE : java standard is CaptialNamingConvention

program must contain method called 'main'

public class MyFirstJavaProgram
{
    public static void main( String [] args )
    {
        System.out.printIn( "Java is the bomb!");
    }

}

run java file (compiled) simply type java programName


### 1D Compiling and Running a Java Program
1. create source file
2. compile into bytecode
3. run program

### 1E Creating a Java Source File
- New notepad/text editor
- type source code (program)
- saveAs (directory) / (must be samse name exactly as program+.java)
- compile (from command line or IDE)

### 1I Doing Basic Program Output
method - System.out.println | will print a line / this is called argument list
System.out.print("text") DOES NOT generate a line feed

Output basics:

public class OutPutDemo1
{
    public static void main ( String [] args )
    {
        int x = 10;
        System.out.println();   // Just prints linefeed
        System.out.println( "Java Rocks!" );
        System.out.print( "the value of x is ");
        System.out.println( x );    // Prints 10 in string form
    }
}
