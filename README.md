# The Monty language

Monty 0.98 is a scripting language that is first compiled into Monty byte codes (Just like Python). It relies on a unique stack, with specific instructions to manipulate it. The goal of this project is to create an interpreter for Monty ByteCodes files.

## Monty byte code files

Files containing Monty byte codes usually have the .m extension. Most of the industry uses this standard but it is not required by the specification of the language. There is not more than one instruction per line. There can be any number of spaces before or after the opcode and its argument:

```bash
 ayo  hp-HP-Pavilion-g6-Notebook-PC  ../Desktop/Monty/monty  main ◔  cat -e test/00.m

push 1$
push 2$
push 3$
pall$
$
```

Monty byte code files can contain blank lines (empty or made of spaces only, and any additional text after the opcode or its required argument is not taken into account:

```bash
julien@ubuntu:~/monty$ cat -e bytecodes/001.m
push 0 Push 0 onto the stack$
push 1 Push 1 onto the stack$
$
push 2$
  push 3$
                   pall    $
$
$
                           $
push 4$
$
    push 5    $
      push    6        $
$
pall This is the end of our program. Monty is awesome!$
julien@ubuntu:~/monty$
```

## Project Goal

Write a monty interpreter in C to run monty bytecodes, just like how python interpreter runs python codes.

## List of monty bytecodes implemented with stack doubly linked list:

> - Push: The opcode `push` pushes an element to the stack.
> - Pall: The opcode `pall` prints all the values on the stack, starting from the top of the stack.
> - Pint: The opcode `pint` prints the value at the top of the stack, followed by a new line.
> - Pop: The opcode `pop` removes the top element of the stack.
> - Swap: The opcode `swap` swaps the top two elements of the stack.
> - Add: The opcode `add` adds the top two elements of the stack.
> - Nop: The opcode `nop` doesn’t do anything.
> - Sub: The opcode `sub` subtracts the top element of the stack from the second top element of the stack.
> - Div: The opcode `div` divides the second top element of the stack by the top element of the stack.
> - Mul: The opcode `mul` multiplies the second top element of the stack with the top element of the stack.
> - Mod: The opcode mod computes the rest of the division of the second top element of the stack by the top element of the stack.
> - Pchar: The opcode `pchar` prints the char at the top of the stack, followed by a new line.
> - Pstr: The opcode `pstr` prints the string starting at the top of the stack, followed by a new line.
> - Rotl: The opcode `rotl` rotates the stack to the top.
> - Rotr: The opcode `rotr` rotates the stack to the bottom.
> - Stack: The opcode `stack` sets the format of the data to a stack (LIFO). This is the default behavior of the program.
> - Queue: The opcode `queue` sets the format of the data to a queue (FIFO).

## Usage:

```bash
./monty bytecodes.m
```

## Authors

> - [Silas Inegbe](https://github.com/silas-inegbe)
