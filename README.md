Monty
Desciption
Monty 0.98 is a scripting language that is first compiled into Monty byte codes (Just like Python). It relies on a unique stack, with specific instructions to manipulate it. The goal of this project is to create an interpreter for Monty ByteCodes files.

Installation
To use monty you must first access the console and clone the repository with the following command:
git clone https://github.com/Doouh/monty.git
Once you have the cloned repository, you must access the folder and compile all the files inside it with the following command:
cd monty
gcc -Wall -Werror -Wextra -pedantic *.c -o monty
Now you can use monty passing the path of a file with Monty byte code as an argument to the generated executable:
monty file_path

In the Examples section you can see some usage examples
File Index
File name	Description
additionalFunctions_0	- freestack: Receive a stack per parameter and delete it.
- _isdigit: It receives a character by parameters and returns 1 or 0 if it is a number or not.
functions_0	- push: Receives a stack and a number per parameter and adds this as a new node to the stack.
- pall: It receives a stack per parameter and prints all the values it has stored.
- pint: Receive a stack per parameter and print the value of the first node.
- nop: It receives a stack per parameter and does nothing with it.
- swap: Receive a stack per parameter and swap the first two nodes between them.
functions_1	- pop: Receive one stack per parameter and remove the first node.
- add: Receives a stack per parameter adds the values of the first two nodes and removes them, and saves a new node with the sum.
- sub: Receives a stack per parameter subtracts the values of the first two nodes and removes them, and saves a new node with the subtraction.
- division: Receives a stack per parameter divides the values of the first two nodes and removes them, and saves a new node with division.
- mul: Receives a stack per parameter multiplies the values of the first two nodes and removes them, and saves a new node with the multiplication.
functions_2	- mod: Receives a stack per parameter calculates the modulus between the values of the first two nodes and removes them, and saves a new node with the result.
- pchar: Receive a stack per parameter, convert the value of the first node into char and print it.
- pstr: Receive a stack per parameter, convert the value of each node into character and print it.
main	- main: It's our main function, it receives a file per parameter and starts reading it line by line, for each one of them it verifies by means of the is_opcode function if it is one of the preset options.
- parse: It receives a string per parameter and removes tabs, line breaks and spaces from it, to later check if it is a valid option.
- is_opcode: It receives a stack per parameter and a string, uses the parse function to obtain only valid values from among the string and checks if they are in the list of preset options, if so, calls the respective function according to the chosen option and it passes to this the stack by parameter.
- check_push: Check if an element passed by parameter is of the necessary format to be saved in the stack, if so, do the push.
monty	This file is the header of our entire program, it contains the prototypes of all the functions described in this index and the structure used to call the functions.
Examples
Some examples of using monty and its console output.
Example #1	Example #2	Example #3
~/monty$ cat -e bytecodes/00.m
push 1$
push 2$
push 3$
pall$
~/monty$ ./monty bytecodes/00.m
3
2
1









~/monty$ cat bytecodes/07.m
push 1
push 2
push 3
pall
pop
pall
pop
pall
pop
pall
~/monty$ ./monty bytecodes/07.m
3
2
1
2
1
1	~/monty$ cat bytecodes/09.m
push 1
push 2
push 3
pall
swap
pall
~/monty$ ./monty bytecodes/09.m
3
2
1
2
3
1




Authors
Jeremih Kuria
