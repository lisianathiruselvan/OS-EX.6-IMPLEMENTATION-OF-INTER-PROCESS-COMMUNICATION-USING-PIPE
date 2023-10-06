# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

AIM:

write C programs to illustrate IPC using pipes mechanisms

ALGORITHM:

1. IPC using pipes

2. Create a child process usingfork()

3. Create a simple pipe with C, we make use of the pipe() systemcall

4. Create a simple pipe with C, we make use of the pipe() systemcall

5. Close the read end of parent process using close() and perform writeoperation

6. Close the write end of child process and performreading

7. Display thetext.
PROGRAM:
```
#include <stdio.h>

int main()

{

int fd[2],child; char a[10];

printf("\n Enter the string:");

scanf("%s",a);

pipe(fd);

child=fork();

if(!child)

{

close(fd[0]);

write(fd[1],a,5); wait(0);

}

else

{

close(fd[1]);

read(fd[0],a,5); printf("The string received from pipe is: %s",a);

}

return 0;

}
```
OUTPUT:

![270084867-9c9a59a5-12e1-46bc-a71f-91a4bd16d5b0](https://github.com/lisianathiruselvan/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/119389971/dd082884-6189-4dd5-b295-af6814f0e1ea)


RESULT:

Thus, IPC using pipes mechanisms is illustrated using c program successfully
