---
marp: true
paginate: true
theme: default

header: "RA04 – Administració bàsica de sistemes operatius · Bloc 4 – Grups d'usuaris i perfils a GNU/Linux"
footer: "Mòdul 0222 – SO Monolloc"

style: |
    header, footer {
        display: block;
        width: 100vw;
        font-size: .45rem;
        color: #bbbbbcff;
        z-index: 10;
    }
    header { text-align: right !important; padding-right: 50px; }
---

<!-- SLIDE 1 -->
# **RA04 – Bloc 4**
## **Grups d'usuaris i perfils a GNU/Linux**

**SMX01 - Sistemes Operatius Monolloc**  
**Professor - Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **Què treballarem en aquest bloc**

Aquest bloc se centra en:

- què són els **grups d'usuaris** a GNU/Linux  
- diferència entre **grup principal** i **grups secundaris**  
- fitxer de configuració `/etc/group`  
- ordres bàsiques per gestionar grups  
- comprovació de grups amb `id`, `groups` i `whoami`  
- perfils d'usuari i ús del directori `/etc/skel`

Objectiu: entendre com Linux organitza usuaris amb permisos comuns i com prepara l'entorn inicial d'un compte nou

---

<!-- SLIDE 3 -->
# 🔸 **Per què existeixen els grups?**

Els grups permeten organitzar usuaris que comparteixen una mateixa necessitat.

Per exemple:

- alumnes d'un mateix projecte  
- usuaris que poden accedir a una carpeta  
- personal administratiu  
- usuaris amb permisos especials  
- serveis del sistema que necessiten accés a recursos concrets

Idea clau: és més fàcil donar permisos a un **grup** que configurar permisos usuari per usuari.

---

<!-- SLIDE 4 -->
# 🔸 **Què és un grup d'usuaris?**

Un grup és una col·lecció d'usuaris amb privilegis o rols comuns.

A GNU/Linux:

- cada grup té un **nom**  
- cada grup té un identificador numèric: **GID**  
- un usuari pot pertànyer a **més d'un grup**  
- els permisos es poden aplicar sobre usuaris i grups

Els grups són una peça bàsica del sistema de permisos.

---

<!-- SLIDE 5 -->
# 🔸 **Usuari i grup per defecte**

En molts sistemes GNU/Linux, quan es crea un usuari també es crea un grup amb el mateix nom.

Exemple:

```text
usuari: alumne1
grup:   alumne1
```

Aquest grup acostuma a ser el **grup principal** de l'usuari.

Això ajuda a separar els fitxers personals de cada compte.

---

<!-- SLIDE 6 -->
# 🔸 **Grup principal i grups secundaris**

Un usuari pot tenir:

- **grup principal**  
  → grup associat per defecte a l'usuari

- **grups secundaris**  
  → grups addicionals que donen permisos extra

Exemple:

```text
alumne1 → grup principal: alumne1
alumne1 → grups secundaris: projecte1, samba, audio
```

---

<!-- SLIDE 7 -->
# 🔸 **Per a què serveixen els grups secundaris?**

Els grups secundaris permeten donar accés a recursos compartits.

Exemples:

- accedir a una carpeta de projecte  
- tenir permisos sobre un dispositiu  
- poder utilitzar un servei concret  
- compartir fitxers amb altres usuaris

En administració de sistemes, els grups secundaris són molt útils per aplicar permisos sense canviar el compte principal de l'usuari.

---

<!-- SLIDE 8 -->
# 🔸 **On es guarden els grups?**

El fitxer principal és:

```bash
/etc/group
```

Aquest fitxer conté:

- la llista de grups del sistema  
- el GID de cada grup  
- els usuaris que pertanyen a cada grup com a membres addicionals

Cada línia representa un grup.

---

<!-- SLIDE 9 -->
# 🔸 **Estructura de `/etc/group`**

Cada línia del fitxer `/etc/group` té camps separats per dos punts:

```text
nom_grup:contrasenya:GID:llista_usuaris
```

Exemple:

```text
projecte1:x:1005:anna,joan
```

Això indica que el grup `projecte1` té el GID `1005` i inclou els usuaris `anna` i `joan`.

---

<!-- SLIDE 10 -->
# 🔸 **Camps de `/etc/group`**

Els camps són:

1. **nom del grup**  
   → identificador textual del grup

2. **contrasenya**  
   → normalment apareix com `x` o queda buit

3. **GID**  
   → identificador numèric del grup

4. **llista d'usuaris**  
   → membres addicionals separats per comes

---

<!-- SLIDE 11 -->
# 🔸 **Compte amb la llista d'usuaris**

A `/etc/group`, la llista final mostra els membres addicionals del grup.

Però un usuari pot tenir aquest grup com a **grup principal** i no aparèixer a la llista.

Per això, per comprovar els grups d'un usuari és millor utilitzar:

```bash
id usuari
groups usuari
```

No n'hi ha prou amb mirar només `/etc/group`.

---

<!-- SLIDE 12 -->
# 🔸 **Crear grups amb `groupadd`**

Per crear un grup nou:

```bash
sudo groupadd nom_grup
```

Exemple:

```bash
sudo groupadd projecte1
```

També es pot assignar un GID concret:

```bash
sudo groupadd -g 1500 projecte1
```

---

<!-- SLIDE 13 -->
# 🔸 **Modificar grups amb `groupmod`**

Per modificar un grup existent:

```bash
sudo groupmod [opcions] nom_grup
```

Opcions habituals:

- `-g` → canvia el GID  
- `-n` → canvia el nom del grup

Exemples:

```bash
sudo groupmod -n projecte_linux projecte1
sudo groupmod -g 1600 projecte_linux
```

---

<!-- SLIDE 14 -->
# 🔸 **Eliminar grups amb `groupdel`**

Per eliminar un grup:

```bash
sudo groupdel nom_grup
```

Exemple:

```bash
sudo groupdel projecte1
```

Abans d'eliminar un grup cal revisar:

- si hi ha usuaris que encara el fan servir  
- si hi ha fitxers que tenen aquest grup com a propietari  
- si algun servei depèn d'aquest grup

---

<!-- SLIDE 15 -->
# 🔸 **Afegir usuaris a un grup amb `gpasswd`**

Per afegir un usuari a un grup:

```bash
sudo gpasswd -a usuari nom_grup
```

Exemple:

```bash
sudo gpasswd -a anna projecte1
```

Per eliminar un usuari d'un grup:

```bash
sudo gpasswd -d anna projecte1
```

---

<!-- SLIDE 16 -->
# 🔸 **Afegir usuaris a grups amb `usermod`**

També es pot fer amb `usermod`:

```bash
sudo usermod -aG nom_grup usuari
```

Exemple:

```bash
sudo usermod -aG projecte1 anna
```

La combinació `-aG` és important:

- `-G` indica grups secundaris  
- `-a` evita perdre els grups secundaris que l'usuari ja tenia

---

<!-- SLIDE 17 -->
# 🔸 **Error habitual amb `usermod`**

Compte amb aquesta ordre:

```bash
sudo usermod -G projecte1 anna
```

Sense `-a`, pot substituir la llista de grups secundaris de l'usuari.

Forma recomanada:

```bash
sudo usermod -aG projecte1 anna
```

Idea clau: quan afegim un usuari a un grup nou, normalment volem **afegir**, no reemplaçar.

---

<!-- SLIDE 18 -->
# 🔸 **Comprovar el grup d'un usuari**

Ordres útils:

```bash
whoami
groups
id
```

També podem consultar un usuari concret:

```bash
groups anna
id anna
```

Aquestes ordres ajuden a verificar si els canvis s'han aplicat correctament.

---

<!-- SLIDE 19 -->
# 🔸 **Quan s'apliquen els canvis de grup?**

Quan afegim un usuari a un grup, pot ser necessari tancar sessió i tornar a entrar.

Això passa perquè els grups de la sessió es carreguen en iniciar sessió.

Seqüència recomanada:

1. afegir l'usuari al grup  
2. tancar sessió  
3. iniciar sessió de nou  
4. comprovar amb `id` o `groups`

---

<!-- SLIDE 20 -->
# 🔸 **Exemple complet de grup de projecte**

Crear un grup i afegir-hi dos usuaris:

```bash
sudo groupadd projecte1
sudo usermod -aG projecte1 anna
sudo usermod -aG projecte1 joan
```

Comprovar-ho:

```bash
id anna
id joan
getent group projecte1
```

`getent group` permet consultar la informació del grup de manera directa.

---

<!-- SLIDE 21 -->
# 🔸 **Grups i permisos**

Els grups tenen sentit quan els combinem amb permisos.

Exemple:

```bash
sudo mkdir /srv/projecte1
sudo chgrp projecte1 /srv/projecte1
sudo chmod 770 /srv/projecte1
```

Això permet que:

- el propietari tingui permisos  
- el grup `projecte1` tingui permisos  
- la resta d'usuaris no tingui accés

---

<!-- SLIDE 22 -->
# 🔸 **Recordatori de permisos bàsics**

En GNU/Linux, els permisos s'apliquen a tres nivells:

```text
usuari propietari | grup propietari | altres usuaris
```

I poden ser:

- `r` → lectura  
- `w` → escriptura  
- `x` → execució o accés a directori

Exemple:

```text
drwxrwx---
```

---

<!-- SLIDE 23 -->
# 🔸 **Setgid en directoris compartits**

En carpetes compartides per grup, és habitual utilitzar el bit **setgid**.

Exemple:

```bash
sudo chmod 2770 /srv/projecte1
```

El `2` inicial fa que els fitxers nous creats dins la carpeta mantinguin el grup propietari del directori.

Això és útil quan diversos usuaris treballen dins una mateixa carpeta de projecte.

---

<!-- SLIDE 24 -->
# 🔸 **No confondre setgid i sticky bit**

`chmod 2770` aplica **setgid**, no sticky bit.

Diferència ràpida:

- **setgid en directori**  
  → els fitxers nous hereten el grup del directori

- **sticky bit**  
  → impedeix que un usuari elimini fitxers d'altres usuaris en directoris compartits

Exemple típic de sticky bit:

```bash
/tmp
```

---

<!-- SLIDE 25 -->
# 🔸 **Altres ordres útils**

Ordres relacionades amb usuaris i grups:

```bash
whoami
who
groups
id
login
chage
chsh
chfn
```

Serveixen per:

- saber quin usuari està actiu  
- veure sessions obertes  
- consultar grups i identificadors  
- gestionar caducitat de contrasenyes  
- modificar shell o dades personals

---

<!-- SLIDE 26 -->
# 🔸 **Què és un perfil d'usuari a GNU/Linux?**

Quan un usuari inicia sessió, el sistema prepara el seu entorn de treball.

Això inclou:

- directori personal `/home/usuari`  
- fitxers de configuració  
- preferències del shell  
- variables i scripts d'inici  
- configuracions personals

Aquest conjunt forma part del perfil de l'usuari.

---

<!-- SLIDE 27 -->
# 🔸 **El directori `/home`**

Cada usuari normal acostuma a tenir un directori dins de `/home`.

Exemple:

```text
/home/anna
/home/joan
/home/alumne1
```

Aquest directori conté:

- documents personals  
- configuracions ocultes  
- preferències d'aplicacions  
- fitxers propis de l'usuari

---

<!-- SLIDE 28 -->
# 🔸 **Què és `/etc/skel`?**

`/etc/skel` és el directori plantilla per als nous usuaris.

Conté una estructura mínima comuna que es copia al directori personal quan es crea un compte nou.

Exemple:

```bash
ls -la /etc/skel
```

Si es crea un usuari amb directori personal, el sistema pot copiar-hi aquests fitxers inicials.

---

<!-- SLIDE 29 -->
# 🔸 **Fitxers típics dins `/etc/skel`**

Fitxers habituals:

- `.bashrc`  
  → configura el shell interactiu

- `.bash_logout`  
  → s'executa en tancar sessió

- `.profile` o `.bash_profile`  
  → configura l'entorn en iniciar sessió

Són fitxers ocults perquè comencen amb punt.

---

<!-- SLIDE 30 -->
# 🔸 **Per què és útil `/etc/skel`?**

Permet preparar tots els usuaris nous amb una base comuna.

Exemples d'ús:

- afegir un fitxer de benvinguda  
- crear carpetes inicials  
- deixar scripts preparats  
- configurar variables d'entorn  
- aplicar una estructura comuna en un centre educatiu

Això ajuda a estandarditzar els comptes nous.

---

<!-- SLIDE 31 -->
# 🔸 **Exemple amb `/etc/skel`**

Afegir un fitxer de benvinguda:

```bash
sudo nano /etc/skel/.benvinguda.txt
```

Crear un usuari nou:

```bash
sudo useradd -m -s /bin/bash alumne2
sudo passwd alumne2
```

Comprovar el resultat:

```bash
ls -la /home/alumne2
```

El nou usuari hauria de rebre el fitxer `.benvinguda.txt`.

---

<!-- SLIDE 32 -->
# 🔸 **Canviar la plantilla per defecte**

La configuració de creació d'usuaris es pot consultar a:

```bash
/etc/default/useradd
```

Aquest fitxer pot indicar quin directori s'utilitza com a plantilla.

La plantilla habitual és:

```bash
/etc/skel
```

Això permet modificar el comportament inicial dels nous comptes.

---

<!-- SLIDE 33 -->
# 🔸 **Seqüència recomanada de treball**

Per treballar amb grups i perfils:

1. crear el grup necessari  
2. afegir-hi els usuaris  
3. tancar i iniciar sessió si cal  
4. comprovar amb `id` o `groups`  
5. preparar carpetes i permisos  
6. revisar `/etc/skel` si cal crear usuaris nous amb plantilla

Treballar per fases evita errors i facilita la documentació.

---

<!-- SLIDE 34 -->
# 🔸 **Errors habituals**

Errors freqüents:

- oblidar `sudo` en ordres d'administració  
- utilitzar `usermod -G` sense `-a`  
- no tancar sessió després d'afegir un grup  
- mirar només `/etc/group` i no comprovar amb `id`  
- modificar `/etc/skel` després de crear l'usuari i esperar que s'apliqui automàticament  
- confondre setgid amb sticky bit

---

<!-- SLIDE 35 -->
# 🔸 **Relació amb la pràctica A1**

Aquest bloc ajuda a preparar la part Linux de la pràctica A1.

A la pràctica es treballa:

- crear usuaris a Ubuntu  
- observar què es copia al seu `/home`  
- modificar `/etc/skel`  
- crear un altre usuari  
- comparar les diferències  
- documentar-ho amb captures

La idea és entendre què fa el sistema quan crea un compte nou.

---

<!-- SLIDE 36 -->
# 🔸 **Relació amb la pràctica A4**

Aquest bloc també prepara la pràctica de carpetes compartides restringides per grups.

A la pràctica A4 es treballa:

- crear grups locals  
- afegir usuaris als grups  
- crear carpetes de projecte  
- assignar grup propietari  
- aplicar permisos amb `chmod`  
- comprovar que només el grup correcte hi pot accedir

Els grups són la base per restringir l'accés.

---

<!-- SLIDE 37 -->
# 🔸 **Resum del bloc 4**

- Els grups permeten organitzar usuaris amb permisos comuns  
- Cada grup té un nom i un GID  
- `/etc/group` guarda la informació dels grups  
- `groupadd`, `groupmod`, `groupdel`, `gpasswd` i `usermod` permeten administrar grups  
- `id` i `groups` serveixen per comprovar la pertinença a grups  
- `/etc/skel` funciona com a plantilla per als nous usuaris

---

<!-- SLIDE 38 -->
# **Fi del Bloc 4**
