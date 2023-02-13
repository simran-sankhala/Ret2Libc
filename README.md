# What is Ret2libc?

A ret2libc (return to libc, or return to the C library) attack is one in which the attacker does not require any shellcode to take control of a target, vulnerable process. So attackers use this technique a lot.

# A bit about libc 

Every time you write a C program, you use one or the other of the inbuilt functions, like `printf`, `scanf`, `puts` etc. Have you wondered where the definitions of these functions lie? All the standard C functions have been compiled into a single file, named the standard C library or the `libc`. A libc is native to the system that you are working on and is independent of the binary (compiled program). You can use the `ldd` command to find out which `libc` is being used by an application.

```sh
$ ldd ./ret2libc 
  linux-gate.so.1 (0xf7fc7000)
  libc.so.6 => /lib/i386-linux-gnu/libc.so.6 (0xf7d73000)
  /lib/ld-linux.so.2 (0xf7fc9000)
  ```

## Diagram

![](https://2603957456-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-LFEMnER3fywgFHoroYn%2F-MXwAmlrjE8Ejl_0OQQX%2F-MY1FO9lURZfx9fTrAf0%2Fimage.png?alt=media&token=39659182-e3ff-4d34-a031-c7091567890a)
