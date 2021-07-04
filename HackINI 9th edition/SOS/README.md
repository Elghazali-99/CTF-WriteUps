# SOS Challenge
## Challenge description
> Mayday mayday! The nazis are invading de_aztec, we need some reinforcements over here!
I'm sending you their coordinates, over.
> Attached file: message.txt
## Solution
the text looks like a morse code
after the decoding using the https://morsedecoder.com/ :
![image](https://user-images.githubusercontent.com/60848443/124399906-a27c3480-dd16-11eb-902b-870c5e651229.png)
 the output contains some 'BREAK' after every sequence of 'TEETE....'
with a simple python code i splitted the decoded text and replaced the 'T' by '0' and 'E' by '1'
```ss = s.split('BREAK')

for i in ss:
    i=i.replace('T','0')
    i=i.replace('E','1')
    print(i) 
```
on the output i noticed a square, so to make it clearer i replaced 'T' by '█' and 'E' by ' '
![image](https://user-images.githubusercontent.com/60848443/124400188-93968180-dd18-11eb-836e-ad22ad2e3300.png)

after that i copied the output to texteditor, removed the line spacing, to get something looks like a QR code that is called Aztec Barcode
![photo_2021-07-03_16-21-23](https://user-images.githubusercontent.com/60848443/124400444-5632f380-dd1a-11eb-8883-56f4df6f5b23.jpg)

the scan result shows the flag ! using this website : https://products.aspose.app/barcode/recognize/aztec

FLAG: shellmates{1_l0v3_b4rc0d3es_4nd_1_l0v3_d3_4zt3c_:)}
