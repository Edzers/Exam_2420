# Exam_2420
# Part 1
``` 
sudo apt update
sudo apt upgrade 
sudo reboot
```
# Part 2 
Keybindings used to make the changes include the following:
First, gg to get to the top of the buffer.

Entering insert mode first to replace the -eq 1 with -eq 0, moving with the arrowkeys, or k(up) h(left) l(right) j(down)

To replace the mistyped V with C (celsius), I used /V to find the instances of V, and then manually entered insert mode with i to replace.

As for the numbs, I used the command :s/numbs/:digit: to replace it, as well as :1,11s/eco/echo/g to replace all instances of "eco" with "echo" through lines 1 to 11 (the entire script). Then, after I was done editing, I exited vim with :q!.

![2420ex1pic](https://user-images.githubusercontent.com/98194499/206576327-07383c0f-8ac6-47cb-ad48-a49f94b3fe5e.png)


# Part 3
Found the first screenshot by searching with /options and scrolling down until I found the correct option for printing the current boot users.
![2420part3pic1](https://user-images.githubusercontent.com/98194499/206575540-2705586c-b27e-4e05-8f1f-f49b3a30c1ef.png)

Found the second screenshot with /priority for the -p command.
![priority](https://user-images.githubusercontent.com/98194499/206575570-777871a8-3e35-43d6-93aa-12d9c80a91ec.png)

Found the third screenshot with /json to find json-pretty.
![pretty](https://user-images.githubusercontent.com/98194499/206575590-291a49b1-7ea5-4b41-bccd-fa474def6329.png)

Final output:
![part3script](https://user-images.githubusercontent.com/98194499/206575660-df684e03-dd5e-4ea8-8d6f-0a211618ea3c.png)


# Part 4
Put script in bin directory.
```
#!/bin/bash


# Use grep to find the users
users=$(grep -E "^[^:]+:[^:]+:[1-5][0-9][0-9][0-9]:" /etc/passwd)

# Use awk to extract the name, UID, and login shell for each user
echo "$users" | awk -F: '{print $1", "$3", "$7}'

# Print all currently logged in users using the 'w' command

echo "Users currently logged in are:"
login=$(who | awk '{print $1}')
echo "$login"

# Get the output and save it to the motd file
echo "$users" > /etc/motd
echo "$login" >> /etc/motd
```

# Part 5
```
[Unit]
Description=exampart5

[Service]
Type=simple
ExecStart=/bin/part4script.sh

[Install]
WantedBy=multi-user.target
```

# Part 6
```
[Unit]
Description=exampart6timer

[Timer]
OnBootSec=1min
OnUnitActiveSec=1d

[Install]
WantedBy=timers.target


```







