## 練習:pass
```
pass.c

#include"stdio.h"
#include"stdlib.h"

void printTheKey(){
  /*
   *
   * print the key
   *
   */
}

int main(){
  setvbuf(stdout, 0, 2, 0);
  setvbuf(stdin, 0, 2, 0);
  int token = 1234;
  char key[16];

  printf("Billy left his key in the locked room.\n");
  printf("However, he forgot the token of the room.\n");
  printf("Do you know what's the key?");

  read(0, key, 40);

  if((int)token == 0xdeadbeef){
    printf("Door open. OwO\n");
    printTheKey();
    system("cat /home/ctf/flag");
  }else{
    printf("Cannot open door. QwQ\n");
  }

  return 0;
}
```
```
gdb-peda$ file pass
Reading symbols from pass...(no debugging symbols found)...done.

```
```
gdb-peda$ disas main
Dump of assembler code for function main:
   0x000000000040080e <+0>:	push   rbp
   0x000000000040080f <+1>:	mov    rbp,rsp
   0x0000000000400812 <+4>:	sub    rsp,0x20
   0x0000000000400816 <+8>:	mov    rax,QWORD PTR [rip+0x200843]        # 0x601060 <stdout@@GLIBC_2.2.5>
   0x000000000040081d <+15>:	mov    ecx,0x0
   0x0000000000400822 <+20>:	mov    edx,0x2
   0x0000000000400827 <+25>:	mov    esi,0x0
   0x000000000040082c <+30>:	mov    rdi,rax
   0x000000000040082f <+33>:	call   0x4005b0 <setvbuf@plt>
   0x0000000000400834 <+38>:	mov    rax,QWOR
```
```

```
