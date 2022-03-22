# Shell Grammar In Used


## Shell Control Statement
**Conditional Execution**
- if statement
- if-else statement
- if..elif..else..fi statement (Else If ladder)
- if..then..else..if..then..fi..fi..(Nested if)
- switch statement

### if statement
**Syntax**:
```bash
1.
	if [ expression ]
	then
		statement
	fi
2.
	if [ expression ] ; then
		statement
	fi
```
- `then` is like `{` in C programming
- `fi` is like `}` in C programming


### if..then..elif..then..else..fi statement
**Syntax**:
```bash
if [ expression1 ]
then
   statement1
   statement2
   .
   .
elif [ expression2 ]
then
   statement3
   statement4
   .
   .
else
   statement5
fi
```
## Shell variables

`$#`
- argument count, (int)argc in C programming

`$1`, `$2`, `$3`
- argv[1], argv[2], argv[3] in C programming

`$@`

`$?`
