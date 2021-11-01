# OverTheWire-Bandit-Writeups
Writeups for https://overthewire.org/wargames/bandit/

***Level 1*** :

The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

<details>
  <summary> <b>View Solution </b></summary>
  
```
cat readme
  ```
<img width="366" alt="Screen Shot 2021-11-01 at 15 54 14" src="https://user-images.githubusercontent.com/92652606/139691756-3eef686e-abbd-4f9a-be43-0067095b0d43.png">

</details>

***level 2*** :

The password for the next level is stored in a file called - located in the home directory

<details>
  <summary> <b>View Solution </b></summary>
  
```
find . -type f -name "-" -exec cat "{}" ";"
  ```
<img width="537" alt="Screen Shot 2021-11-01 at 15 57 43" src="https://user-images.githubusercontent.com/92652606/139692344-b17e7be8-6b73-4007-b9a9-f73c1ec76603.png">

</details>
***level 3***

The password for the next level is stored in a file called spaces in this filename located in the home directory

<details>
  <summary> <b>View Solution </b></summary>
  
```
cat spaces\ in\ this\ filename 
  ```
<img width="415" alt="Screen Shot 2021-11-01 at 16 00 29" src="https://user-images.githubusercontent.com/92652606/139692886-ad408387-3921-4bc3-b333-d338425e5752.png">


</details>


***level 4***

The password for the next level is stored in a hidden file in the inhere directory.

<details>
  <summary> <b>View Solution </b></summary>
  
```
cat .hidden
  ```
<img width="509" alt="Screen Shot 2021-11-01 at 16 02 08" src="https://user-images.githubusercontent.com/92652606/139693115-777c1b56-8665-4e56-bab9-451d1a7787e4.png">

</details>


***level 5***

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command

<details>
  <summary> <b>View Solution </b></summary>
  
```
find . -type f -exec file "{}" ";"
  cat ./-file07
  ```
<img width="527" alt="Screen Shot 2021-11-01 at 16 12 31" src="https://user-images.githubusercontent.com/92652606/139694648-c53add4b-ab7f-4cfd-a724-c7d24fc60c3e.png">


</details>


***level 6***

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable
<details>
  <summary> <b>View Solution </b></summary>
  
```
find ./inhere/ -type f -size 1033c -exec cat "{}" ";"
  ```
<img width="641" alt="Screen Shot 2021-11-01 at 16 17 08" src="https://user-images.githubusercontent.com/92652606/139695369-4319180f-1293-46f2-a337-6b5fdf6fd491.png">
</details>


***level 7***

The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size

<details>
  <summary> <b>View Solution </b></summary>
  
```
find / -type f -user bandit7 -a -group bandit6 -size 33c -exec cat "{}" ";" 2> /dev/null
  ```
<img width="882" alt="Screen Shot 2021-11-01 at 16 19 37" src="https://user-images.githubusercontent.com/92652606/139695720-8f463b73-c188-4811-bd7d-485800f9bb14.png">
  
</details>


***level 8***

The password for the next level is stored in the file data.txt next to the word millionth
<details>
  <summary> <b>View Solution </b></summary>
  
```
cat data.txt | egrep -i "millionth" | awk '{print $NF}'
  ```
<img width="655" alt="Screen Shot 2021-11-01 at 16 23 50" src="https://user-images.githubusercontent.com/92652606/139696404-7eabf2ef-9a76-4c74-844a-20f63bdc4ca6.png">


</details>


***level 9***

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

<details>
  <summary> <b>View Solution </b></summary>
  
```
cat data.txt |  sort | uniq -u
  ```
<img width="443" alt="Screen Shot 2021-11-01 at 16 29 32" src="https://user-images.githubusercontent.com/92652606/139697312-a9a079ef-905f-481f-8492-239e3d1d642a.png">


</details>


***level 10***

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

<details>
  <summary> <b>View Solution </b></summary>
  
```
strings  data.txt | egrep -ai "==+"
  ```

<img width="480" alt="Screen Shot 2021-11-01 at 16 34 30" src="https://user-images.githubusercontent.com/92652606/139698015-ab1d2146-9c55-4835-9590-b886dbb31bcc.png">

</details>


***level 11***

The password for the next level is stored in the file data.txt, which contains base64 encoded data 

<details>
  <summary> <b>View Solution </b></summary>
  
```
cat data.txt | base64 -d
  ```
<img width="593" alt="Screen Shot 2021-11-01 at 16 35 57" src="https://user-images.githubusercontent.com/92652606/139698241-ce222826-f9be-4867-8830-ddf3ddab3ef3.png">


</details>


***level 12***

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

<details>
  <summary> <b>View Solution </b></summary>
  
```
cat data.txt | tr a-zA-Z n-za-mN-ZA-M
  ```

<img width="480" alt="Screen Shot 2021-11-01 at 16 38 28" src="https://user-images.githubusercontent.com/92652606/139698593-71bd2951-2e48-4467-b55f-84ce01636deb.png">

</details>

***level 13***

The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

<details>
  <summary> <b>View Solution </b></summary>
  
```
i used first xxd -r to revert the file data.txt to the original format .
and after that i start using file command line to check which file type is the file .
and decompressing the file depending on the 
type most time i had to use mv to change the file name like data to data.gz ( commands i used are tar xf , gunzip , bunzip und xxd ) 
  ```

<img width="1419" alt="Screen Shot 2021-11-01 at 16 48 17" src="https://user-images.githubusercontent.com/92652606/139700115-f217c749-2138-46ba-a8dd-21a01110c8bb.png">
  
<img width="400" alt="Screen Shot 2021-11-01 at 16 49 00" src="https://user-images.githubusercontent.com/92652606/139700261-d5a905e4-a916-4b87-98cf-5110f7902e0e.png">

</details>

***level 14***

The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

<details>
  <summary> <b>View Solution </b></summary>
  
```
ssh -i sshkey.private bandit14@localhost
cat /etc/bandit_pass/bandit14
  ```
<img width="766" alt="Screen Shot 2021-11-01 at 16 54 56" src="https://user-images.githubusercontent.com/92652606/139701197-e26ebc6b-7531-4617-80c7-7cc598154dcf.png">

</details>

***level 15***

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

<details>
  <summary> <b>View Solution </b></summary>
  
```
telnet localhost  30000
nc 127.0.0.1 30000
  ```
<img width="400" alt="Screen Shot 2021-11-01 at 17 01 26" src="https://user-images.githubusercontent.com/92652606/139702229-a19f9d33-c519-4e72-9571-6caa0f6ee918.png">

</details>

***level 16***

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

<details>
  <summary> <b>View Solution </b></summary>
  
```
openssl s_client -host 127.0.0.1 -port 30001
  ```
<img width="681" alt="Screen Shot 2021-11-01 at 17 04 59" src="https://user-images.githubusercontent.com/92652606/139702755-37cd0dcb-7f2c-4a1b-8a85-a73c9c47397b.png">

</details>

***level 17***

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it

<details>
  <summary> <b>View Solution </b></summary>
  
```
nmap -vv -p31000-32000 localhost | awk  '{print $1}'  | grep -i [0-9] | sed 's/\/tcp//g'
openssl s_client -host 127.0.0.1 -port 31790
  ```
<img width="615" alt="Screen Shot 2021-11-01 at 17 32 23" src="https://user-images.githubusercontent.com/92652606/139706658-2fc042e5-f859-4c22-9ee2-c321b12963d5.png">

</details>

***level 18***

There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

<details>
  <summary> <b>View Solution </b></summary>
  
```
diff -u passwords.new passwords.old
  ```

<img width="524" alt="Screen Shot 2021-11-01 at 17 37 05" src="https://user-images.githubusercontent.com/92652606/139707409-27ac6a74-7cf4-40fd-90e2-77d1ed539c7d.png">

</details>

***level 19**
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.
<details>
  <summary> <b>View Solution </b></summary>
  
```
ssh bandit18@bandit.labs.overthewire.org -p 2220  cat readme
  ```
<img width="739" alt="Screen Shot 2021-11-01 at 17 40 03" src="https://user-images.githubusercontent.com/92652606/139707723-556f6cf0-da74-4950-96f0-9fa38e426841.png">

</details>

***level 20***

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

<details>
  <summary> <b>View Solution </b></summary>
  
```
./bandit20-do cat /etc/bandit_pass/bandit20
  ```
<img width="542" alt="Screen Shot 2021-11-01 at 17 43 33" src="https://user-images.githubusercontent.com/92652606/139708188-d02d360a-392e-4edc-a67e-76e38e851f23.png">

</details>

***level 21***

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
<details>
  <summary> <b>View Solution </b></summary>
  
```
./suconnect 2345

nc -lvp 2345
  ```
<img width="352" alt="Screen Shot 2021-11-01 at 17 47 53" src="https://user-images.githubusercontent.com/92652606/139708758-f10ae29f-4de3-4b42-b433-8832c478578a.png">

<img width="479" alt="Screen Shot 2021-11-01 at 17 48 02" src="https://user-images.githubusercontent.com/92652606/139708770-ef700c7d-8aff-44df-834e-b6a0800d19cf.png">
</details>
  
***level 22***

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

<details>
  <summary> <b>View Solution </b></summary>

<img width="1009" alt="Screen Shot 2021-11-01 at 17 56 00" src="https://user-images.githubusercontent.com/92652606/139709846-4717930b-9662-4e5b-a5fa-00c2ebac52d5.png">

</details>
  
***level 23***

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

<details>
  <summary> <b>View Solution </b></summary>
  
<img width="683" alt="Screen Shot 2021-11-01 at 18 00 22" src="https://user-images.githubusercontent.com/92652606/139710421-ca301bc0-85b1-48c1-8da9-7b92ba3ca7cc.png">

</details>


***level 24***
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
<details>
  <summary> <b>View Solution </b></summary>
  
```
#!/bin/bash 
  
cat /etc/bandit_pass/bandit24 > /tmp/newfile.txt 

  ```
<img width="514" alt="Screen Shot 2021-11-01 at 18 14 34" src="https://user-images.githubusercontent.com/92652606/139712116-a7494ad8-2d6f-4cb6-9a3a-1c3d8a81a3ad.png">

</details>

***level 25***

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
<details>
  <summary> <b>View Solution </b></summary>
  
```
 

  ```


</details>
