# Engineering_calculator_C program
Engineering Calculator – A complete C console application that evaluates mathematical expressions with support for trigonometric, logarithmic, exponential functions, factorial, random numbers, previous-result recall, persistent history, and an ASCII function plotter. Designed as a first-year Electrical Engineering programming project.
markdown
markdown
# Engineering Calculator (C) 

A console-based engineering calculator written in C that supports arithmetic expressions, trigonometric and logarithmic functions, factorial, degree/radian modes, ASCII graph plotting, and history logging.

## Features

- Arithmetic operations with correct operator precedence: `+`, `-`, `*`, `/`, `^`
- Right-associative exponentiation (`2^3^2` = `512`)
- Parentheses for grouping
- Factorial (`!`) in both prefix (`!5`) and postfix (`5!`) forms
- Mathematical functions:
  - Trigonometric: `sin`, `cos`, `tan`, `cot`
  - Inverse trigonometric: `asin`, `acos`, `atan`, `acot`
  - Logarithmic: `ln`, `log`
  - Exponential: `exp`
  - Square root: `sqrt`
  - Absolute value: `abs`
  - Random integer: `rand(n)` (0 to n-1)
- Mathematical constants: `p` / `PI` (π) and `e` / `E` (Euler's number)
- Previous result access via `&`
- Angle mode: radian or degree (affects trig functions)
- Simple ASCII graph plotting for functions of `x`
- History stored in text files (`History.txt` and `GraphHistory.txt`)
- Clear history functionality

## Requirements

- C compiler (GCC recommended)
- Standard C library
- Math library (`libm`)

## Compilation

Compile with GCC and link the math library:

```bash
gcc -o calculator calculator.c -lm
If you are using a different compiler, ensure that the math library is linked.

Usage
Run the executable:

bash
./calculator
The main menu will appear:

text
=== Engineering Calculator ===
0. Help
1. Calculation
2. Show History
3. Clear History
4. Graph (ASCII plot)
5. Show Graph History
e. Exit
Menu Options
0. Help – displays a quick usage guide.

1. Calculation – perform a mathematical calculation.

2. Show History – view past calculations from History.txt.

3. Clear History – delete both history files.

4. Graph (ASCII plot) – plot a function of x in the terminal.

5. Show Graph History – view past graph commands from GraphHistory.txt.

e. Exit – quit the program.

Detailed Instructions
1. Calculation
Select option 1. First, you will be prompted to choose the angle mode:

text
Angle mode: 0 = Radian (default), 1 = Degree
Enter 0 for radians or 1 for degrees. Then enter your mathematical expression, for example:

text
Enter expression (e.g. 3+sin(45)^2): 
After pressing Enter, the result is displayed and saved to history.

2. Show History
Displays the content of History.txt (if it exists). Each line contains an expression followed by its result.

3. Clear History
Removes History.txt and GraphHistory.txt from the current directory.

4. Graph (ASCII plot)
Select option 4. You will be asked to enter a function of x:

text
Enter function (e.g. sin(x) or x^2 + 3): 
Then provide the range for x:

text
x min: 
x max: 
The program evaluates the function at 41 equally spaced points between x_min and x_max, and draws an ASCII graph with a height of 20 rows. The x-axis labels are aligned with the columns.

Note: When x is replaced by a negative number, it is wrapped in parentheses to preserve correct precedence (e.g., (-5)^2 = 25).

5. Show Graph History
Displays the content of GraphHistory.txt, which stores the function and range of each graph plotted.

Supported Operators and Functions
Operators
Operator	Description	Example
+	Addition	2 + 3 → 5
-	Subtraction	5 - 2 → 3
*	Multiplication	4 * 2 → 8
/	Division	10 / 4 → 2.5
^	Exponentiation (right-associative)	2^3^2 → 512
!	Factorial (prefix or postfix)	!5 → 120, 5! → 120
Functions
Function	Description
sin(x)	Sine
cos(x)	Cosine
tan(x)	Tangent
cot(x)	Cotangent
asin(x)	Arcsine
acos(x)	Arccosine
atan(x)	Arctangent
acot(x)	Arccotangent
sqrt(x)	Square root
ln(x)	Natural logarithm
log(x)	Base-10 logarithm
exp(x)	Exponential (e^x)
abs(x)	Absolute value
rand(n)	Random integer between 0 and n-1
Constants
Symbol	Value
p or PI	π ≈ 3.14159...
e or E	e ≈ 2.71828...
Previous Result
Use & to refer to the result of the last calculation. Example:

text
Enter expression: 2 + 3
Result = 5.0000000000

Enter expression: & * 10
Result = 50.0000000000
Angle Mode
Angle mode affects trigonometric functions and their inverses:

Radian mode: sin(pi) = 0, asin(1) = pi/2

Degree mode: sin(180) = 0, asin(1) = 90

Graph Plotting Details
The graph uses a fixed width of 41 columns for the function values.

The y-axis is scaled to fit the minimum and maximum of the evaluated function.

If the function has zero range (constant), the range is extended to 1 unit for display.

The x-axis labels are printed every 5 columns, aligned correctly.

History Files
History.txt – stores each calculation expression and its result.

GraphHistory.txt – stores the function and x-range of each graph plotted.

These files are created in the same directory as the executable. They can be viewed using the menu options or any text editor.

Examples
Arithmetic
text
3 + 4 * 2
= 11

(3 + 4) * 2
= 14

10 / 3
= 3.3333333333
Trigonometric (in degree mode)
text
sin(30) + cos(60)
= 1.0000000000
Factorial
text
!6
= 720

6!
= 720
Graph
text
Function: x^2 - 4
x min: -5
x max: 5
Produces a parabola with vertex at (0, -4).

Limitations
No support for complex numbers.

The maximum length of an input expression is 1000 characters.

The graph has a fixed resolution (41 points horizontally, 20 rows vertically).

The random function rand(n) uses the standard C rand() and is seeded once per program execution.

Inverse trigonometric functions are defined only for their valid domains.

License
This project is provided as-is for educational purposes. You are free to use, modify, and distribute it.

Contributing
Contributions are welcome. Feel free to open issues or submit pull requests.
