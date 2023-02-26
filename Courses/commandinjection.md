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
| * | It can be use as 'all' or  auto complete |
```
ls -lah /tmp
```
>ls = command to be executed, -lah = Options, /tmp = Argument

# Command Substitution

```
echo $(pwd)
echo `whoami`
```

# Base64 Encoding/Decoding

```
echo "yellphonenaing" | base64
Output => eWVsbHBob25lbmFpbmcK

echo "eWVsbHBob25lbmFpbmcK" | base64 -d
Output => yellphonenaing
```
