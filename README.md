# Week10Homework_UserInputAndValidation

## Simple Calculator

### Description
Your assignment is to build a calculator that takes user input and converts it into a result.  This calculator should support decimal values.  Upon starting up the application, the following message should appear:

`Enter Your Mathematical Expression Below (use a single space between each number/operator):`

The user will then enter a mathematical expression that will be converted into a result, which will then get printed to the console.  For example, I could type in `10 + 10 * 2 / 2 * 100` and expect the following output:

`Result: 1030.0.  Would you like to enter another expression? (y/n):`

If "y" is selected, the app should restart the process of asking the user to input an expression and converting their input into a result.  If "n" is selected, the following message should appear:

`Thank you for using this simple calculator!`

Be sure to keep running the application until the user terminates the program by selecting "n" for no when being asked if they want to enter another expression.

### Validation
It is possible our users might enter invalid characters, so we need to validate input prior to running our equation.  Below is a list of operators we will support for this app:

|Operator| What It Should Do|
|--------|------------------|
|   +    | Addition          |
|   -    | Subtraction      |
|   *    | Multiplication   |
|   /    | Division         |

All numbers and operators should be separated by a single space.  For example, the input below would be valid:

`10 + 10 / 6 - 2`

However, this input would not (despite it being the same equation):

`10+10/6-2`

Any expression containing one or more string values that are not numbers, single spaces, or valid operators should return the following message:

`Invalid input detected: <invalid character(s) here>.  Please try again`

The app should then inquire the user to input their mathematical expression using the opening message defined earlier in this assignment.  Repeat this process until the user inputs the correct data in the correct format. 

### Separation of Concerns
It does not make sense to throw all the app logic into Program.cs, so you should delegate functionality to a class.  I would expect the following functionality to be present in a class (each with its own method):
-	Validation of user input
-	Calculation of validated input 

Also consider if you should use a regular or static class.  Remember, a regular class requires constructors and instantiation to be used.  A static class can simply be a placeholder for your methods without any constructor or instantiation.  Which one of these makes more sense to use?  Also consider which arguments your methods will take in and which datatype they will return.


### Hints
- Your midterm introduced you to libraries, which I highly recommend you use in this homework.  I would expect you to use one when running your calculations, otherwise you will be spending a lot of time trying to figure out to manually execute a mathematical expression while adhering to the order of operations.  Remember, answers to complex problems like these are usually one google search away!  Feel free to use a Nuget package if you'd like (though I do want to stress that .NET has something built in that should help you execute expressions).

- Don't forget that I asked you to ensure that numbers and operators are separated by a space.  The reason for this is that the string datatype has a built-in method that allows you to **split** a delimited string into substrings using a defined delimiter (your empty space).  This will return collection of substrings as an array.  From there, you could check that each element is either a valid number or operator.  

- There are two parts of this app that will need to run on repeat:
  - When a user submits the wrong input.
  - When a user is asked if they wish to enter another expression and they select "y" for yes.

  You will need to make sure these parts of your app repeat as long as they need to.  What concept in our class have we learned that can help you acomplish this?  
