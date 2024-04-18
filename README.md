# Name: SREEKUMAR S
# Reg. no: 212223240157
# Linux-IPC-Shared-memory
Ex06-Linux IPC-Shared-memory

# AIM:
To Write a C program that illustrates two processes communicating using shared memory.

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online Linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - Shared Memory

### Step 3:

Execute the C Program for the desired output. 

# PROGRAM:

## Write a C program that illustrates two shared memory-processing processes.

```
#include <stdio.h>
#include <sys/ipc.h>
#include <sys/shm.h>

int main()
{
	key_t key = ftok("shmfile", 65);

	int shmid = shmget(key, 1024, 0666 | IPC_CREAT);
      printf("Shared memory id = %d \n",shmid);
	char* str = (char*)shmat(shmid, (void*)0, 0);
	
    printf("Write Data : ");
	fgets(str, 1024, stdin);

	printf("Data written in memory: %s\n", str);

	shmdt(str);

	return 0;
}
```



## OUTPUT
![Screenshot 2024-04-18 090152](https://github.com/guru14789/Linux-IPC-Shared-memory/assets/151705853/a8c254eb-e58e-4b80-b069-64db66595212)
![Screenshot 2024-04-18 090203](https://github.com/guru14789/Linux-IPC-Shared-memory/assets/151705853/d90e8c96-5f1f-423d-abd6-2519269cb34f)





# RESULT:
The program is executed successfully.
