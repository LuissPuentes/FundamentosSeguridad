## Objetivo 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solución
```bash
┌──(luispuentes㉿kali)-[~/picoctf/forensic/sharkonwire2]
└─$ ls
capture.pcap  data.txt

┌──(luispuentes㉿kali)-[~/picoctf/forensic/sharkonwire2]
└─$ cat data.txt | grep UDP | awk '{print $7}'
5000
5112
5105
5099
5111
5067
5084
5070
5123
5112
5049
5076
5076
5102
5051
5114
5051
5100
5095
5100
5097
5116
5097
5095
5118
5049
5097
5095
5115
5116
5051
5103
5048
5125
5000

┌──(luispuentes㉿kali)-[~/picoctf/forensic/sharkonwire2]
└─$ cat data.txt | grep UDP | awk '{print $7}' | cut -e2
cut: invalid option -- 'e'
Try 'cut --help' for more information.

┌──(luispuentes㉿kali)-[~/picoctf/forensic/sharkonwire2]
└─$ cat data.txt | grep UDP | awk '{print $7}' | cut -c2- | grep -v 000
112
105
099
111
067
084
070
123
112
049
076
076
102
051
114
051
100
095
100
097
116
097
095
118
049
097
095
115
116
051
103
048
125

┌──(luispuentes㉿kali)-[~/picoctf/forensic/sharkonwire2]
└─$ ls                                                                                                                                                                 
capture.pcap  data.txt

┌──(luispuentes㉿kali)-[~/picoctf/forensic/sharkonwire2]
└─$ cat data.txt | grep UDP | awk '{print $7}' | cut -c2- | grep -v 000                                                                                                
112
105
099
111
067
084
070
123
112
049
076
076
102
051
114
051
100
095
100
097
116
097
095
118
049
097
095
115
116
051
103
048
125

picoCTF{p1LLf3r3d_data_v1a_st3g0}

```


## Notas
en wireshark se tomarron ciertos paquetes y los exportaron en un txt

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Decimal('Line%20feed',false)&input=MTEyCjEwNQowOTkKMTExCjA2NwowODQKMDcwCjEyMwoxMTIKMDQ5CjA3NgowNzYKMTAyCjA1MQoxMTQKMDUxCjEwMAowOTUKMTAwCjA5NwoxMTYKMDk3CjA5NQoxMTgKMDQ5CjA5NwowOTUKMTE1CjExNgowNTEKMTAzCjA0OAoxMjU