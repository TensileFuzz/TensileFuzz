# TensileFuzz

***TensileFuzz: Facilitating Seed Input Generation in Fuzzing via String Theory***

## Dependencies

TensileFuzz invokes CVC4 (version 1.7) as smt-solver so you should install CVC4 first. It is available at https://github.com/CVC4/CVC4

## Description

* `probe:`  A single step seed analyzer
* `tf:` TensileFuzz 
* `qemu-x86_64:` Code emulator
* `libhook.so:` Preload library for hooking some library calls
* `run-shm:` Bash file for running qemu

## Basic Usage

Refer to the usage of AFL. Run TensileFuzz together with AFL -S mode.

```bash
./AFL -S slave -i <inputdir> -o <outputdir> -f <filename1.postfix> -- <binary> @@
./tf -i <inputdir> -o <outputdir> -f <filename2.postfix> -- ./run-shm <binary> @@
```

Or you can also analyze one seed with probe. It generates interesting seeds based on input.

```
./probe -i <inputdir> -o <outputdir> -f <filename.postfix> -- ./run-shm <binary> @@
```

## Image

Here is an image with TensileFuzz installed. 

https://drive.google.com/open?id=1qKEUNF78TVALv8FSOt8wL6Aih16ecjqq
