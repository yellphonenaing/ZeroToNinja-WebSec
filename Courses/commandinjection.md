## 1. Command Injection Attack

![](https://i.ytimg.com/vi/UBWMLFbjPBc/maxresdefault.jpg)
>We will use DVWA Labs To Learn Bruteforce Attacks

# Linux Command syntax
| Character | Action |
|--|--|
| ; | And |
| && | And |
| \|\| | Or |
| \| | Share Output To Second Command |

```
ls -lah /tmp
```
>ls = command to be executed, -lah = Options, /tmp = Argument

# Command Substitution

```
echo $(pwd)
echo `whoami`
```
