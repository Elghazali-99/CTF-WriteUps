# Rocca Pia Challenge
## Challenge description
> Help me! I can't find the password for this binary!.
> Attached file: rocca_pia
## Solution
* Disassembling using Ghidra

![image](https://user-images.githubusercontent.com/60848443/111136918-847ba000-857e-11eb-8643-3e9eb20b7e9a.png)


the main function containing ``transform`` function where its returned value is saved to ``iVar1`` and this last one is used in if/else to show `` Nice Flag`` or ``Nice Try``

Let's see what's inside the ``transform`` function:

![image](https://user-images.githubusercontent.com/60848443/111137550-36b36780-857f-11eb-83a2-730bbb2b79f1.png)

1. taking a sequence of bytes
2. performing an ``XOR`` operation with each byte
   - if the index is even perform an ``XOR`` with ``0x13``
   - if the index is odd perform an ``XOR`` with ``0x37``
3. comparing the final result with ``wAPcULZh\x7f\x06x\x04LDd\x06~Z\"YtJ``

**now all we need is to do the inverse using a simple python script.**
```rocca_pia.py
#Python 2.7
def unxor(password):
   result = ""
   for i in range(len(password)):
       if i & 1 == 0:
           result += chr(ord(password[i]) ^ 0x13)
       else:
           result += chr(ord(password[i]) ^ 0x37)
   return result

print(unxor('wAPcULZh\x7f\x06x\x04LDd\x06~Z\"YtJ'))

```
result = ``dvCTF{I_l1k3_sw1mm1ng}``
