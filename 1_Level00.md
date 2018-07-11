# Problem
  * About
  
    This level requires you to find a Set User ID program that will run as the "flag00” account.
    You could also find this by carefully looking in top level directories in / for suspicious looking directories.
    Aternatively, look at the find man page.
    
    To access this level, log in as level00 with the password of level00.

  * Source code
  
    There is no source code available for this level
    
# Explanation
* Firstly, to access this level you need to log in to system with user 'level00' and password 'level00'
(next levels will be familiar)  
* Here you need to find file, which is set to run as the "flag00" account.
Clearly, we need executable file, which runs as "flag00" account.

# Solution
* Using `find` command:
```bash
level00@nebula:~$ find / -executalbe -user flag00 2> /dev/null
/bin/.../flag00
/home/flag00
/rofs/bin/.../flag00
/rofs/home/flag00
```
* Run `/bin/.../flag00` and follow direction
```Shell
level00@nebula:~$ /bin/.../flag00
Congrats, now run getflag to get your flag!
flag00@nebula:~$ getflag
You have successfully executed getflag on a target account
flag00@nebula:~$ 
```
**Congratulation! You passed this level.**
# Note
* Here I used `2> /dev/null` to ignore error nocification
* One thing more

Here we granted access as account 'flag00' by running `/bin/.../flag00` (look back our result).
In next levels our mission is the same: GRANT ACCESS AS TARGET ACCOUNT (target account will be 'flagxx',
in this level it's 'flag00')
