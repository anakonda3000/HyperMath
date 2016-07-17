# HyperMath
c# library for mathematical calculations with arbitrary size and precision.

## Description
HyperMath is a package that provides the data type "EDecimal" (Extended Decimal)
which enables you to calculate with floating numbers with theoretically no limits.
It's like "calculating with strings".
You can use a precision of 10 decimal places, 1000000 or much more.

## Installation
Just copy the required files into your project directory.

## Requirements
None

## Limitations
The only limits are your memory and CPU power.
Please be aware that calculations with EDecimal types are not as fast as
standard type calculations.

## Content
* EDecimal: floating point calculation class (data type "EDecimal")

## Usage

### Decimal separator
The decimal separator is set to the default language decimal separator.
The german version of Visual Studio uses "," as separator, the english
version uses ".".

If you want to manually set the decimal separator use
```
EDecimal.DecimalSeparator = '.';
```
to set it to what ever you need.


### Precision
The default precision for some operations is set to "no limit" (e.g.: Add, Sub, Mul).
But because "Div()", "Pow()", "Root()",... can produce periodic or "endless" results
(e.g.: 1/3) the precision limit is set to 50 by default.
Use 
```
EDecimal.Precision = 50;
```
to set it to what ever you need.


### Conversion Methods
* String ToString()
* int ToInt32()
* long ToInt64()
* double ToDouble()
* decimal ToDecimal()


### Calculation methods
```
EDecimal EDecimal(string/int/double/decimal Number)
```
Create a new instance of EDecimal.
Also "compact format" is allowed (e.g.: -1.23E-12).
Note: "." and "," is used as comma.


```
EDecimal Negate()
```
Negate the number.

```
EDecimal CommaLeft([int n])
```
Move the comma to the left by n places.

```
EDecimal CommaRight([int n])
```
Move the comma to the right by n places.



```
EDecimal Add(EDecimal b, [int precision])
```
Add "b".

```
EDecimal Sub(EDecimal b, [int precision])
```
Subtract "b".

```
EDecimal Mul(EDecimal b, [int precision])
```
Multiply with "b".

```
EDecimal Div(EDecimal b, [int precision])
```
Divide by "b".

```
EDecimal IDiv(EDecimal b)
```
Divide by "b", without any decimal places (integer division).

```
EDecimal Abs()
```
Get the potitive number.

```
int Sign()
```
Get the sign (-1 if <0, 0 if 0, 1 if >0).



```
EDecimal Min(EDecimal b, [int precision])
```
Get the minimum.

```
EDecimal Max(EDecimal b, [int precision])
```
Get the maximum.



```
EDecimal Pow(EDecimal b, [int precision])
```
Get the "b"th power.
Note: currently only integer power implemented.

```
EDecimal Root(EDecimal b, [int precision])
```
Get the "b"th root.
Note: currently only integer root implemented.

```
EDecimal Sqrt(EDecimal b, [int precision])
```
Get the sqare root.

```
int CompareTo(EDecimal b, [int precision])
```
Compare the number to "b" (1 if >b, 0 if =b, -1 if <b).
Note: currently only integer root implemented.



```
EDecimal Exp([int precision])
```
Get the exponential of the number (e^x).

```
EDecimal Log([int precision])
```
Get the natural logarithm.

```
EDecimal Log(EDecimal Base, [int precision])
```
Get the logarithm using base "Base".

```
EDecimal Log10([int precision])
```
Get the logarithm of base 10.



```
EDecimal Sin([int precision])
```
Get the sinus.

```
EDecimal Cos([int precision])
```
Get the cosinus.

```
EDecimal Tan([int precision])
```
Get the tangens.

```
EDecimal Cot([int precision])
```
Get the cotangens.



```
EDecimal Trunc([int precision = 0])
```
Get the integer part or truncate using a precision.

```
EDecimal Frac([int precision])
```
Get the fractional part.

```
EDecimal Floor()
```
Get the floor of the number.

```
EDecimal Ceiling()
```
Get the ceiling of the number.

```
EDecimal Round([int precision = 0])
```
Round the number.



```
EDecimal Faculty()
```
Get the faculty of the number (non fractional positive numbers only).


### Flags
```
bool IsNegative
```
Get / set the "negative"-flag.


### Check functions
```
bool IsOdd()
```
True if number is odd.
Note: only integer numbers allowed.

```
bool IsEven()
```
True if number is even.
Note: only integer numbers allowed.

```
bool IsInteger()
```
True if number does not have decimal places.

```
bool IsFloat()
```
True if number has decimal places.

```
bool IsZero()
```
True if number is 0.

```
bool IsOne()
```
True if number is 1.


### Properties
```
EDecimal EDecimal.Zero
```
Just EDecimal("0"). 

```
EDecimal EDecimal.One
```
Just EDecimal("1"). 

```
EDecimal EDecimal.Two
```
Just EDecimal("2"). 

```
EDecimal EDecimal.Ten
```
Just EDecimal("10"). 

```
int EDecimal.Precision
```
The maximum precision for operations like "Div()", "Pow()", "Root()", "Exp()",... .

```
char EDecimal.DecimalSeparator
```
Get / set the decimal separator. It's set to the language default by default.


### Operators
Of course you can calculate with EDecimal like double using
```
+, -, *, /, %, <, >, <=, >=, == and != 
```
which uses EDecimal.Precision as maximum precision.

## Speed
Because all calculations are done "by foot" calculating with EDecimal is quite slow.
So EDecimal is not intended to do many calculations in a short amount of time.


## Todo
* General power (e.g.: Pow(2, 1.2))
* General root (e.g.: Root(5, 3.7))


## Notes
Since I'm quite new to c# and I don't have much time there is certainly much
potential for optimizations.
So please let me know if there are additional optimizations which can be implemented.



## History

### Version 0.2.0
* Much faster array based implementation

### Version 0.1.0
* String based implementation


## Author
Volker Heiselmayer

## Licence
MIT

### Additional keywords
c# csharp math mathematics EDecimal extended decimal claculate strings arbitrary precision
rechnen mit strings