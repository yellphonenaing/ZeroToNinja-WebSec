## Install Labs Via Docker
> Web Security Labsတွေကို Docker အသုံးပြုပြီး Install လုပ်သွားမှာဖြစ်ပါတယ်။<br>

**Install Docker**
```
sudo apt install docker
sudo apt install docker.io
```

**Start Docker**
```
sudo systemctl start docker
sudo systemctl enable docker
```

**Install DVWA Labs**
```
sudo docker pull vulnerables/web-dvwa
```


**Start DVWA Labs**
```
sudo docker run -p 80:80 vulnerables/web-dvwa
```

**Install bWAPP**
```
sudo docker pull raesene/bwapp
```

**Start bWAPP**
```
sudo docker run -d -p 8008:80 raesene/bwapp
```

**Install XSS Labs**
```
sudo apt install php -y
sudo apt install git -y
cd
git clone https://github.com/yellphonenaing/xss-labs
```

**Start XSS Labs**
```
cd ~/xss-labs && php -S 127.0.0.1:8009
```
