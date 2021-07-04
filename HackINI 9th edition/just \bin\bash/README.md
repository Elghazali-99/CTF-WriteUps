# /bin/bash Challenge
## Challenge description
> Yaaay I got a shell!
> Wait there's no ls, no cat, just /bin/bash !!
## Solution
only  bash shell ? so lets try this script that reads a file
```
#!/bin/bash
input="flag.txt"
while IFS= read -r line
do
  echo "$line"
done < "$input"
```
![image](https://user-images.githubusercontent.com/60848443/124401535-e88ac580-dd21-11eb-8bab-3d28ac36004e.png)
