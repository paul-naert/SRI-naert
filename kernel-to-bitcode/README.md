# Building the Linux Kernel into LLVM Bitcode

In order to apply OCCAM tools on the kernel, we need to have a bitcode base on which we can act.
Getting that bitcode is the goal of the [built-in-parsing.py](built-in-parsing.py) program. It will read all the files included in the built-in.o archive and convert what it can into bitcode, compile and link them.
Its first argument is the folder where the bitcode should be stored, and the rest are folders which should not be translated into bitcode and instead directly linked.

I have also included a previous version of the script which would compile archives individually and link them afterwards. It did not boot when including the ext4 file system or the drivers in the bitcode, contrary to the other script.


## Necessary tools

 - clang
 - [gllvm](https://github.com/SRI-CSL/gllvm)
 - libelf-dev (in order to build the kernel)
 - libncurses-dev (optional - needed for menuconfig)
 
