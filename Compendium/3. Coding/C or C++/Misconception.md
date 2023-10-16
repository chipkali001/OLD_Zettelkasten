# 
In C you have to first 
during defining say wheter number is int/string/double/float by 
then during printing and scanning tell what you are print/takinging is int/string/double by %d/f/c

```
#include <stdio.h>  
int main() {     
	int abv = 42;     
	printf("The value of number is: %d\n", abv);     
	return 0; }`
```

with **cout** you needn’t specify wheter it’s int/string/double

> [!Attention] Always remember variable in C has two steps
> 1. <span style="background:#d4b106">specify it’s int/float/char/…</span>
> 2. ==set some value to it either in program/input/…==


int main() { 
	<span style="background:#d4b106">float a,b,c,d</span>;
		==a=3.5;
		b=4.6;
		c=5.3;
		d=9.5;==
		return 0; }

The '%' symbol is commonly used in programming languages as a format specifier or placeholder. It serves several important purposes:

1. **Format Specifier:** `%` is used to indicate that what follows should be interpreted as a placeholder for some value, and that value should be formatted or substituted into the final output. For example, `%d` is a format specifier for integers, `%f` for floating-point numbers, `%s` for strings, and so on.
    
2. **Type Matching:** `%` ensures that the provided value matches the expected data type. For instance, if you use `%d`, the programming language knows to expect an integer value to replace it, and it will perform appropriate type conversions if necessary.

`""` are used in functions like `printf` and `scanf` to enclose format strings. These format strings provide instructions to these functions on how to format or interpret the data being printed or read
1. **Format Specifiers:** Inside the format string, you include format specifiers like `%d`, `%s`, `%f`, etc.,
~~scanf(%d,&i)~~   scanf(“%d”, &i)
2. **Separation from Variables**
3. **String Literals:** The double quotation marks indicate that what's inside them is a string literal


# why do we start with int main() {
1.  **Parentheses:** The parentheses `()` are used to enclose any arguments that `main` may accept. By convention, `main` takes two arguments: `int argc` and `char* argv[]`.
example we do same stuff in function protype 
```
int add(int a, int b); 
int main() { 
	int result = add(3, 5); 
	printf("Result: %d\n", result); 
	return 0;
int add(int a, int b) { return a + b;
```
2. **Braces `{}`**:
    
    - The braces in `int main() { ... }` define the body or block of code that belongs to the `main` function. Everything between the opening `{` and closing `}` is the actual code that will be executed when your program runs.
    - These braces create a scope for the code within them. This is crucial for defining the boundaries of the `main` function's code. Variables declared within the `main` function are local to this scope and are not accessible outside of it.
    - The braces also help in organizing and grouping statements together. It allows you to specify multiple statements to be executed sequentially within the function.

### Use 1
Certainly! Here's an example of how you can use `argc` and `argv` in a C or C++ program to work with command-line arguments:
```
#include <stdio.h>

int main(int argc, char* argv[]) {
    // Check if there are at least two arguments (the program name counts as one)
    if (argc < 3) {
        printf("Usage: %s <first_name> <last_name>\n", argv[0]);
        return 1; // Return an error code (non-zero) to indicate improper usage
    }

    // Print the program's name (argv[0]) and the provided first and last names
    printf("Hello, %s %s!\n", argv[1], argv[2]);

    return 0; // Return 0 to indicate successful execution
}

```
In this example, the program takes two command-line arguments: `first_name` and `last_name`. Here's how you would use it when running the program from the command line:
```
`./program_name Alice Johnson`
```

- `./program_name` is the name of the program you're running.
- `Alice` and `Johnson` are the command-line arguments you're passing to the program.

Here's what the program does:
1. It first checks if there are at least three arguments (including the program name itself). If not, it prints a usage message and returns an error code (`1`) to indicate that the program was used incorrectly.
2. If there are enough arguments, it uses `argv[1]` to access the first name and `argv[2]` to access the last name provided as command-line arguments.
3. It then prints a greeting message using the provided names.

So, when you run the program as shown above, it would print:

```
`Hello, Alice Johnson!`
```
This is just a basic example to illustrate how `argc` and `argv` are used to work with command-line arguments. You can adapt this concept to handle more complex scenarios and additional arguments as needed in your programs.

### Use 2 - **Simple Argument Display**
```cpp
#include <iostream>

int main(int argc, char* argv[]) {
    std::cout << "Number of arguments: " << argc << std::endl;

    for (int i = 0; i < argc; ++i) {
        std::cout << "Argument " << i << ": " << argv[i] << std::endl;
    }

    return 0;
}
```
When you run this program with command-line arguments like this:
```shell
./my_program arg1 arg2 arg3
```
It will display:
```
Number of arguments: 4
Argument 0: ./my_program
Argument 1: arg1
Argument 2: arg2
Argument 3: arg3
```
### **Use 3: Sum of Numbers**
```cpp
#include <iostream>
#include <cstdlib>
int main(int argc, char* argv[]) {
    if (argc < 3) {
        std::cerr << "Usage: " << argv[0] << " num1 num2" << std::endl;
        return 1;
    }
    int num1 = std::atoi(argv[1]);
    int num2 = std::atoi(argv[2]);
    int sum = num1 + num2;
    std::cout << "Sum of " << num1 << " and " << num2 << " is: " << sum << std::endl;
    return 0;
}
```
This program calculates the sum of two numbers provided as command-line arguments. For example:
```shell
./sum_program 5 7
```
It will display:
```
Sum of 5 and 7 is: 12
```

### **Use4: Print lines line by line of a text = File Processing**
```cpp
#include <iostream>
#include <fstream>

int main(int argc, char* argv[]) {
    if (argc != 2) {
        std::cerr << "Usage: " << argv[0] << " filename" << std::endl;
        return 1;
    }

    std::ifstream file(argv[1]);
    if (!file) {
        std::cerr << "Error opening file: " << argv[1] << std::endl;
        return 1;
    }
    std::string line;
    while (std::getline(file, line)) {
        std::cout << line << std::endl;
    }

    return 0;
}
```
This program reads and displays the contents of a file specified as a command-line argument. For example:
```shell
./read_file_program input.txt
```
It will display the contents of the `input.txt` file.
> [!Attention] 
> 1. (argc != 2) ==if number of files is not equal to 2==
checks if you have first your **==own program==** and then ==**txt file==** you willl be printing by program.
> 2. (!file) ==if file you are supposed to read text from doesn’t exist==
> 3. std::cerr SAME WORK as std::cout BUT DOESN’T WAIT FOR BUFFER or other stuff INSTATNLY ALARMS YOU OF ERROR
> 4. `++i`: This is the loop's update statement. It increments the value of `i` by 1 in each iteration. It's a way to move from one argument to the next.
> 	- for (int i = 0; i < argc; i += 7) {
> 	- for (int i = 0; i < argc; ++i)
> 5. getline(alpha, beta) - get line from alpha.txt & appoint line you read to beta 
> 6. The atoi() function **converts a character string to an integer value**. 

# std::
It seems like you've started a code snippet with "std::". In C++, "std::" is a prefix that is commonly used when working with objects and functions from the C++ Standard Library. The "std" stands for "standard," and it is the namespace where most of the standard C++ library elements are defined.

# cin >> & cout <<


# getline`
`getline` knows which lines it has read by maintaining an internal position marker within the input stream (in this case, the `std::ifstream` object, such as `FileA`). Here's how it works:
1. **Initialization:** When you first open the input stream (e.g., a file) and call `getline` for the first time, the internal position marker is typically at the beginning of the stream.
2. **Reading a Line:** When you call `getline`, it reads characters from the current position in the stream until it encounters a newline character (`'\n'`) or reaches the end of the stream. It then stores the characters read (the line) in the provided variable (e.g., `line` in `getline(FileA, line)`).
3. **Advancing the Marker:** After reading the line, `getline` advances the internal position marker within the stream to the character immediately after the newline character that ended the line. This prepares the stream for the next call to `getline`.
4. **Repeating the Process:** The next time you call `getline`, it starts reading characters from the current position (after the previous line) and continues until it reaches the next newline character or the end of the stream. This process repeats for each line in the stream until there are no more lines.
```
#include <iostream>
#include <fstream>
#include <string>

int main() {
    std::ifstream FileA("data.txt");
    if (FileA.is_open()) {
        std::string line;
        // Read the first line from the file and store it in line.
        getline(FileA, line);
        // Print the first line.
        std::cout << "First line: " << line << std::endl;
        // Read the same line from the file again and overwrite the content of line.
        getline(FileA, line);
        // Print the same line again.
        std::cout << "Second line: " << line << std::endl;
        FileA.close();
    } else {
        std::cerr << "Error opening the file." << std::endl;
    }
    return 0;
}
```
> [!Error] so instead of using while loop. if you were to just paste getline(FileA, line); getline(FileA, line): twice what it'll do. waht if you were to run them in two different programs
In this example, if "data.txt" contains the lines "Line 1" and "Line 2," running this code would result in both lines being printed, but both lines would be the same because you read the first line twice consecutively.
If you were to run these two `getline` calls in two different programs independently, they would behave independently and not affect each other. Each program would read from the file independently and not be aware of the other program's actions.


# What is command line argument
Command-line arguments are values that you can pass to a program when you run it from the command line or terminal. These arguments provide additional information or input to the program, allowing you to customize its behavior without modifying the source code.

Here are the key points about command-line arguments:
1. **Providing Input:** Command-line arguments are a way to provide input to a program. They allow you to send information to the program when you start it.
2. **Strings:** Command-line arguments are usually provided as strings. This means you can pass text, numbers, file paths, or any other string-compatible data to a program.
3. **Accessing Arguments:** In many programming languages, command-line arguments are accessible within the program through a special variable or function. In C and C++, they are often accessed through `argc` (argument count) and `argv` (argument vector) parameters in the `main` function. In Python, you can access them using the `sys.argv` list from the `sys` module.
4. **Customization:** Command-line arguments allow users to customize a program's behavior without having to change the program's source code. For example, you can pass a filename as an argument to a text editor to open a specific file.
5. **Use Cases:** They are commonly used for tasks such as specifying input files, setting configuration options, enabling debugging modes, and controlling program flow.

Here's an example of how you might use command-line arguments when running a program from the command line:
```
`$ ./my_program -input file.txt -output output.txt -verbose 7.2
```
In this example, the program `my_program` is run with three command-line arguments: `-input`, `file.txt`, `-output`, `output.txt`, and `-verbose`. 
The program can then parse these arguments and use them to determine what it should do.
> [!Example] 
> 1. `argv[0]`=./my_program  gives you the first argument (which is typically the name of the program itself)
> 2. `argv[1]`= input file.txt
> 3. `argv[2]`=output
> 4. `argv[3]`=output.txt
> 5. `argv[4]`=verbose
> 6. `argv[5]`=7.2

Overall, command-line arguments are a powerful and flexible way to interact with programs and provide them with input or configuration information without the need for user interaction within the program itself.

# # include < -- stream>
- `iostream` combines both input and output streams BOTH (istream & ostream)
- `istream` is for input operations. ==Console Input==
- `ostream` is for output operations. ==Console Output==
- `fstream` combines file input and output. BOTH (ifstream & ofstream)
- `ifstream` is for file input. ==Input File==
- `ofstream` is for file output. ==Output File==
