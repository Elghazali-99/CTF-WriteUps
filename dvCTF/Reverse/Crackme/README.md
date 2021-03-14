# Crackme Challenge
## Challenge description
> Find the password!.
> Attached file: crackme
## Solution
after executing the file on Linux the input format was: ``crackme password`` then it returns a hardcoded string.
i disassembled this file using IDA then in ``loc_13AC:`` i changed the last instruction ``JNZ`` with ``JZ`` 


![image](https://user-images.githubusercontent.com/60848443/111077435-07eeb000-84f1-11eb-9a71-f73f9a0ee566.png)

now using a random password the output becomes ``Well done! flag: dvCTF{randpass}``. means the Flag is the entered password!
### Step 2:
inside ``loc_13AC:`` there is a call function ``call    emmdee5`` which looks like MD5 ? Let's jump throught it!

![image](https://user-images.githubusercontent.com/60848443/111077664-23a68600-84f2-11eb-87a6-f40b52d4028d.png)


inside ``emdee5`` there is another function which is ``esrever``, the function's name is indicating that it's inversing some bytes ``reverse --> esrever`` -inversing every two bytes exactly

now the procedure becomes clear:
* 1- takes the input string
* 2- encode it using MD5
* 3- reversing bytes
* 4- comparing it to ``d2862c3379cbf547d317b3b1771a4fb6`` 

### Step 3:
* 1- inversing the hardcoded string: ``b64f1a77b1b317d347f5cb79332c86d2``
* 2- decoding it using crackstation.net 

![image](https://user-images.githubusercontent.com/60848443/111078052-02df3000-84f4-11eb-8d66-3a4765baf524.png)

* 3- Whoah!, the flag is ``dvCTF{741852963}``
