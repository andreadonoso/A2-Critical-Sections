# A2-Critical-Sections
To gain a fuller understanding of critical sections in the Linux kernel by programming them.

# Assignment
Re-implement your module from the device driver assignment as two separate kernel modules - one for an input device, and one for an output device, using shared memory between the two modules to manage the communication.

Don’t overthink the shared memory in the kernel – Use Google or ChatGPT to find out about sharing memory between kernel modules. Hint: It’s as simple as an extern declaration in the right place.

What you will need to put some work into is properly guarding the critical sections.  Investigate the functionality in linux/mutex.h.  Derek Molloy’s documentation can help you here as well. Or, again, ChatGPT!

# Required printk Output
Report via printk the following program states:

Waiting on the lock
Acquiring the lock
Releasing the lock
Writing X bytes
Reading X bytes
Buffer is empty
Buffer is full
Not enough space left in the buffer, dropping the rest.
Failed to initialize device
Failed to read
Failed to write


# Testing
A simple set of shell scripts should test a continuous read/write loop:

#!/bin/bash

        while true; do
        echo "test" > /dev/lkm_pa2-in
        done
        Copy
        
#!/bin/bash

        while true; do
        cat /dev/lkm_pa2-out
        done
        Copy
        
        
# Submitting (zip 3 files)
1. Input device
2. Output device
3. Makefile

