kilo.c -o kilo

We have added a few things to the compilation command:

$(CC) is a variable that make expands to cc by default.
-Wall stands for “all Warnings”, and gets the compiler to warn you when it sees code in your program that might not technically be wrong, but is considered bad or questionable usage of the C language, like using variables before initializing them.
-Wextra and -pedantic turn on even more warnings. For each step in this tutorial, if your program compiles, it shouldn’t produce any warnings except for “unused variable” warnings in some cases. If you get any other warnings, check to make sure your code exactly matches the code in that step.
-std=c99 specifies the exact version of the C language standard we’re using, which is C99. C99 allows us to declare variables anywhere within a function, whereas ANSI C requires all variables to be declared at the top of a function or block.

// char c = '\0';
// if (read(STDIN_FILENO, &c, 1) == -1 && errno != EAGAIN) die("read"); // errno and EAGAIN come from <errno.h>.
// if (iscntrl(c)) { // comes from <ctype.h> - iscntrl() tests whether a character is a control character
// printf("%d\r\n", c); // Control characters are nonprintable characters that we don’t want to print to the screen
// } else {
// printf("%d ('%c')\r\n", c, c);
// }
// if (c == CTRL_KEY('q')) break;
