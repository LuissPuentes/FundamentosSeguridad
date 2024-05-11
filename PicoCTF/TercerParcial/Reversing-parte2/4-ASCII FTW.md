## Objetivo 
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/506/asciiftw).

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/asciiftw]
└─$ ls
asciiftw
                                                                                  
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/asciiftw]
└─$ cat asciiftw         
@@@@�▒▒▒XX��   pp�-�=�=`h�-�=�=�888 XXXDDS�td888 P�td      DDQ�tdR�td�-�=�=PP/lib64/ld-linux-x86-64.so.2GNU�GNU�x.�:��sMw���[`�F�GNU��e�mZ 
                                                         2v � #"libc.so.6__stack_chk_failprintf__cxa_finalize__libc_start_mainGLIBC_2.2.5GLIBC_2.4_ITM_deregisterTMCP�`@�?�?�?�?�?�?�?��H�H��/H��t��H���5�/��%�/��h���������h�����������%�/D����%]/D���H�=��2/��H�=Y/H�R/H9�tH�/H��t  �����H�=)/H�5"/H)�H��H��?H��H�H��tH��.H����fD�����=�.u+UH�=�.H��t
               H�=�.�   ����d�����.]������w�����UH��H��0dH�%(H�E�1��E�p�E�i�E�c�E�o�E�C�E�T�E�F�E�{�E�A�E�S�E�C�E�I�E�I�E�_�E�I�E�S�E�_�E�E�E�A�E�S�E�Y�E�_�E�3�E�C���V����H�E�dH3%(t�1�����f.�D��AWL�=c+AVI��AUI��ATA��UH�-T+SL)�H������H��t1��L��L��D��A��H��H9�u�H�[]A\A]A^A_�ff.������H�H��The flag starts with %x
D���x0����@����`���`I���� ��������8zRx
                                     ����/D$4����0F▒J
�                                                    �?▒:*3$"\����t���� �q����E�C
D�(���eF�I▒�E �E(�D0�H8�G@n8A0A(B B▒B�P���` 
��▒����o���
�
 ▒�?0(� ������o8���o���o(���o�=0@GCC: (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0▒8X|�(8
h
 (
 P`��   h �=�=�=▒�?@▒@�
                       ��! 7▒@F�=m`y�=������l!����=��=��=�  �▒�?�
                                                                 � � @3@�:Vj�@� @� �@e�▒▒@��/�▒@�i��@�"crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.8061__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryasciiftw.c__FRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTable_edata__stack_chk_fail@@GLIBC_2.4printf@@GLIBC_2.2.5__libc_start_main@@GLIBC_2.2.5__data_start__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note.gnu.property.note.gnu.build-id.note.ABI-tag.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.plt.sec.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.comment▒▒#886XX$I|| W���o��a
                                                                          ��▒i���q�  �    D�h ������=�-��?�@0�PP�`` ���5���
                         @00+@00▒       p6$�8▒                                                                                  
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/asciiftw]
└─$ chmod +x asciiftw 
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/asciiftw]
└─$ gdb -q asciiftw 
Reading symbols from asciiftw...
(No debugging symbols found in asciiftw)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001169 <+0>:     endbr64
   0x000000000000116d <+4>:     push   rbp
   0x000000000000116e <+5>:     mov    rbp,rsp
   0x0000000000001171 <+8>:     sub    rsp,0x30
   0x0000000000001175 <+12>:    mov    rax,QWORD PTR fs:0x28
   0x000000000000117e <+21>:    mov    QWORD PTR [rbp-0x8],rax
   0x0000000000001182 <+25>:    xor    eax,eax
   0x0000000000001184 <+27>:    mov    BYTE PTR [rbp-0x30],0x70
   0x0000000000001188 <+31>:    mov    BYTE PTR [rbp-0x2f],0x69
   0x000000000000118c <+35>:    mov    BYTE PTR [rbp-0x2e],0x63
   0x0000000000001190 <+39>:    mov    BYTE PTR [rbp-0x2d],0x6f
   0x0000000000001194 <+43>:    mov    BYTE PTR [rbp-0x2c],0x43
   0x0000000000001198 <+47>:    mov    BYTE PTR [rbp-0x2b],0x54
   0x000000000000119c <+51>:    mov    BYTE PTR [rbp-0x2a],0x46
   0x00000000000011a0 <+55>:    mov    BYTE PTR [rbp-0x29],0x7b
   0x00000000000011a4 <+59>:    mov    BYTE PTR [rbp-0x28],0x41
   0x00000000000011a8 <+63>:    mov    BYTE PTR [rbp-0x27],0x53
   0x00000000000011ac <+67>:    mov    BYTE PTR [rbp-0x26],0x43
   0x00000000000011b0 <+71>:    mov    BYTE PTR [rbp-0x25],0x49
   0x00000000000011b4 <+75>:    mov    BYTE PTR [rbp-0x24],0x49
   0x00000000000011b8 <+79>:    mov    BYTE PTR [rbp-0x23],0x5f
   0x00000000000011bc <+83>:    mov    BYTE PTR [rbp-0x22],0x49
   0x00000000000011c0 <+87>:    mov    BYTE PTR [rbp-0x21],0x53
   0x00000000000011c4 <+91>:    mov    BYTE PTR [rbp-0x20],0x5f
   0x00000000000011c8 <+95>:    mov    BYTE PTR [rbp-0x1f],0x45
   0x00000000000011cc <+99>:    mov    BYTE PTR [rbp-0x1e],0x41
   0x00000000000011d0 <+103>:   mov    BYTE PTR [rbp-0x1d],0x53
   0x00000000000011d4 <+107>:   mov    BYTE PTR [rbp-0x1c],0x59
   0x00000000000011d8 <+111>:   mov    BYTE PTR [rbp-0x1b],0x5f
   0x00000000000011dc <+115>:   mov    BYTE PTR [rbp-0x1a],0x33
   0x00000000000011e0 <+119>:   mov    BYTE PTR [rbp-0x19],0x43
   0x00000000000011e4 <+123>:   mov    BYTE PTR [rbp-0x18],0x46
   0x00000000000011e8 <+127>:   mov    BYTE PTR [rbp-0x17],0x34
--Type <RET> for more, q to quit, c to continue without paging--c
   0x00000000000011ec <+131>:   mov    BYTE PTR [rbp-0x16],0x42
   0x00000000000011f0 <+135>:   mov    BYTE PTR [rbp-0x15],0x46
   0x00000000000011f4 <+139>:   mov    BYTE PTR [rbp-0x14],0x41
   0x00000000000011f8 <+143>:   mov    BYTE PTR [rbp-0x13],0x44
   0x00000000000011fc <+147>:   mov    BYTE PTR [rbp-0x12],0x7d
   0x0000000000001200 <+151>:   movzx  eax,BYTE PTR [rbp-0x30]
   0x0000000000001204 <+155>:   movsx  eax,al
   0x0000000000001207 <+158>:   mov    esi,eax
   0x0000000000001209 <+160>:   lea    rdi,[rip+0xdf4]        # 0x2004
   0x0000000000001210 <+167>:   mov    eax,0x0
   0x0000000000001215 <+172>:   call   0x1070 <printf@plt>
   0x000000000000121a <+177>:   nop
   0x000000000000121b <+178>:   mov    rax,QWORD PTR [rbp-0x8]
   0x000000000000121f <+182>:   xor    rax,QWORD PTR fs:0x28
   0x0000000000001228 <+191>:   je     0x122f <main+198>
   0x000000000000122a <+193>:   call   0x1060 <__stack_chk_fail@plt>
   0x000000000000122f <+198>:   leave
   0x0000000000001230 <+199>:   ret
End of assembler dump.
(gdb) 
```

picoCTF{ASCII_IS_EASY_3CF4BFAD}
## Notas
70
69
63
6f
43
54
46
7b
41
53
43
49
49
5f
49
53
5f
45
41
53
59
5f
33
43
46
34
42
46
41
44
7d

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=NzANCjY5DQo2Mw0KNmYNCjQzDQo1NA0KNDYNCjdiDQo0MQ0KNTMNCjQzDQo0OQ0KNDkNCjVmDQo0OQ0KNTMNCjVmDQo0NQ0KNDENCjUzDQo1OQ0KNWYNCjMzDQo0Mw0KNDYNCjM0DQo0Mg0KNDYNCjQxDQo0NA0KN2Q&ieol=CRLF&oeol=CRLF