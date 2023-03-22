# OS_Assignment1_21K4714
Make a custom kernel with a custom HelloWorld function.

## All commands used for the assignment: 

![3 fullProcess](https://user-images.githubusercontent.com/125374283/227026198-0a66216f-75b0-4609-bdd4-12461a65d78c.JPG)

## Details about all steps

1: First we will download Kernel from kernel.org i did 4.19.272 Version [tarball] format. After it is downloaded extract the folder and in the extracted folder will make a new folder named 'hello'.

2: In that folder, Run a terminal, we'll make two files 'hello.c' (our task to run) and Makefile via terminal commands 'gedit hello.c' and gedit Makefile respectively

3: In hello.c write this code #include <linux/kernel.h> asmlinkage long sys_hello(void) { printk("Hello world\n"); return 0; }

4: In Makefile add this obj-y := hello.o

5: We have to add the system call entry into the syscall_64.tbl file which keeps the name of all the system. For doing this we will open that file by running command in terminal which will open a file

6: In the syscall_64.tbl file scroll down to line [334], in the next line put this line (which will be line 335), then save the file.

![abcacac](https://user-images.githubusercontent.com/125374283/227025222-1ba6c41e-5dcd-42b2-8f34-4e5f6fdad406.png)

7: Now we have to add the prototype of our system call in the system’s header file. In kernel folder “/include/linux/syscalls.h” we have to add the prototype of our system call function in this file.

8: In this file we just have to add our function call in the system file by simply typing in the function name in the end, save it.

![syscalls](https://user-images.githubusercontent.com/125374283/227025387-2aaccf51-ec55-4903-acb6-bfa9e4703ebc.png)

9: Open Makefile and in Extraversion put the value equal to the roll number

10: Press CTRL+F in the same file and search for "core-y", navigate to second instance and in the end of the line put " hello/"

![core - y](https://user-images.githubusercontent.com/125374283/227025483-dd330314-ec03-4e0a-8532-4aa581f280ae.png)

11: We have to create a config file for our kernel. First, we search for the current config, copy the config, typing “cp /boot/config-4.10.0-28-generic /workingdirectory”

12: We will now write the configuration file

13: We have to clean our processes in the kernel by typing “make clean -j1” , we now type “make -j1” to start building our kernel and then install modules through command "make modules_install install".

14: now we will restart ubuntu and then choose ubuntu version with our roll number

15: write "uname -r" in ubuntu to check if you have done correctly

![uname -r](https://user-images.githubusercontent.com/125374283/227026688-bb749ca0-00be-4fe5-b8d1-7f064560898a.jpg)

16: now make a c file and write the following code to check if the system call you made works

17: you can verify through writing "dmesg" in terminal

![dmesg](https://user-images.githubusercontent.com/125374283/227027211-05aa07c4-6ffc-4235-aa71-8901cb0b04e3.jpg)
