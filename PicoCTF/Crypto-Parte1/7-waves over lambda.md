## Objetivo 
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 39894`.

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto]
└─$ nc jupiter.challenges.picoctf.org 39894
-------------------------------------------------------------------------------
zrudbogt ljbj wt krxb ieod - ibjmxjuzk_wt_z_rfjb_eonaho_odiezdgkxj
-------------------------------------------------------------------------------
oejsjk ikrhrbrfwgzl yobonoprf vot glj glwbh tru ri ikrhrb qoferfwgzl yobonoprf, o eouh rvujb vjee yurvu wu rxb hwtgbwzg wu lwt rvu hok, ouh tgwee bjnjnajbjh onrud xt rvwud gr lwt derrnk ouh gbodwz hjogl, vlwzl loqqjujh glwbgjju kjobt odr, ouh vlwzl w tloee hjtzbwaj wu wgt qbrqjb qeozj. irb glj qbjtjug w vwee ruek tok glog glwt eouhrvujbirb tr vj xtjh gr zoee lwn, oeglrxdl lj lobhek tqjug o hok ri lwt ewij ru lwt rvu jtgogjvot o tgboudj gkqj, kjg ruj qbjggk ibjmxjugek gr aj njg vwgl, o gkqj oacjzg ouh fwzwrxt ouh og glj tonj gwnj tjutjejtt. axg lj vot ruj ri glrtj tjutjejtt qjbtrut vlr obj fjbk vjee zoqoaej ri errywud oigjb gljwb vrbehek oiiowbt, ouh, oqqobjugek, oigjb urglwud jetj. ikrhrb qoferfwgzl, irb wutgouzj, ajdou vwgl ujsg gr urglwud; lwt jtgogj vot ri glj tnoeejtg; lj bou gr hwuj og rgljb nju't goaejt, ouh iotgjujh ru gljn ot o grohk, kjg og lwt hjogl wg oqqjobjh glog lj loh o lxuhbjh glrxtouh brxaejt wu lobh zotl. og glj tonj gwnj, lj vot oee lwt ewij ruj ri glj nrtg tjutjejtt, iougotgwzoe ijeervt wu glj vlrej hwtgbwzg. w bjqjog, wg vot urg tgxqwhwgkglj nocrbwgk ri gljtj iougotgwzoe ijeervt obj tlbjvh ouh wugjeewdjug jurxdlaxg cxtg tjutjejttujtt, ouh o qjzxewob uogwruoe irbn ri wg.

```

frequency_is_c_over_lambda_agflcgtyue

## Notas
en la pagina https://www.guballa.de/substitution-solver nos da el texto descifrado por sustitucion.

la pista nos dice que la bandera no esta en el formato acostumbrado
## Referencias
https://www.guballa.de/substitution-solver

https://gchq.github.io/CyberChef/#recipe=Substitute('abcdefghijklmnopqrstuvwxyz','zudxvnjqgpieahbrfokmtsyclw',false)&input=LS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLQ0KeHJmaXBtdXYgbmxwbCBrdiB3cmJwIHF5bWkgLSBxcGxoYmxmeHdfa3ZfeF9yZWxwX3ltdG9jbV9taXF5eGl1d2JsDQotLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tDQp6bCB6bHBsIGZydSB0YnhuIHRycGwgdW5tZiBtIGhibXB1bHAgcnEgbWYgbnJicCByYnUgcnEgcmJwIHZua2ogdWt5eSB6bCB2bXogbmxwIHZrZnMsIG1mYyB1bmxmIGsgYmZjbHB2dXJyYyBxcnAgdW5sIHFrcHZ1IHVrdGwgem5tdSB6bXYgdGxtZnUgb3cgbSB2bmtqIHFyYmZjbHBrZmkga2YgdW5sIHZsbS4gIGsgdGJ2dSBteHNmcnp5bGNpbCBrIG5tYyBubXBjeXcgbHdsdiB1ciB5cnJzIGJqIHpubGYgdW5sIHZsbXRsZiB1cnljIHRsIHZubCB6bXYgdmtmc2tmaTsgcXJwIHFwcnQgdW5sIHRydGxmdSB1bm11IHVubHcgcG11bmxwIGpidSB0bCBrZnVyIHVubCBvcm11IHVubWYgdW5tdSBrIHRraW51IG9sIHZta2MgdXIgaXIga2YsIHR3IG5sbXB1IHptdiwgbXYga3UgemxwbCwgY2xtYyB6a3Vua2YgdGwsIGptcHV5dyB6a3VuIHFwa2ludSwgam1wdXl3IHprdW4gbnJwcHJwIHJxIHRrZmMsIG1mYyB1bmwgdW5yYmludXYgcnEgem5tdSB6bXYgd2x1IG9scXJwbCB0bC4&oenc=65001&ieol=CRLF&oeol=CRLF