# What does Python do
In the beginning, computers were programmed manually. If a programmer wanted to automate something using a computer, they had to put all kinds of switches in the right order for the program to run and work.

Luckily, we live in a day and age where everything is now digital.

## Machine code and compiled languages
Computers only understand specific instructions. *Move this data here* or *Add this value and this value together*. The programmers that used to program in instructions like those were practically wizards. They would be able to deduce what the following program does just by looking at it:

```nasm
section .data
    message db "Hello, World!", 10
    length equ $ - message

section .text
    global _start

_start:
    ; write(stdout, message, length)
    mov rax, 1          ; syscall: write
    mov rdi, 1          ; file descriptor: stdout
    mov rsi, message    ; pointer to message
    mov rdx, length     ; message length
    syscall

    ; exit(0)
    mov rax, 60         ; syscall: exit
    xor rdi, rdi        ; exit code 0
    syscall
```

## How Python is different
Python is build on layers and layers of other programming code that takes care of all the details and boring stuff. Because of that, the code that was shown above in Assembly can be written in Python like this:

```Python
print("Hello World")
```

Only one line of code is enough. This will show, or **return**, the phrase "Hello World" to the person that runs this bit of code.

That is in essence how Python works. You give it a line of code, Python:
- **interprets** the code 
- **returns** the outcome
- **moves** to the next line of code

Thus, when you give it two lines of code, it will run the first, and then the second.

```Python
print("one")
print("two")
```
Will return "one", followed by "two".
