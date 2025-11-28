Exception Handling in Java
Demonstration of try, catch, finally, throw, and throws

This project provides a simple Java example that demonstrates how exception handling works using:

try – for code that may cause an exception

catch – to handle specific exceptions

finally – to execute code regardless of exceptions

throw – to manually throw an exception

throws – to declare an exception that a method might throw

Java’s exception-handling mechanism helps separate normal logic from error-handling logic and ensures that important cleanup code is always executed.

📁 Project Structure
/src
 └── ExceptionDemo.java
README.md

📌 Features Demonstrated
1. try Block

Contains code that might produce an exception.

2. catch Block

Catches and handles the specific exception type thrown inside the try block.

3. finally Block

Runs whether an exception occurs or not.
Useful for cleanup operations like closing files, database connections, etc.

4. throw Keyword

Used to manually throw an exception based on a specific condition.

5. throws Keyword

Used in method declarations to indicate that a method might pass an exception to the caller.

📘 Example Code
public class ExceptionDemo {

    public static void main(String[] args) {
        try {
            int result = divideNumbers(10, 0);  // Will cause ArithmeticException
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());
        } finally {
            System.out.println("Finally block executed.");
        }

        try {
            validateAge(15); // Will throw custom exception
        } catch (Exception e) {
            System.out.println("Validation Error: " + e.getMessage());
        }
    }

    // Method using 'throws'
    public static int divideNumbers(int a, int b) throws ArithmeticException {
        return a / b;
    }

    // Method using 'throw'
    public static void validateAge(int age) throws Exception {
        if (age < 18) {
            throw new Exception("Age must be 18 or above!");
        }
        System.out.println("Age validated successfully.");
    }
}

▶️ How to Run

Clone or download this repository.

Open a terminal in the project folder.

Compile the Java file:

javac ExceptionDemo.java


Run the program:

java ExceptionDemo

📝 Output Example
Error: / by zero
Finally block executed.
Validation Error: Age must be 18 or above!
