# Buffer-overflow-project

Compile your program with gcc
gcc -fno-stack-protector -z execstack -o login login.c -m32
-fno-stack-protector disables stack canaries, making it easier to exploit buffer overflows.
-z execstack allows code execution on the stack.
-m32 compile the program in 32 bit program.

