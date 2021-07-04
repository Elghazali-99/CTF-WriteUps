# can't see - 0x1 Challenge
## Challenge description
> You can still have a shell!
But this time I'm only showing output if there's an error in your command :D

> Connect with : nc misc.mk.shellmates.me 3332

> Author : chenx3n
## Solution
there is output only when in case of error, so let's redirect the stdout > stderr 
```cat flag.txt 1>&2```
![image](https://user-images.githubusercontent.com/60848443/124401236-2981da80-dd20-11eb-9a82-1a3e98770ab7.png)

flag: shellmates{IO_reDIr3CtI0N_i$_a1W4y$_ImPOr7Ant}
