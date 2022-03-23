# Shell Grammar In Used


## Shell Control Statement
**Conditional Execution**
- if statement
- if-else statement
- if..elif..else..fi statement (Else If ladder)
- if..then..else..if..then..fi..fi..(Nested if)
- case...esac statement

### if statement
>**Syntax**:
>```bash
>	if [ expression ]
>	then
>		statement
>	fi
>```
>```bash
>	if [ expression ] ; then
>		statement
>	fi
>```
- `then` is like `{` in C programming
- `fi` is like `}` in C programming


### if..then..elif..then..else..fi statement
>**Syntax**:
>```bash
>if [ expression1 ]
>then
>   statement1
>   statement2
>   .
>   .
>elif [ expression2 ]
>then
>   statement3
>   statement4
>   .
>   .
>else
>   statement5
>fi
>```
### case...esac statement

>**Syntax:**
>```bash
>case word in
>   pattern1)
>      Statement(s) to be executed if pattern1 matches
>      ;;
>   pattern2)
>      Statement(s) to be executed if pattern2 matches
>      ;;
>   pattern3)
>      Statement(s) to be executed if pattern3 matches
>      ;;
>   *)
>     Default condition to be executed
>     ;;
>esac
>```
>>https://www.tutorialspoint.com/unix/case-esac-statement.htm#:~:text=if...elif%20statements.-,Syntax,-The%20basic%20syntax

## Shell variables

`$#`
- argument count, (int)argc in C programming

`$1`, `$2`, `$3`
- argv[1], argv[2], argv[3] in C programming

`$@`

`$?`

`$IFS` - Internal Field Separator

Example:
- ifs.sh
```bash
#!/bin/bash

oldIFS=$IFS
echo $1
IFS=":"
echo $1
```
- command-line
```bash
bash-3.2$ sh ifs.sh '::hello,:world!::' | cat -e
::hello,:world!::$
  hello, world! $
```

## Misc or Yet
variable-slicing: `${varname:start:size}`

Example:
```bash
> var="/abc/123/abc"
> echo ${var:0:1} | cat -e
> /$
```
POSIX variable-slicing method: `${var%${var#?}}`

Example:
```bash
> var=/abc/123/abc/
> echo ${var#?} | cat -e
> abc/123/abc/$
> echo ${var%abc} | cat -e
> /abc/123/abc/$
> echo ${var%abc/} | cat -e
> /abc/123/$
> echo ${var%${var#?}}
> /$
```