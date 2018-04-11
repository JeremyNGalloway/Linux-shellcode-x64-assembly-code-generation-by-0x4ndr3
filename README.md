Linux-shellcode-x64-assembly-code-generation-by-0x4ndr3
https://www.exploit-db.com/exploits/44445/

 Features:
   - Linux shellcode x64 assembly code generation
   - stack based (smaller payload size)
   - execve based
   - supports long commands (meaning bigger than an x64 register - 64 bits)
   - supports long parameters (meaning bigger than an x64 register - 64 bits)
   - one command only (execve will alter the current memory proc and when it exits there's no continuation)
   - supports command with up to 8 parameters

 Instructions
   - requires full path to the command
   - only one command is supported due to execve transforming the current process into a new one, loosing all previous context (any other instructions that would have been executed)
   - after having the x64 generated assembly code:
       - copy paste it into a file (in a Linux environment) - example.nasm
       - execute:
           nasm -felf64 example.nasm -o example.o && ld example.o -o example

 Author: Andre Lima @0x4ndr3
   https://pentesterslife.blog
