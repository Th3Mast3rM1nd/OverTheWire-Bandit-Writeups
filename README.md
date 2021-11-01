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

  ```


</details>


***level 3***

The password for the next level is stored in a file called spaces in this filename located in the home directory

<details>
  <summary> <b>View Solution </b></summary>
  
```

  ```

</details>


***level 3***

The password for the next level is stored in a file called spaces in this filename located in the home directory

<details>
  <summary> <b>View Solution </b></summary>
  
```

  ```


</details>

