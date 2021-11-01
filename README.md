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

