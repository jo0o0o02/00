# 00
all: process_creation output_program simple_program

process_creation: process_creation.c
	gcc process_creation.c -o process_creation

output_program: file1.c file2.c
	gcc file1.c file2.c -o output_program

simple_program: simple_program.c
	gcc simple_program.c -o simple_program
