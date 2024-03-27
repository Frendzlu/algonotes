# Naming and Stylistic Conventions in the library
## Code Styling
### Use OTBS
```cpp
void exampleFunction() {

}
```
...not Allman
```cpp
void exampleFunction()
{

}
```
### Always write braces
```cpp
if (x%2) {
    someDeclaredVariable = 12; 
} else { // 'else' placed in the same line as closing brace!
    someOtherVariable = 20;
}
```
### Always divide with spaces
```cpp
if () {}
```
### Try to use intuitive equations
```cpp
i + a*b;
(a*2 - 20)/(b++ + 11);
i + 1;
a%2;
```
### Be concise when writing array returns and conditions
```cpp
cout << arr[i] << arr[i + 1];
```
### Do not do this
This refering to == 1 and == 0 when comparing booleans or checking for truthiness
```cpp
if (geometryObject.isRectangle == 0) {}
// Do this
if (!geometryObject.isRectangle) {}
```
### Use ternary operator only when absolutely necessary
Good example
```cpp
char translateParity(int number) {
    return number%2 ? "o" : "e";
}
```

## Naming conventions
### Use camelCase for variable and function names
```cpp
void someExampleFunction() {
    int someExampleVariable = 0;
}
```
### Use PascalCase for class and struct names
```cpp
class ExampleClass {};
```
### Use descriptive (but not verbose) class, function and variable names
```cpp
// Good
double calculateCoefficient() {}
// Slightly worse
double calcCoeff() {}
// Bad
double cCoeff() {}
// Very bad
double cC() {}
```
### Pluralize array names
```cpp
int numbers[];
// not
int numberArray[];
```
## Other conventions
### Macros
We don't use macros
### Language
Use english. Only english
Do not do something like [`isPies`](https://wykop.pl/wpis/30442309/kod-pkp-jest-zlotem-function-czywybranopsa-var-isp)
### STL
Write in docs which functions are used
### C++ standard
We use C++17, as it is the newest provided on most competitions