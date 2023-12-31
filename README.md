\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
\| ASM BASICS CHEAT SHEET \|
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

1\. Data Declaration: ; Declare a variable variable_name data_type
initial_value

Example: message db \'Hello, World!\', 0 ; Declare a null-terminated
string

2\. Data Types: db - Define Byte (8 bits) dw - Define Word (16 bits)
dd - Define Doubleword (32 bits) dq - Define Quadword (64 bits)

Example: count dw 10 ; Declare a 16-bit word variable

3\. Reading Input: mov eax, 3 ; System call number for \"read\" mov ebx,
0 ; File descriptor 0: stdin mov ecx, buffer ; Buffer to store input mov
edx, length ; Maximum number of bytes to read int 0x80 ; Call the kernel

Example: mov eax, 3 ; Read input from stdin mov ebx, 0 mov ecx,
input_buffer mov edx, 256 int 0x80

4\. Writing Output: mov eax, 4 ; System call number for \"write\" mov
ebx, 1 ; File descriptor 1: stdout mov ecx, message ; Message to write
mov edx, length ; Length of the message int 0x80 ; Call the kernel

Example: mov eax, 4 ; Write message to stdout mov ebx, 1 mov ecx,
message mov edx, length int 0x80

5\. Loops: mov ecx, loop_count ; Loop counter initial value

loop_start: ; Loop body instructions go here

loop loop_start ; Decrement counter and jump if not zero

Example: mov ecx, 10 ; Loop from 10 to 1

loop_start: ; Loop body instructions go here

loop loop_start

6\. Conditional Statements: cmp operand1, operand2 ; Compare two
operands jmp label_name ; Unconditional jump je label_name ; Jump if
equal (ZF = 1) jne label_name ; Jump if not equal (ZF = 0) jg label_name
; Jump if greater (ZF = 0, SF = OF) jge label_name ; Jump if greater or
equal (SF = OF) jl label_name ; Jump if less (SF ≠ OF) jle label_name ;
Jump if less or equal (ZF = 1, SF ≠ OF)

Example: cmp eax, ebx ; Compare the values of eax and ebx je equal_label
; Jump to equal_label if they are equal jne not_equal_label

7\. Exit Program: mov eax, 1 ; System call number for \"exit\" xor ebx,
ebx ; Exit code 0 int 0x80 ; Call the kernel

Example: mov eax, 1 ; Exit the program with exit code 0 xor ebx, ebx int
0x80

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
