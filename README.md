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



