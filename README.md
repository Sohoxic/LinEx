# Kernel-Module
## Explanation for the above code: 

Kernel modules must have at least two functions: a “start” (initialization) function called init_module() which is called when the module is insmoded into the kernel, and an “end” (cleanup) function called cleanup_module() which is called just before it is rmmoded. Actually, things have changed starting with kernel 2.3.13. You can now use whatever name you like for the start and end functions of a module. In fact, the new method is the preferred method. However, many people still use init_module() and cleanup_module() for their start and end functions. In this code we have used hello_start() as init function and hello_end() as cleanup function.
Another thing that you might have noticed is that instead of printf() function we have used printk(). This is because module will not print anything on the console but it will log the message in /var/log/kern.log. Hence it is used to debug kernel modules. Moreover, there are eight possible loglevel strings, defined in the header , that are required while using printk(). We have list them in order of decreasing severity:

- KERN_EMERG: Used for emergency messages, usually those that precede a crash.
- KERN_ALERT: A situation requiring immediate action.
- KERN_CRIT: Critical conditions, often related to serious hardware or software failures.
- KERN_ERR: Used to report error conditions; device drivers often use KERN_ERR to report hardware difficulties.
- KERN_WARNING: Warnings about problematic situations that do not, in themselves, create serious problems with the system.
- KERN_NOTICE: Situations that are normal, but still worthy of note. A number of security-related conditions are reported at this level.
- KERN_INFO: Informational messages. Many drivers print information about the hardware they find at startup time at this level.
- KERN_DEBUG: Used for debugging messages.

> We have used KERN_INFO to print the message.
