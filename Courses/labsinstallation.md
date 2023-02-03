#Install Labs Via Docker
> Web Security Labsတွေကို Docker အသုံးပြုပြီး Install လုပ်သွားမှာဖြစ်ပါတယ်။<br>

**Install Docker**
```
sudo apt install docker
sudo apt install docker.io
```
<br>
**Start Docker**
```
sudo systemctl start docker
sudo systemctl enable docker
```
<br>
**Install DVWA Labs**
```
docker pull vulnerables/web-dvwa
```
<br>
**Start DVWA Labs**
```
docker run -p 80:80 vulnerables/web-dvwa
```
<br>
**Install bWAPP**
```
docker pull raesene/bwapp
```
<br>
**Start bWAPP**
```
docker run -d -p 8008:80 raesene/bwapp
```
