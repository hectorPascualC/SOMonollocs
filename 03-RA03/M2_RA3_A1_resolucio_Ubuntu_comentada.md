# M02 – RA3 – Activitat 1
## Resolució comentada només per Ubuntu

---

## Índex

- [Fase 1 — Primeres configuracions](#fase-1--primeres-configuracions)
  - [1. Comprovar la versió del sistema operatiu](#1-comprovar-la-versió-del-sistema-operatiu)
  - [2. Identificar els usuaris existents](#2-identificar-els-usuaris-existents)
  - [3. Crear un nou usuari amb permisos d’administració](#3-crear-un-nou-usuari-amb-permisos-dadministració)
  - [4. Canviar entre usuaris i verificar privilegis](#4-canviar-entre-usuaris-i-verificar-privilegis)
- [Fase 2 — Gestió de fitxers i directoris](#fase-2--gestió-de-fitxers-i-directoris)
  - [1. Crear una estructura de directoris](#1-crear-una-estructura-de-directoris)
  - [2. Crear i editar un fitxer de text](#2-crear-i-editar-un-fitxer-de-text)
  - [3. Copiar, moure i esborrar fitxers](#3-copiar-moure-i-esborrar-fitxers)
  - [4. Llistar contingut i verificar permisos](#4-llistar-contingut-i-verificar-permisos)
- [Fase 3 — Administració del sistema](#fase-3--administració-del-sistema)
  - [1. Comprovar processos actius](#1-comprovar-processos-actius)
  - [2. Gestionar serveis del sistema](#2-gestionar-serveis-del-sistema)
  - [3. Monitoritzar l’ús del disc i la RAM](#3-monitoritzar-lús-del-disc-i-la-ram)
  - [4. Gestionar usuaris i permisos](#4-gestionar-usuaris-i-permisos)
- [Fase 4 — Xarxa i connexió remota](#fase-4--xarxa-i-connexió-remota)
  - [1. Comprovar la configuració de xarxa](#1-comprovar-la-configuració-de-xarxa)
  - [2. Fer un ping a un altre servidor](#2-fer-un-ping-a-un-altre-servidor)
  - [3. Connectar-se per SSH a una altra màquina](#3-connectar-se-per-ssh-a-una-altra-màquina)
- [Apunts extres útils](#apunts-extres-útils)
  - [Com detectar usuaris reals humans](#com-detectar-usuaris-reals-humans)
  - [Què és un paquet `.deb`](#què-és-un-paquet-deb)
  - [Com interpretar una línia de `/etc/passwd`](#com-interpretar-una-línia-de-etcpasswd)
  - [Resum final d’ordres utilitzades](#resum-final-dordres-utilitzades)

---

# Fase 1 — Primeres configuracions

## 1. Comprovar la versió del sistema operatiu

```bash
lsb_release -a
uname -r
cat /etc/os-release
```

### `lsb_release -a`

**Què fa**  
Mostra informació sobre la distribució Linux instal·lada.

**Què vol dir la comanda**
- `lsb` = **Linux Standard Base**
- `release` = versió o edició

Per tant, `lsb_release` vol dir, aproximadament:

> mostrar la informació estàndard de versió de la distribució Linux.

**Què vol dir l’opció**
- `-a` = **all**

Vol dir que mostri **tota** la informació disponible.

**Què acostuma a mostrar**
- distribuïdor
- descripció
- versió
- nom en clau

---

### `uname -r`

**Què fa**  
Mostra la versió del nucli del sistema.

**Què vol dir la comanda**
- `u` = Unix
- `name` = nom

Històricament, `uname` significa:

> mostrar informació del sistema tipus Unix.

**Què vol dir l’opció**
- `-r` = **release**

Mostra la versió del **kernel** o nucli.

**Idea clau**  
Això no diu tant la versió d’Ubuntu com la versió del **nucli Linux**.

---

### `cat /etc/os-release`

**Què fa**  
Mostra el contingut del fitxer `/etc/os-release`.

**Què vol dir la comanda**
- `cat` = **concatenate**

Originalment servia per concatenar fitxers, però molt sovint s’utilitza simplement per **mostrar el contingut** d’un fitxer.

**Què és `/etc/os-release`**
- `/etc` = directori de configuració del sistema
- `os` = **operating system**
- `release` = versió

Aquest fitxer conté informació identificativa del sistema operatiu.

### Exemple d’interpretació de `/etc/os-release`

Si surt això:

```text
PRETTY_NAME="Ubuntu 24.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.3 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo
```

vol dir:

- `PRETTY_NAME` = nom complet “bonic” del sistema
- `NAME` = nom curt de la distribució
- `VERSION_ID` = identificador curt de versió
- `VERSION` = versió completa
- `VERSION_CODENAME` = nom en clau de la versió
- `ID` = identificador intern del sistema
- `ID_LIKE` = sistema en què es basa o al qual s’assembla
- `HOME_URL` = web principal
- `SUPPORT_URL` = web de suport
- `BUG_REPORT_URL` = pàgina per reportar errors
- `PRIVACY_POLICY_URL` = política de privacitat
- `UBUNTU_CODENAME` = nom en clau específic d’Ubuntu
- `LOGO` = nom intern del logotip

> **LTS** = **Long Term Support** = versió amb suport a llarg termini.

---

## 2. Identificar els usuaris existents

```bash
cut -d: -f1 /etc/passwd
getent passwd
```

### `cut -d: -f1 /etc/passwd`

**Què fa**  
Extreu només el primer camp de cada línia del fitxer `/etc/passwd`, que correspon al nom d’usuari.

**Què vol dir la comanda**
- `cut` = tallar

Serveix per tallar parts d’un text per camps.

**Què volen dir les opcions**
- `-d:` = **delimiter**
  - `d` = **delimiter**
  - indica que el separador és `:`
- `-f1` = **field 1**
  - `f` = **field**
  - indica que vols el camp 1

**Què és `/etc/passwd`**  
És el fitxer on el sistema guarda informació bàsica dels usuaris.

**Per què surt una llista tan llarga?**  
Perquè aquí **no només hi ha usuaris humans**. També hi ha:
- usuaris del sistema
- comptes interns
- usuaris de serveis
- comptes de daemons

Per això hi surten noms com:
- `www-data`
- `syslog`
- `sshd`
- `gdm`
- `cups-browsed`
- `libvirt-qemu`

Aquests **no són persones**, sinó comptes tècnics que utilitzen serveis del sistema.

---

### `getent passwd`

**Què fa**  
Mostra la base de dades d’usuaris completa.

**Què vol dir la comanda**
- `get` = obtenir
- `ent` = **entries** (entrades)

Vol dir:

> obtenir les entrades d’una base de dades del sistema.

**Què vol dir `passwd` aquí**  
Aquí no vol dir “canviar contrasenya”, sinó consultar la base de dades d’usuaris anomenada `passwd`.

**Diferència entre les dues comandes**
- `cut -d: -f1 /etc/passwd` → mostra només els noms d’usuari
- `getent passwd` → mostra totes les línies completes

---

## 3. Crear un nou usuari amb permisos d’administració

```bash
sudo adduser alumne4
sudo usermod -aG sudo alumne4
groups alumne4
id alumne4
```

### `sudo adduser alumne4`

**Què fa**  
Crea un usuari nou anomenat `alumne4`.

**Què vol dir `sudo`**
- `su` = **substitute user** o **superuser**
- `do` = fer

Vol dir:

> executar una ordre amb permisos d’administrador.

**Què vol dir `adduser`**
- `add` = afegir
- `user` = usuari

És una ordre d’alt nivell per crear usuaris de manera guiada.

**Què passa normalment quan es crea un usuari nou?**  
A Ubuntu, quan fas `adduser`, **normalment també es crea un grup principal amb el mateix nom** que l’usuari.

Per exemple, si crees `alumne4`, el més habitual és que es creï també:
- usuari: `alumne4`
- grup principal: `alumne4`

---

### `sudo usermod -aG sudo alumne4`

**Què fa**  
Afegeix l’usuari `alumne4` al grup `sudo`, és a dir, li dona permisos administratius.

**Què vol dir `usermod`**
- `user` = usuari
- `mod` = **modify**

Vol dir:

> modificar un usuari existent.

**Què volen dir les opcions**
- `-a` = **append**
  - afegeix sense esborrar altres grups
- `-G` = **groups**
  - permet indicar grups suplementaris

**Què significa `sudo` en aquesta ordre**  
Aquí `sudo` **no és la comanda**, sinó el **nom del grup**.

---

### `groups alumne4`

**Què fa**  
Mostra els grups als quals pertany l’usuari `alumne4`.

**Què vol dir**
- `groups` = grups

Serveix per comprovar si realment forma part de `sudo`.

---

### `id alumne4`

**Què fa**  
Mostra la identitat completa de l’usuari.

**Què vol dir `id`**
- `id` = **identity**

**Què acostuma a mostrar**
- `uid` = **User ID**
- `gid` = **Group ID**
- `groups` = grups als quals pertany

Exemple típic:

```text
uid=1001(alumne4) gid=1001(alumne4) groups=1001(alumne4),27(sudo)
```

Això indica que:
- l’usuari és `alumne4`
- el grup principal també és `alumne4`
- a més, pertany al grup `sudo`

---

## 4. Canviar entre usuaris i verificar privilegis

```bash
su - alumne4
whoami
id
sudo -l
```

### `su - alumne4`

**Què fa**  
Canvia a l’usuari `alumne4`.

**Què vol dir `su`**
- `su` = **substitute user**

Vol dir:

> canviar a un altre usuari.

**Què vol dir `-`**  
Aquest guió fa que es carregui l’entorn complet del nou usuari, com si hagués iniciat sessió de veritat.

---

### `whoami`

**Què fa**  
Mostra quin usuari ets en aquest moment.

**Què vol dir**
- `who` = qui
- `am` = sóc
- `I` = jo

Literalment:

> qui sóc jo?

---

### `id`

**Què fa**  
Mostra la identitat de l’usuari actual.

**Què mostra**
- UID
- GID
- grups

Això és útil per comprovar si l’usuari realment està dins del grup `sudo`.

---

### `sudo -l`

**Què fa**  
Mostra quines ordres pot executar l’usuari amb `sudo`.

**Què vol dir l’opció**
- `-l` = **list**

És a dir, llistar els permisos de `sudo`.

---

# Fase 2 — Gestió de fitxers i directoris

## 1. Crear una estructura de directoris

```bash
mkdir -p practica/docs practica/copies practica/logs
ls -R practica
```

### `mkdir -p practica/docs practica/copies practica/logs`

**Què fa**  
Crea diversos directoris alhora.

**Què vol dir `mkdir`**
- `mk` = **make**
- `dir` = **directory**

Vol dir:

> crear directoris.

**Què vol dir `-p`**
- `p` = **parents**

Fa dues coses útils:
- crea també els directoris pare si cal
- no dona error si algun directori ja existeix

**Què es crea aquí**
- `practica`
- `practica/docs`
- `practica/copies`
- `practica/logs`

---

### `ls -R practica`

**Què fa**  
Mostra el contingut del directori `practica` i de totes les seves subcarpetes.

**Què vol dir `ls`**
- `ls` = **list**

**Què vol dir `-R`**
- `R` = **recursive**

Vol dir: mostrar-ho de manera recursiva.

---

## 2. Crear i editar un fitxer de text

```bash
touch practica/docs/notes.txt
nano practica/docs/notes.txt
cat practica/docs/notes.txt
```

Alternativa ràpida:

```bash
echo "Això és una prova de la pràctica RA3" > practica/docs/notes.txt
```

### `touch practica/docs/notes.txt`

**Què fa**  
Crea un fitxer buit si no existeix.

**Què vol dir `touch`**  
Originalment vol dir “tocar” un fitxer, és a dir, actualitzar-ne la marca de temps.

Si el fitxer no existeix, el crea.

---

### `nano practica/docs/notes.txt`

**Què fa**  
Obre el fitxer amb l’editor de text `nano`.

**Què és `nano`**  
És un editor de text senzill per a terminal.

Permet:
- escriure text
- modificar-lo
- guardar-lo des de la línia d’ordres

---

### `cat practica/docs/notes.txt`

**Què fa**  
Mostra el contingut del fitxer per pantalla.

**Què vol dir `cat`**
- `cat` = **concatenate**

En aquest cas, s’utilitza simplement per llegir el fitxer.

---

### `echo "..." > practica/docs/notes.txt`

**Què fa**  
Escriu un text dins del fitxer.

**Què vol dir `echo`**
- `echo` = repetir o mostrar per pantalla

**Què vol dir `>`**  
És una redirecció.

Vol dir:
- enviar la sortida a un fitxer
- si el fitxer no existeix, el crea
- si existeix, el sobreescriu

---

## 3. Copiar, moure i esborrar fitxers

```bash
cp practica/docs/notes.txt practica/copies/notes_copia.txt
mv practica/copies/notes_copia.txt practica/logs/
rm practica/logs/notes_copia.txt
```

### `cp origen destí`

**Què fa**  
Copia un fitxer.

**Què vol dir `cp`**
- `cp` = **copy**

En aquest cas:
- origen = `practica/docs/notes.txt`
- destí = `practica/copies/notes_copia.txt`

Això crea una còpia amb un altre nom.

---

### `mv origen destí`

**Què fa**  
Mou o canvia de nom fitxers i carpetes.

**Què vol dir `mv`**
- `mv` = **move**

Aquí mou el fitxer a la carpeta `logs`.

---

### `rm fitxer`

**Què fa**  
Elimina el fitxer indicat.

**Què vol dir `rm`**
- `rm` = **remove**

> Compte: `rm` esborra fitxers i, si no hi ha paperera al terminal, la supressió és directa.

---

## 4. Llistar contingut i verificar permisos

```bash
ls -l practica/docs
stat practica/docs/notes.txt
```

### `ls -l practica/docs`

**Què fa**  
Mostra el contingut de la carpeta en format llarg.

**Què vol dir `-l`**
- `l` = **long**

Mostra més informació:
- permisos
- nombre d’enllaços
- propietari
- grup
- mida
- data
- nom

---

### `stat practica/docs/notes.txt`

**Què fa**  
Mostra informació detallada d’un fitxer.

**Què vol dir `stat`**
- `stat` = estat

Mostra dades com:
- mida exacta
- tipus de fitxer
- permisos
- inode
- dates d’accés, modificació i canvi

---

# Fase 3 — Administració del sistema

## 1. Comprovar processos actius

```bash
ps aux
top
```

### `ps aux`

**Què fa**  
Mostra una llista de processos en execució.

**Què vol dir `ps`**
- `ps` = **process status**

**Què volen dir les opcions**
- `a` = processos de tots els usuaris amb terminal
- `u` = format orientat a usuari, amb més columnes
- `x` = inclou processos sense terminal associat

Això permet veure pràcticament tots els processos actius.

---

### `top`

**Què fa**  
Mostra els processos en temps real.

**Què vol dir `top`**  
No és ben bé una abreviació; es refereix a veure els processos “de dalt”, és a dir, destacant els que més recursos consumeixen.

**Què permet veure**
- ús de CPU
- ús de RAM
- càrrega del sistema
- processos en viu

Per sortir-ne, prem `q`.

---

## 2. Gestionar serveis del sistema

```bash
systemctl status ssh
sudo systemctl start ssh
sudo systemctl stop ssh
sudo systemctl restart ssh
sudo systemctl enable ssh
```

### `systemctl status ssh`

**Què fa**  
Mostra l’estat del servei `ssh`.

**Què vol dir `systemctl`**
- `system` = sistema
- `ctl` = **control**

Vol dir:

> controlar serveis i unitats gestionats per `systemd`.

**Què vol dir `status`**  
Mostra l’estat actual del servei.

**Què és `ssh`**
- `ssh` = **Secure Shell**

És el servei que permet connexions remotes segures.

---

### `sudo systemctl start ssh`

**Què fa**  
Inicia el servei `ssh`.

**Què vol dir `start`**  
Arrencar o iniciar el servei.

---

### `sudo systemctl stop ssh`

**Què fa**  
Atura el servei `ssh`.

**Què vol dir `stop`**  
Parar o aturar el servei.

---

### `sudo systemctl restart ssh`

**Què fa**  
Reinicia el servei `ssh`.

**Què vol dir `restart`**  
Aturar-lo i tornar-lo a iniciar.

---

### `sudo systemctl enable ssh`

**Què fa**  
Fa que el servei s’iniciï automàticament en arrencar el sistema.

**Què vol dir `enable`**  
Activar a l’inici.

---

## 3. Monitoritzar l’ús del disc i la RAM

```bash
df -h
du -sh practica
free -h
```

### `df -h`

**Què fa**  
Mostra l’espai ocupat i lliure dels sistemes de fitxers.

**Què vol dir `df`**
- `df` = **disk free**

**Què vol dir `-h`**
- `h` = **human-readable**

Vol dir: mostrar-ho en format fàcil de llegir, com KB, MB o GB.

---

### `du -sh practica`

**Què fa**  
Mostra quant espai ocupa la carpeta `practica`.

**Què vol dir `du`**
- `du` = **disk usage**

**Què volen dir les opcions**
- `-s` = **summary**
  - mostra només el resum final
- `-h` = **human-readable**
  - mostra el resultat de manera llegible

---

### `free -h`

**Què fa**  
Mostra la memòria RAM i l’espai d’intercanvi (swap).

**Què vol dir `free`**  
Fa referència a la memòria disponible o lliure.

**Què vol dir `-h`**
- `h` = **human-readable**

---

## 4. Gestionar usuaris i permisos

```bash
sudo chown alumne4:alumne4 practica/docs/notes.txt
chmod 640 practica/docs/notes.txt
sudo passwd alumne4
sudo usermod -L alumne4
sudo usermod -U alumne4
```

### `sudo chown alumne4:alumne4 practica/docs/notes.txt`

**Què fa**  
Canvia el propietari i el grup del fitxer.

**Què vol dir `chown`**
- `ch` = **change**
- `own` = **owner**

Vol dir:

> canviar propietari.

**Què significa `alumne4:alumne4`**
- primer `alumne4` = nou propietari
- segon `alumne4` = nou grup

---

### `chmod 640 practica/docs/notes.txt`

**Què fa**  
Canvia els permisos del fitxer.

**Què vol dir `chmod`**
- `ch` = **change**
- `mod` = **mode**

Vol dir:

> canviar el mode o els permisos.

**Què vol dir `640`**
- `6` = propietari → lectura (`4`) + escriptura (`2`) = `6`
- `4` = grup → només lectura
- `0` = altres → cap permís

**Equivalència**
- `r` = read = lectura = `4`
- `w` = write = escriptura = `2`
- `x` = execute = execució = `1`

---

### `sudo passwd alumne4`

**Què fa**  
Canvia la contrasenya de l’usuari `alumne4`.

**Què vol dir `passwd`**
- `pass` = password
- `wd` = word

Històricament fa referència a **password**.

---

### `sudo usermod -L alumne4`

**Què fa**  
Bloqueja el compte de l’usuari.

**Què vol dir `-L`**
- `L` = **lock**

---

### `sudo usermod -U alumne4`

**Què fa**  
Desbloqueja el compte.

**Què vol dir `-U`**
- `U` = **unlock**

---

# Fase 4 — Xarxa i connexió remota

## 1. Comprovar la configuració de xarxa

```bash
ip a
ip route
hostname -I
```

### `ip a`

**Què fa**  
Mostra les interfícies de xarxa i les seves adreces IP.

**Què vol dir `ip`**  
És l’eina moderna de Linux per gestionar configuració de xarxa.

**Què vol dir `a`**
- `a` = **address**

Mostra les adreces IP de cada interfície.

---

### `ip route`

**Què fa**  
Mostra la taula d’encaminament.

**Què vol dir `route`**  
Ruta o encaminament.

Permet veure:
- la passarel·la per defecte
- les rutes cap a altres xarxes

---

### `hostname -I`

**Què fa**  
Mostra les adreces IP del sistema.

**Què vol dir `hostname`**
- `host` = host o màquina
- `name` = nom

**Què vol dir `-I`**
- `I` = adreces IP associades al sistema

---

## 2. Fer un ping a un altre servidor

```bash
ping -c 4 8.8.8.8
```

### `ping -c 4 8.8.8.8`

**Què fa**  
Comprova si hi ha connectivitat de xarxa amb la destinació indicada.

**Què és `ping`**  
És una utilitat que envia paquets ICMP per comprovar si un host respon.

**Què vol dir `-c 4`**
- `c` = **count**

Vol dir: enviar només **4** paquets.

**Què és `8.8.8.8`**  
És la IP de destinació. Sovint s’utilitza com a exemple perquè és pública i coneguda.

---

## 3. Connectar-se per SSH a una altra màquina

```bash
ssh usuari@192.168.1.50
```

### `ssh usuari@192.168.1.50`

**Què fa**  
Obre una connexió remota segura a una altra màquina.

**Què vol dir `ssh`**
- `ssh` = **Secure Shell**

És el protocol i l’eina de connexió remota segura.

**Què significa `usuari@192.168.1.50`**
- `usuari` = usuari remot
- `@` = separa usuari i host
- `192.168.1.50` = IP de la màquina remota

La primera vegada, normalment demana confirmar l’empremta o clau del servidor.

---

### Si no hi ha servidor SSH instal·lat

```bash
sudo apt update
sudo apt install openssh-server
systemctl status ssh
```

#### `sudo apt update`

**Què fa**  
Actualitza la llista de paquets disponibles.

**Què vol dir `apt`**
- `apt` = **Advanced Package Tool**

**Què vol dir `update`**  
Actualitzar la informació dels paquets disponibles.

---

#### `sudo apt install openssh-server`

**Què fa**  
Instal·la el servidor SSH.

**Què vol dir `install`**  
Instal·lar un paquet.

**Què és `openssh-server`**
- `OpenSSH` = implementació oberta d'SSH
- `server` = component servidor

---

# Apunts extres útils

## Com detectar usuaris reals humans

En Linux **no hi ha una marca perfecta** que digui “aquest usuari és humà”, però normalment es fa servir una combinació de pistes:

1. **UID alt**  
   A Ubuntu, els usuaris humans solen tenir **UID 1000 o superior**.

2. **Shell real**  
   Els usuaris humans solen tenir una shell com:
   - `/bin/bash`
   - `/bin/sh`
   - `/bin/zsh`

   En canvi, molts comptes del sistema tenen:
   - `/usr/sbin/nologin`
   - `/bin/false`

3. **Carpeta personal real**  
   Els usuaris humans solen tenir una carpeta personal dins de `/home`.

### Comanda pràctica per detectar-los

```bash
awk -F: '$3 >= 1000 && $7 !~ /(nologin|false)$/ {print $1}' /etc/passwd
```

### Explicació
- `awk` = eina per processar text per camps
- `-F:` = separador `:`
- `$3` = camp 3 = UID
- `$7` = camp 7 = shell
- `!~` = no coincideix amb el patró
- `{print $1}` = mostra el camp 1, és a dir, el nom d’usuari

Això selecciona usuaris que:
- tenen UID `>= 1000`
- no acaben amb `nologin` ni `false`

---

## Què és un paquet `.deb`

Els paquets `.deb` són els fitxers d’instal·lació de programes típics de **Debian** i **Ubuntu**.

### Idea simple
Un fitxer `.deb` conté:
- el programa
- fitxers necessaris
- metadades
- instruccions d’instal·lació

### Exemple
```text
google-chrome-stable_current_amd64.deb
```

### Eines relacionades
- `dpkg` = gestor bàsic de paquets `.deb`
- `apt` = gestor més còmode que també resol dependències

---

## Com interpretar una línia de `/etc/passwd`

Exemple:

```text
hector:x:1000:1000:hector:/home/hector:/bin/bash
```

### Camps
1. `hector` → nom d’usuari  
2. `x` → la contrasenya es guarda en un altre fitxer segur  
3. `1000` → **UID** = User ID  
4. `1000` → **GID** = Group ID  
5. `hector` → comentari o descripció  
6. `/home/hector` → carpeta personal  
7. `/bin/bash` → shell d’inici de sessió

---

## Resum final d’ordres utilitzades

```bash
# Fase 1
lsb_release -a
uname -r
cat /etc/os-release
cut -d: -f1 /etc/passwd
getent passwd
sudo adduser alumne4
sudo usermod -aG sudo alumne4
groups alumne4
id alumne4
su - alumne4
whoami
id
sudo -l

# Fase 2
mkdir -p practica/docs practica/copies practica/logs
ls -R practica
touch practica/docs/notes.txt
nano practica/docs/notes.txt
cat practica/docs/notes.txt
echo "Això és una prova de la pràctica RA3" > practica/docs/notes.txt
cp practica/docs/notes.txt practica/copies/notes_copia.txt
mv practica/copies/notes_copia.txt practica/logs/
rm practica/logs/notes_copia.txt
ls -l practica/docs
stat practica/docs/notes.txt

# Fase 3
ps aux
top
systemctl status ssh
sudo systemctl start ssh
sudo systemctl stop ssh
sudo systemctl restart ssh
sudo systemctl enable ssh
df -h
du -sh practica
free -h
sudo chown alumne4:alumne4 practica/docs/notes.txt
chmod 640 practica/docs/notes.txt
sudo passwd alumne4
sudo usermod -L alumne4
sudo usermod -U alumne4

# Fase 4
ip a
ip route
hostname -I
ping -c 4 8.8.8.8
ssh usuari@192.168.1.50
sudo apt update
sudo apt install openssh-server
systemctl status ssh
```
