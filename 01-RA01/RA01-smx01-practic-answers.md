t### 1) `/etc/cron.hourly/`

`drwxr-xr-x 2 root root 4096 Dec 7 23:04 /etc/cron.hourly/` 

a) directori
b) 2
c) root
d) root
e) 4096 bytes
f) propietari: rwx
g) grup: r-x
h) altres: r-x
i) pot entrar: propietari, grup i altres (tots tenen x al directori)
j) pot modificar contingut: només root (cal w al directori; només el propietari el té)

### 2) Hex 1C3₁₆ → resta

1C3₁₆ = 1·16² + 12·16 + 3 = 256 + 192 + 3 = **451₁₀**
Binari: 1C3 = 0001 1100 0011 → **111000011₂**
Octal: 451₁₀ → **703₈**

### 3) Unitats (dues respostes possibles si no vols fixar taula)

Com que **no indiques la taula**, l’examen és contestable de dues maneres. A correcció, jo validaria “A o B” si és consistent.

**Amb 1024**

* 8192 bytes → 8 KB
* 1,5 MB → 1.572.864 bytes
* 2 GB → 2048 MB
* 65536 bits → 8192 bytes
* 4 KB → 32768 bits

**Amb 1000**

* 8192 bytes → 8,192 KB
* 1,5 MB → 1.500.000 bytes
* 2 GB → 2000 MB
* 65536 bits → 8192 bytes
* 4 KB → 32000 bits
    
*(L’important és que ho facin amb procés i coherència.)*

### 4) Permisos 500

500 → propietari 5=r+x, grup 0, altres 0
a) propietari: llegir i executar
b) grup: res
c) altres: res
d) apte per script: sí si només propietari; però no el podrà editar (no té w)
e) dades personals: millor 600; 500 no és l’ideal

### 5) Octal (a partir de línia)

a) -rwxr-xr-x → 755
b) -rw-r----- → 640
c) -rwxr-x--- → 750 


