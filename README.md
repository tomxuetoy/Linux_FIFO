create_FIFO
===========

to show how to create Linux FIFO

The original code is from web link:
    http://linuxprograms.wordpress.com/2008/02/15/programming-with-fifo-mkfifo-mknod/


About mknod():
    SYSCALL_DEFINE3(mknod, const char __user *, filename, int, mode, unsigned, dev)
    {
        return sys_mknodat(AT_FDCWD, filename, mode, dev);
    }

    From the web link, about "dev": 
        "If the file type is S_IFCHR or S_IFBLK then dev is checked; otherwise it is ignored. So we passed 0 as the argument."


About mode:
    S_IRUSR
      Permits the file's owner to read it.

    S_IWUSR
      Permits the file's owner to write to it.

    S_IRGRP
      Permits the file's group to read it.

    S_IWGRP
      Permits the file's group to write to it.


Notice:
    Run below command in non-vfat partition
        createFIFO_mkfifo myfifo
    
    otherwise error will occur like below:
        mkfifo: Operation not permitted
