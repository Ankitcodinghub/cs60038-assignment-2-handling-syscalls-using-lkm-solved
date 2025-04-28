# cs60038-assignment-2-handling-syscalls-using-lkm-solved
**TO GET THIS SOLUTION VISIT:** [CS60038 Assignment 2-Handling Syscalls using LKM Solved](https://www.ankitcodinghub.com/product/cs60038-assignment-2-solved-2/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;117973&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS60038 Assignment 2-Handling Syscalls using LKM Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
(Handling Syscalls using LKM)

Command Description

PB2_SET_CAPACITY This command initializes the LKM with the maximum priority-queue capacity. LKM is already initialized for the current process, this command resets the LKM and reinitializes again. It expects a pointer to a 32-bit integer. The value must be in the range between 1 and 100 (both inclusive). Invalid value or inaccessible pointer causes an error and sets the error number to EINVAL. On success, it returns 0.

No other operation can be performed (including read or write) before performing this system call. Every other system call on the LKM returns an error (-1) with code EACCES.

PB2_INSERT_INT This command inserts an integer into the priority-queue. It takes a pointer to an integer as the input value. Invalid value causes an error in LKM and sets error number to EINVAL. On success, it returns 0.

This command is followed by the PB2_INSERT_PRIO command at the userspace process.

PB2_INSERT_PRIO This command inserts the priority into the priority-queue. It takes a pointer to an integer as the input value. Invalid value causes an error in LKM and sets error number to EINVAL. On success, this command returns 0.

If the priority-queue is full, it returns an error (-1) with code EACCES.

PB2_GET_INFO This command returns the information about the priority-queue. PB2_GET_INFO command expects a pointer to a structure object of type struct obj_info as the value.

On success, LKM returns 0 and fills the various fields of the pointer passed by the process. On error, LKM sets appropriate error no and returns -1.

PB2_GET_MIN This extracts the element with minimum priority from the priority-queue (Element having lowest integer value as priority, should be considered as minimum priority element). This function returns 0 on success and -1 on error.

PB2_GET_MAX This extracts the element with maximum priority from the priority-queue. This function returns 0 on success and -1 on error.

The definition of ioctl commands are as follows:

#define PB2_SET_CAPACITY

#define PB2_INSERT_INT

#define PB2_INSERT_PRIO

#define PB2_GET_INFO

#define PB2_GET_MIN

#define PB2_GET_MAX

_IOW(0x10, 0x31, int32_t*)

_IOW(0x10, 0x32, int32_t*)

_IOW(0x10, 0x33, int32_t*)

_IOR(0x10, 0x34, int32_t*)

_IOR(0x10, 0x35, int32_t*)

_IOR(0x10, 0x36, int32_t*)

The definition of structures are as follows:

struct obj_info {

int32_t prio_que_size; // current number of elements in priority-queue int32_t capacity; // maximum capacity of priority-queue

};

A userspace process interacts with the LKM in the following manner only.

2. Userspace process calls the ioctl system call with command PB2_SET_CAPACITY and appropriate value to set the maximum capacity of the priority-queue in the kernel.

3. Insert elements using the ioctl system call with commands PB2_INSERT_INT and

PB2_INSERT_PRIO as many times as you want. However, there is no bound on the number of times the user program can call this insert operation. LKM verifies the arguments in the system call and inserts the input into the priority-queue. In case the priority-queue is full,

an appropriate error is returned.

4. To perform read/ extract data from priority-queue, the userspace program uses ioctl system call with command PB2_GET_MIN or PB2_GET_MAX. The system call returns 0 in case of successful execution and populates the result, whose pointer is passed while making the call.

5. When all the operations are done, the userspace process closes the file and LKM releases all the resources allocated for the process.

6. In between the userspace program can call the ioctl system call with command PB2_GET_INFO to retrieve information and the current state of the priority-queue.

LKM should be able to handle concurrency and separate data from multiple processes. Also, no userspace program should be able to open the file more than once simultaneously. However, the userspace process should be able to reset the LKM (for the said process) by reopening the file.

Submission Details:

– Students have to submit the LKM Code and the corresponding Makefile.

– Compress these files into a zip file and name the zip file: ASGN2_&lt;ROLL_NO&gt;.zip.
