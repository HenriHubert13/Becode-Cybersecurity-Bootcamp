Pipping_and_redirection

- Write the message "hello everyone" in a file called "test" by redirecting the output of the echo command.

`echo "hello everyone" > test.txt`

- Write the message "goodbye" in the same file "test" by redirecting the output of the echo command and without overwriting the content of "test" and check with the cat command

`echo "Goodbye" >> test.txt`

- Make the ls -la command redirect to the foo file

`ls -la > foo`

- Execute find /etc -name *conf* command and redirect errors (only errors) to a file named err.txt

`find /etc -name *conf* 2>err.txt`

- Repeat the previous exercise, this time redirecting the errors to the linux nothingness.

`find /etc -name *conf* 2>/dev/null`

- Now redirect the standard output and the error output of the find /etc -name *conf* command to two different files (std.out and std.err)

`find /etc -name *conf* 1>/dev/std.out 2>/dev/std.err`
