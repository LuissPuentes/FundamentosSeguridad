## Objetivo 
What can you do with this file?I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/291/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/SafeOpener2]
└─$ ls
SafeOpener.class
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/SafeOpener2]
└─$ file SafeOpener.class 
SafeOpener.class: compiled Java class data, version 52.0 (Java 1.8)
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/SafeOpener2]
└─$ java SafeOpener       
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter password for the safe: sld
c2xk
Password is incorrect

You have  2 attempt(s) left
Enter password for the safe: mkd
bWtk
Password is incorrect

You have  1 attempt(s) left
Enter password for the safe: oowowow
b293b3dvdw==
Password is incorrect

You have  0 attempt(s) left

```

```
   import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Base64;
import java.util.Base64.Encoder;

public class SafeOpener {
   public static void main(String[] args) throws IOException {
      BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
      Encoder encoder = Base64.getEncoder();
      String encodedkey = "";
      String key = "";

      for(int i = 0; i < 3; ++i) {
         System.out.print("Enter password for the safe: ");
         key = keyboard.readLine();
         encodedkey = encoder.encodeToString(key.getBytes());
         System.out.println(encodedkey);
         boolean isOpen = openSafe(encodedkey);
         if (isOpen) {
            break;
         }

         System.out.println("You have  " + (2 - i) + " attempt(s) left");
      }

   }

   public static boolean openSafe(String password) {
      String encodedkey = "picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_198203f7}";
      if (password.equals(encodedkey)) {
         System.out.println("Sesame open");
         return true;
      } else {
         System.out.println("Password is incorrect\n");
         return false;
      }
   }
}
```
## Notas
en un decompiler online, subimos el archivo .class y en el codigo java nos da la bandera.

## Referencias
https://www.decompiler.com/jar/3dc78584a5d7406b9baa096edc13b8c1/SafeOpener.java
