java c
Question 1: Read-Write Semaphore (Max Mark: 30 / 100)
This question requires you to implement Read-Write semaphores for xv6.Two files – semaphore.h and semaphore.c are provided for you as a reference design for semaphore implementation in xv6. A structure representing a semaphore is defined in semaphore.h. There are three functions associated with the semaphore – initsema(), downsema(), and  upsema(), that  initialize,  decrement,  and  increment  a  semaphore respectively.  The code for these functions is provided in semaphore.c. Study them in conjunction with the lecture slides to make sure you understand them. You  may want to compile them with the xv6 kernel and see how it works with the user programsematest.c provided for you. In order to do so, add the function provided in  sys_sematest.c to sysfile.c and make sematest() a system call for xv6 in the usual way. Then compile xv6 with make qemu CPUS=1 and run sematest. Running xv6 on a single CPU prevents the displayed messages from being garbled.Task:    Implement  Read-Write  Semaphore  that  can  be  used  to  solve  the  Reader/Writer problem  as  discussed   in  class.   In  semaphore.h there  is  already  an  empty   struct rwsemaphore. There are also five associated function prototypes:
void initrwsema(struct rwsemaphore *rws);
int downreadsema(struct rwsemaphore *rws);
int upreadsems(struct rwsemaphore *rws);
void downwritesema(struct rwsemaphore *rws); void upwritesema(struct rwsemaphore *rws);You will need to design an appropriate struct rwsemaphore, and implement these five functions in semaphore.c. Your struct rwsemaphore should be defined using the semaphore in semaphore.c. That is, do not use the xv6 locks. Note that you do not need  to  wake  up  the  waiting  threads/processes  in  the  same  order  as  semaphores  are requested.There    is    a    function    called    sys_rwsematest() in     sys_sematest.c.    Make rwsematest() a system call like sematest() above. A user test program has been provided in rwsematest.c. It makes use of this system call. The test program conducts three tests – read lock test, write lock test, and read  write lock test.  You will need to work out from this program what the correct output of each test should be. Capture your test output and paste it into a document. Then explain why this output shows that your implementation is correct.Submission Requirement: Cleanup (remove) all the object files and executable files using the com代 写Read-Write SemaphorePython
代做程序编程语言mand make clean (in the directory where the Makefile is located). Then, in the parent directory of xv6-riscv, run the tar command to archive the whole xv6riscv directory (with its sub-directories including user, kernel, and mkfs). Name this tar file q1-.tar where  is your student ID.
The code you added/modified should be documented with appropriate comments.
Submit  both this tar file and the document showing the test  program  outputs and your explanations to Canvas.
Marking Criteria:

Question 4: Files in xv6 (Max Mark: 40 / 100)In  Unix/Linux, there  is  a system call  named  lseek() (accessed  through the standard C library) that repositions the offset of an open file for reading and writing. Look at the man page of lseek to understand more.
Task: Implement alseek() system call for xv6-riscv. This system call is a lot more restricted
than the Linux version. The function prototype is
int lseek(int fd, int offset);where fd is the file descriptor, and the file offset is set of offset bytes. Offset is always computed from the beginning of the file. It returns the resulting offset location in bytes if successful. Otherwise, it should return -1.Note that if the offset is larger than the size of the file, then the offset location will be set to the end of the file and this value  is what should  be  returned.  This  is  different from the behaviour of the lseek() in Unix/Linux.Write your own user program filetest (in a file filetest.c) to test your lseek() system call. It should take two arguments, the first one is a text file name and the second is an integer (the offset). Make sure that it test for the case where the offset is larger than the file size. Otherwise, it should read a few characters from the file and print them out to show that the offset has been set correctly.
Chapter 8 of the xv6 book contains useful information.Submission Requirements: Clean up (remove) all the object files and executable files using the command make clean (in the directory where the Makefile is located). Then, in the parent directory of xv6-riscv, run the tar command to archive the whole xv6riscv directory (with its sub-directories including user, kernel, and mkfs). Name this tar file q4-.tar where  is your student ID. Submit this file to Canvas.
The code you added/modified should be documented with appropriate comments.
Marking Criteria:






         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
