## Objetivo 
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Solución
```bash
luispuentes-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
nurse
Please give the 01101110 01110101 01110010 01110011 01100101 as a word.
...
you have 45 seconds.....

Input:
nurse
Please give me the  141 156 151 155 141 164 151 157 156 as a word.
Input:
animation
Please give me the 636f6d7075746572 as a word.
Input:
computer
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}

luispuentes-picoctf@webshell:~$
```

## Notas
Hay que ir conviertiendo 

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=MDExMDExMTAgMDExMTAxMDEgMDExMTAwMTAgMDExMTAwMTEgMDExMDAxMDE

https://gchq.github.io/CyberChef/#recipe=From_Octal('Space')&input=MTQxIDE1NiAxNTEgMTU1IDE0MSAxNjQgMTUxIDE1NyAxNTY

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=NjM2ZjZkNzA3NTc0NjU3Mg
