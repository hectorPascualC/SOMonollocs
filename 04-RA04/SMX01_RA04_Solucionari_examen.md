
# 1. Documents relacionats principals

| Document | Contingut que justifica |
|---|---|
| `bloc03.md` | Usuaris GNU/Linux, `useradd`, `passwd`, `/etc/passwd`, `/etc/shadow`, UID, GID, directori personal i shell |
| `bloc03.md` | Grups, `/etc/group`, `usermod -aG`, permisos `770`, `setgid`, `sticky bit`, `/etc/skel` |
| `bloc06.md` | Sistema d’arxius, muntatge, `mount`, `umount`, `/etc/mtab`, `/etc/fstab`, `mount -a` |
| `M02.RA3.A1.docx` | Pràctica d’usuaris, `/etc/skel`, permisos i comparació de sistemes |
| `M02.RA3.A3.docx` | Pràctica de gestió d’arxius, directoris, emmagatzematge i `df -h` |
| `M2.RA3.A3.A5.docx` | Pràctica de carpetes compartides restringides per grups |

---

# 2. Respostes ràpides amb document relacionat

## 2.1. Versió A

| Pregunta | Resposta | Tema | Document relacionat |
|---:|:---:|---|---|
| 1 | **b** | `useradd -m -s /bin/bash` | `bloc03.md` |
| 2 | **c** | `/etc/passwd` i `x` | `bloc03.md` |
| 3 | **a** | `passwd -e` | `bloc03.md` |
| 4 | **b** | `usermod -aG` | `bloc03.md` |
| 5 | **c** | `/etc/group` | `bloc03.md` |
| 6 | **a** | permisos `770` | `bloc03.md` |
| 7 | **c** | `setgid` i `sticky bit` | `bloc03.md` |
| 8 | **a** | `/etc/skel` i `.benvinguda.txt` | `bloc03.md` + `M02.RA3.A1.docx` |
| 9 | **a** | `/etc/mtab` i `/etc/fstab` | `bloc06.md` |
| 10 | **a** | línia de `/etc/fstab` | `bloc06.md` |

## 2.2. Versió B

| Pregunta | Resposta | Tema | Document relacionat |
|---:|:---:|---|---|
| 1 | **d** | `/etc/group` | `bloc03.md` |
| 2 | **d** | línia de `/etc/fstab` | `bloc06.md` |
| 3 | **a** | `setgid` i `sticky bit` | `bloc03.md` |
| 4 | **c** | `useradd -m -s /bin/bash` | `bloc03.md` |
| 5 | **d** | permisos `770` | `bloc03.md` |
| 6 | **c** | `usermod -aG` | `bloc03.md` |
| 7 | **c** | `/etc/mtab` i `/etc/fstab` | `bloc06.md` |
| 8 | **c** | `passwd -e` | `bloc03.md` |
| 9 | **c** | `/etc/skel` i `.benvinguda.txt` | `bloc03.md` + `M02.RA3.A1.docx` |
| 10 | **d** | `/etc/passwd` i `x` | `bloc03.md` |

---

# 3. Correcció detallada del test



## 3.1. Crear usuari amb `useradd -m -s /bin/bash`

**A:** pregunta 1 → resposta **b**  
**B:** pregunta 4 → resposta **c**

La comanda és:

```bash
sudo useradd -m -s /bin/bash alumne1
```

La resposta correcta és que crea l’usuari `alumne1`, crea el seu directori personal i li assigna `/bin/bash` com a shell.

### On surt a la teoria?

**bloc03.md — Diapositiva 14, “Crear usuari amb directori personal”.**

Text literal dels apunts:

> En molts sistemes és habitual usar l'opció `-m` per crear també el directori personal.

Exemple literal:

```bash
sudo useradd -m -s /bin/bash alumne1
sudo passwd alumne1
```

Text literal:

> crea l'usuari `alumne1`  
> crea `/home/alumne1`  
> assigna `/bin/bash` com a shell  
> permet definir una contrasenya

---

## 3.2. Interpretar `/etc/passwd` i la `x`

**A:** pregunta 2 → resposta **c**  
**B:** pregunta 10 → resposta **d**

Línia de l’examen:

```text
alumne1:x:1001:1001:Alumne SMX:/home/alumne1:/bin/bash
```

La resposta correcta és que la `x` indica que la informació sensible de la contrasenya no es guarda directament a `/etc/passwd`.

### On surt a la teoria?

**bloc03.md — Diapositiva 23, “Camps de `/etc/passwd`”.**

Text literal:

> Cada línia de `/etc/passwd` té 7 camps:

> 1. nom d'usuari  
> 2. contrasenya indicada normalment amb `x`  
> 3. UID  
> 3. GID  
> 4. informació addicional  
> 6. directori personal  
> 7. shell per defecte

Exemple literal:

```text
alumne1:x:1001:1001:Alumne SMX:/home/alumne1:/bin/bash
```

**bloc03.md — Diapositiva 24, “Què significa la `x` a `/etc/passwd`?”.**

Text literal:

> `/etc/passwd` mostra una `x`  
> la contrasenya real no és visible  
> la informació sensible es guarda a `/etc/shadow`

---

## 3.3. Opció correcta de `passwd`

**A:** pregunta 3 → resposta **a**  
**B:** pregunta 8 → resposta **c**

La resposta correcta és:

```bash
passwd -e alumne1
```

Obliga l’usuari a canviar la contrasenya en el proper inici de sessió.

### On surt a la teoria?

**bloc03.md — Diapositiva 16, “Opcions útils de `passwd`”.**

Text literal:

> `-l` → bloqueja temporalment el compte  
> `-x` → defineix la durada màxima de la contrasenya  
> `-e` → obliga a canviar la contrasenya en el proper inici de sessió  
> `-S` → mostra l'estat de la contrasenya

---

## 3.3. Afegir usuari a grup sense perdre grups secundaris

**A:** pregunta 4 → resposta **b**  
**B:** pregunta 6 → resposta **c**

La comanda correcta és:

```bash
sudo usermod -aG projecte1 anna
```

### On surt a la teoria?

**bloc03.md — Diapositiva 16, “Afegir usuaris a grups amb `usermod`”.**

Text literal:

```bash
sudo usermod -aG nom_grup usuari
```

Exemple literal:

```bash
sudo usermod -aG projecte1 anna
```

Text literal:

> La combinació `-aG` és important:  
> `-G` indica grups secundaris  
> `-a` evita perdre els grups secundaris que l'usuari ja tenia

**bloc03.md — Diapositiva 17, “Error habitual amb `usermod`”.**

Text literal:

> Sense `-a`, pot substituir la llista de grups secundaris de l'usuari.

---

## 3.4. Interpretar `/etc/group`

**A:** pregunta 5 → resposta **c**  
**B:** pregunta 1 → resposta **d**

Línia de l’examen:

```text
projecte1:x:1500:anna,joan
```

La resposta correcta és que `anna` i `joan` apareixen com a membres addicionals del grup `projecte1`.

### On surt a la teoria?

**bloc03.md — Diapositiva 8, “On es guarden els grups?”.**

Text literal:

> `/etc/group`

Text literal:

> Aquest fitxer conté:  
> la llista de grups del sistema  
> el GID de cada grup  
> els usuaris que pertanyen a cada grup com a membres addicionals

**bloc03.md — Diapositiva 9, “Estructura de `/etc/group`”.**

Text literal:

```text
nom_grup:contrasenya:GID:llista_usuaris
```

Exemple literal:

```text
projecte1:x:1005:anna,joan
```

**bloc03.md — Diapositiva 10, “Camps de `/etc/group`”.**

Text literal:

> llista d'usuaris → membres addicionals separats per comes

---

## 3.6. Permisos `770`

**A:** pregunta 6 → resposta **a**  
**B:** pregunta 5 → resposta **d**

La resposta correcta és que propietari i grup tenen lectura, escriptura i execució, i altres usuaris no tenen cap permís.

### On surt a la teoria?

**bloc03.md — Diapositiva 21, “Grups i permisos”.**

Text literal:

```bash
sudo chmod 770 /srv/projecte1
  # propietari → 7 → rwx → llegir, escriure i entrar/executar
  # grup       → 7 → rwx → llegir, escriure i entrar/executar
  # altres     → 0 → cap permís
```

Text literal:

> el propietari tingui permisos  
> el grup `projecte1` tingui permisos  
> la resta d'usuaris no tingui accés

---

## 3.7. Setgid i sticky bit

**A:** pregunta 7 → resposta **c**  
**B:** pregunta 3 → resposta **a**

La resposta correcta és que el setgid en un directori fa que els fitxers nous heretin el grup del directori, mentre que el sticky bit impedeix que un usuari elimini fitxers d’altres usuaris en directoris compartits.

### On surt a la teoria?

**bloc03.md — Diapositiva 23, “Setgid en directoris compartits”.**

Text literal:

```bash
sudo chmod 2770 /srv/projecte1
```

Text literal:

> El `2` inicial fa que els fitxers nous creats dins la carpeta mantinguin el grup propietari del directori.

**bloc03.md — Diapositiva 24, “No confondre setgid i sticky bit”.**

Text literal:

> `chmod 2770` aplica **setgid**, no sticky bit.

Text literal:

> setgid en directori → els fitxers nous hereten el grup del directori  
> sticky bit → impedeix que un usuari elimini fitxers d'altres usuaris en directoris compartits

Exemple literal:

```bash
sudo chmod 1777 /srv/compartit
# 1   → sticky bit activat
# 777 → tothom pot llegir, escriure i entrar
```

---

## 3.8. `/etc/skel` i `.benvinguda.txt`

**A:** pregunta 8 → resposta **a**  
**B:** pregunta 9 → resposta **c**

La resposta correcta és que el fitxer `.benvinguda.txt` hauria d’aparèixer al directori personal de `alumne2`.

### On surt a la teoria?

**bloc03.md — Diapositiva 28, “Què és `/etc/skel`?”.**

Text literal:

> `/etc/skel` és el directori plantilla per als nous usuaris.

Text literal:

> Conté una estructura mínima comuna que es copia al directori personal quan es crea un compte nou.

**bloc03.md — Diapositiva 31, “Exemple amb `/etc/skel`”.**

Text literal:

```bash
sudo nano /etc/skel/.benvinguda.txt
```

```bash
sudo useradd -m -s /bin/bash alumne2
sudo passwd alumne2
```

```bash
ls -la /home/alumne2
```

Text literal:

> El nou usuari hauria de rebre el fitxer `.benvinguda.txt`.

### On surt a la pràctica?

**M02.RA3.A1.docx**

Text literal:

> Modifica `/etc/skel` afegint un fitxer personalitzat (ex. `.benvinguda.txt`) i crea un altre usuari.

---

## 3.9. `/etc/mtab` i `/etc/fstab`

**A:** pregunta 9 → resposta **a**  
**B:** pregunta 7 → resposta **c**

La resposta correcta és que `/etc/mtab` mostra què està muntat actualment i `/etc/fstab` defineix muntatges automàtics o permanents.

### On surt a la teoria?

**bloc06.md — Diapositiva 15, “Com veure què està muntat?”.**

Text literal:

> `/etc/mtab`

Text literal:

> Aquest fitxer mostra els sistemes d'arxius muntats actualment.

Text literal:

> `/etc/mtab` descriu l'estat actual del muntatge.

**bloc06.md — Diapositiva 21, “Diferència entre `/etc/mtab` i `/etc/fstab`”.**

Text literal:

> `/etc/mtab`  
> mostra què està muntat **ara mateix**  
> representa l'estat actual del sistema

Text literal:

> `/etc/fstab`  
> indica què s'ha de muntar **automàticament**  
> és una configuració permanent

Text literal:

> `mtab` informa; `fstab` configura.

---

## 3.10. Camps d’una línia de `/etc/fstab`

**A:** pregunta 10 → resposta **a**  
**B:** pregunta 2 → resposta **d**

Línia de l’examen:

```text
UUID=1234-ABCD  /mnt/dades  ext4  defaults  0  2
```

La resposta correcta és que `UUID=1234-ABCD` identifica la partició, `/mnt/dades` és el punt de muntatge i `ext4` és el tipus de sistema d’arxius.

### On surt a la teoria?

**bloc06.md — Diapositiva 22, “Estructura d'una línia de `/etc/fstab`”.**

Text literal:

```text
dispositiu  punt_muntatge  tipus  opcions  backup  revisió
```

Exemple literal:

```text
UUID=xxxx  /dades  ext4  defaults  0  2
```

**bloc06.md — Diapositiva 23, “Camp 1: dispositiu”.**

Text literal:

> El primer camp identifica què volem muntar.

Text literal:

> El **UUID** identifica la partició de manera més estable que el nom `/dev/sdX`.

**bloc06.md — Diapositiva 24, “Camps 2 i 3: punt i tipus”.**

Text literal:

> Segon camp: punt de muntatge

Text literal:

> Tercer camp: tipus de sistema d'arxius

**bloc06.md — Diapositiva 27, “Exemple complet de `/etc/fstab`”.**

Text literal:

```text
UUID=1234-ABCD  /mnt/dades  ext4  defaults  0  2
```

Text literal:

> munta la partició identificada pel UUID  
> la fa accessible a `/mnt/dades`  
> utilitza sistema d'arxius `ext4`  
> aplica opcions per defecte  
> no fa backup  
> la revisa després del sistema principal

---

# 4. Part pràctica — Solucionari conjunt

La part pràctica és la mateixa en A i B, però canviada d’ordre.

- **A:** primer usuaris/grups/permisos i després sistema d’arxius.
- **B:** primer sistema d’arxius i després usuaris/grups/permisos.

---

## 5.1. Usuaris, grups i permisos d’una carpeta de projecte

### a. Crear l’usuari, assignar contrasenya i comprovar-lo

```bash
sudo useradd -m -s /bin/bash alumneprova
sudo passwd alumneprova
id alumneprova
grep alumneprova /etc/passwd
```

**Explicació:**

- `useradd` crea l’usuari.
- `-m` crea el directori personal.
- `-s /bin/bash` assigna Bash com a shell.
- `passwd` assigna contrasenya.
- `id` comprova UID, GID i grups.
- `grep` comprova l’entrada dins `/etc/passwd`.

**On surt:** bloc03.md, diapositives 14 i 28.

---

### b. Crear grup i afegir l’usuari amb `-aG`

```bash
sudo groupadd projecte1
sudo usermod -aG projecte1 alumneprova
id alumneprova
groups alumneprova
```

**Explicació:**

`-aG` és necessari perquè afegeix el grup nou sense eliminar els altres grups secundaris.

**On surt:** bloc03.md, diapositives 12, 16, 17 i 18.

---

### c. Crear carpeta, assignar grup i aplicar permisos `770`

```bash
sudo mkdir -p /srv/projecte1
sudo chgrp projecte1 /srv/projecte1
sudo chmod 770 /srv/projecte1
ls -ld /srv/projecte1
```

**Explicació de `770`:**

- primer `7`: propietari amb `rwx`;
- segon `7`: grup amb `rwx`;
- tercer `0`: altres usuaris sense permisos.

**On surt:** bloc03.md, diapositiva 21.

---

### d. Aplicar setgid i diferenciar-lo del sticky bit

```bash
sudo chmod 2770 /srv/projecte1
ls -ld /srv/projecte1
```

**Explicació:**

El `2` inicial activa `setgid`. Els fitxers nous hereten el grup del directori.

Exemple de sticky bit:

```bash
sudo chmod 1777 /srv/compartit
```

També és vàlid l’exemple:

```bash
/tmp
```

**On surt:** bloc03.md, diapositives 23 i 23.

---

## 5.2. Sistema d’arxius, muntatge i `/etc/fstab`

### a. Explicar muntatge i muntar `/dev/sdb1`

```bash
sudo mkdir -p /mnt/dades
sudo mount -t ext4 /dev/sdb1 /mnt/dades
```

**Explicació:**

Muntar una partició vol dir fer accessible el seu contingut des d’un directori del sistema. Aquest directori és el punt de muntatge.

**On surt:** bloc06.md, diapositives 5, 10, 11 i 12.

---

### b. Comprovar muntatge i desmuntar

```bash
mount | grep /mnt/dades
df -h
sudo umount /mnt/dades
```

També és vàlid:

```bash
cat /etc/mtab | grep /mnt/dades
```

**On surt:** bloc06.md, diapositives 15, 16 i 17. `df -h` surt a la pràctica A3.

---

### c. Línia orientativa de `/etc/fstab`

```text
UUID=1234-ABCD  /mnt/dades  ext4  defaults  0  2
```

**Camps:**

- `UUID=1234-ABCD`: identifica la partició.
- `/mnt/dades`: punt de muntatge.
- `ext4`: tipus de sistema d’arxius.
- `defaults`: opcions per defecte.
- `0`: no activa còpia de seguretat.
- `2`: revisió després del sistema principal.

**On surt:** bloc06.md, diapositives 22, 23, 24, 26 i 27.

---

### d. `sudo mount -a`, `/etc/mtab` i `/etc/fstab`

```bash
sudo mount -a
```

**Explicació:**

`sudo mount -a` munta tots els sistemes definits a `/etc/fstab`. És útil després d’editar `/etc/fstab` perquè permet comprovar la configuració abans de reiniciar.

Diferència:

- `/etc/mtab`: mostra què està muntat ara mateix.
- `/etc/fstab`: indica què s’ha de muntar automàticament i és una configuració permanent.

**On surt:** bloc06.md, diapositives 12, 20, 21 i 30.


