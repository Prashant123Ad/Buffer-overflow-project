# Buffer Overflow Vulnerability Project

This project demonstrates a buffer overflow vulnerability in a C program. It includes a proof-of-concept exploit using `gdb` to bypass authentication and discusses mitigation techniques like stack canaries and ASLR.

## Features

- Vulnerable C program utilizing `gets()` function
- Exploitation to achieve unauthorized access
- Discussion on defense mechanisms

## Prerequisites

- **Operating System**: Kali Linux (or any Linux distribution with `gcc` and `gdb` installed)
- **Compiler**: `gcc`
- **Debugger**: `gdb`

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/Prashant123Ad/Buffer-overflow-project.git
   cd buffer-overflow-project
   ```

2. Compile the vulnerable C program:
   ```bash
   gcc -fno-stack-protector -z execstack login.c -o login
   ```

3. Disable ASLR (Address Space Layout Randomization) for testing:
   ```bash
   echo 0 | sudo tee /proc/sys/kernel/randomize_va_space
   ```

4. Run the program:
   ```bash
   ./login
   ```

## Exploitation Steps

1. Open the program in `gdb`:
   ```bash
   gdb ./login
   ```

2. Overwrite the return address.

## Defense Techniques

- **Stack Canaries**: Enable during compilation with `-fstack-protector`.
- **ASLR**: Re-enable ASLR after testing using:
  ```bash
  echo 2 | sudo tee /proc/sys/kernel/randomize_va_space
  ```
- **Secure Functions**: Replace `gets()` with `fgets()` or other safe alternatives.



## References

- [Buffer Overflow Explained](https://owasp.org/www-community/attacks/Buffer_Overflow)
- [GDB Tutorial](https://sourceware.org/gdb/current/onlinedocs/)

---

### Author
Prashant Adhikari  

Feel free to raise an issue if you encounter any problems or have suggestions for improvement.
