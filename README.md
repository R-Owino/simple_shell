## Simple Shell

Simple UNIX command interpreter.

## Allowed functions and system calls
- access (man 2 access)
- chdir (man 2 chdir)
- close (man 2 close)
- closedir (man 3 closedir)
- execve (man 2 execve)
- exit (man 3 exit)
- _exit (man 2 _exit)
- fflush (man 3 fflush)
- fork (man 2 fork)
- free (man 3 free)
- getcwd (man 3 getcwd)
- getline (man 3 getline)
- getpid (man 2 getpid)
- isatty (man 3 isatty)
- kill (man 2 kill)
- malloc (man 3 malloc)
- open (man 2 open)
- opendir (man 3 opendir)
- perror (man 3 perror)
- read (man 2 read)
- readdir (man 3 readdir)
- signal (man 2 signal)
- stat (__xstat) (man 2 stat)
- lstat (__lxstat) (man 2 lstat)
- fstat (__fxstat) (man 2 fstat)
- strtok (man 3 strtok)
- wait (man 2 wait)
- waitpid (man 2 waitpid)
- wait3 (man 2 wait3)
- wait4 (man 2 wait4)
- write (man 2 write)

## Compilation

The shell will be compiled this way:

``` gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh ```


## Testing 

In interactive mode, the shell should work like this:

```
$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$
```

And in non-interactive mode, it should work like this:

```
$ echo "/bin/ls" | ./hsh
hsh main.c shell.c test_ls_2
$
$ cat test_ls_2
/bin/ls
/bin/ls
$
$ cat test_ls_2 | ./hsh
hsh main.c shell.c test_ls_2
hsh main.c shell.c test_ls_2
$
```

Output:
- Unless specified otherwise, the program must have the exact same output as sh as well as the same exact error output. The only difference is when an error is printed, the name of the prigram must be equivalent to the argv[0]. Example:
	- Error with sh:
	```
	$ echo "qwerty" | /bin/sh
	/bin/sh: 1: qwerty: not found
	$ echo "qwerty" | /bin/../bin/sh
	/bin/../bin/sh: 1: qwerty: not found
	$
	```

	- Same error with hsh:
	```
	$ echo "qwerty" | ./hsh
	./hsh: 1: qwerty: not found
	$ echo "qwerty" | ./././hsh
	./././hsh: 1: qwerty: not found
	$
	```
