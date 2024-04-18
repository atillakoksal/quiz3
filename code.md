```
section .text
        global _start

_start:

        mov edx, [num1]
        sub edx, 1
        mov ecx, edx
        mov ebx, [num1]

        multiply:

        mov eax, edx
        sub edx, 1
        mul ebx

        dec ecx
        cmp ecx, 1
        jnb multiply

        mov [result], eax
        mov eax, 1
        int 0x80


segment .bss
        result  resb 1
        num2    resb 1

section .data
        num1 DD 5


```
