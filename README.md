# 00
all: process_creation output_program simple_program

process_creation: process_creation.c
	gcc process_creation.c -o process_creation

output_program: file1.c file2.c
	gcc file1.c file2.c -o output_program

simple_program: simple_program.c
	gcc simple_program.c -o simple_program


#include <stdio.h>
#include <unistd.h>

int main() {
    pid_t pid = fork();

    if (pid == 0) {
        printf("This is the child process. PID: %d\n", getpid());
    } else if (pid > 0) {
        printf("This is the parent process. PID: %d\n", getpid());
    } else {
        printf("Fork failed!\n");
    }
    return 0;
}



#include <stdio.h>

void hello() {
    printf("Hello from file1!\n");
}



void hello();

int main() {
    hello();
    return 0;
}



#include <stdio.h>

int main() {
    printf("This is a simple program.\n");
    return 0;
}
