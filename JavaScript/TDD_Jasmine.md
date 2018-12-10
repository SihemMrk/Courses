Test Driven Development
========================


**TDD** (Test Driven Development) or French test-driven development is a development method for which testing is an essential element. In such a way that it is possible to write the tests even before writing the code.

We start from the initial functional specifications (ie: write a function accepting 2 parameters and returning the result of the addition) we determine the tests (if we pass the parameters 2 and 2 the function must return 4 .... ect ect) then the tests are written via test libraries.

There are test libraries in all programming languages ​​and for JS there we will focus on [Jasmine:] (https://jasmine.github.io/)

Jasmine determines a number of functions that are unique to her, and you have to look at the documentation to understand it, and that's the completeness of what's out there.

A test or an assertion represents the smallest possible unit, it makes it possible to verify that a variable is correctly defined or that it contains the good value or that a function returns the good result for example.

A spec groups together a set of tests (or assertions).

A set of tests (or suits) allows to group them by tested functionality.


From the moment the suits are defined, we will need a "test runner" to execute all the tests and to lay out the results in order to be easily interpreted by a human. FullStack uses the "test runner": [testem:] (https://github.com/testem/testem)

To work, testem needs a configuration file (testem.json) at the root of the working folder, once this configuration is defined (see the files available in TestFirst-Part-1) just open the console , to position yourself in the working folder and launch the command "testem". There (without going into details), testem provides a url to run the tests; then just c / c the url in a browser to see the result.


In the browser the test library will present the results of the different "specs" with:
*the number of "specs" executed
*the number of errors returned (failures)
The goal of the "game" obviously being to manage to execute a maximum of specs and to have no error.


It is interesting to have this kind of test in place to ensure the smooth running of a program throughout one's life without the need to manually test the different functions developed. If we write the tests beforehand or as the program progresses, we make sure that everything is consistent and in the future when we have to go back on a function to modify the behavior we can quickly identify if a problem occurs without jeopardizing the entire program, all to prevent regressions appear.