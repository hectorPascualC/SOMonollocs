---
marp: true
paginate: true
theme: default

header: "RA04 – Administració bàsica de sistemes operatius · Bloc 3 – Gestió d'usuaris a GNU/Linux"
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
# **RA04 – Bloc 3**
## **Gestió d'usuaris a GNU/Linux**

**SMX01 - Sistemes Operatius Monolloc**  
**Professor - Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **Què treballarem en aquest bloc**

Aquest bloc se centra en:

- gestió d'**usuaris** a Ubuntu  
- creació, modificació i eliminació de comptes  
- diferència entre gestió **gràfica** i gestió per **terminal**  
- ordres bàsiques: `useradd`, `passwd`, `usermod`, `userdel`  
- fitxers de configuració: `/etc/passwd` i `/etc/shadow`

Objectiu: entendre com el sistema crea i controla els comptes d'usuari en GNU/Linux

---

<!-- SLIDE 3 -->
# 🔸 **Per què cal gestionar usuaris?**

En un sistema operatiu, cada usuari necessita:

- un **nom de compte** per iniciar sessió  
- una **contrasenya** o sistema d'autenticació  
- un **directori personal**  
- uns **permisos** dins del sistema  
- un entorn de treball propi

La gestió d'usuaris permet controlar qui pot entrar al sistema i què pot fer-hi.

---

<!-- SLIDE 4 -->
# 🔸 **Què pot fer l'administrador?**

A Ubuntu, l'administrador pot:

- crear nous comptes d'usuari  
- modificar dades d'un compte existent  
- canviar o bloquejar contrasenyes  
- assignar directoris personals  
- eliminar usuaris del sistema

Aquestes operacions es poden fer de dues maneres:

- amb **interfície gràfica**  
- amb **ordres de terminal**

---

<!-- SLIDE 5 -->
# 🔸 **Dues formes de treballar**

## Mode gràfic

- més visual  
- recomanat per a tasques bàsiques  
- útil per començar

## Mode terminal

- més directe  
- més flexible  
- imprescindible en administració real de sistemes

Idea clau: el mode gràfic és més senzill, però el terminal dona més control.

---

<!-- SLIDE 6 -->
# 🔸 **Gestió d'usuaris en mode gràfic**

A Ubuntu es pot gestionar usuaris des de la configuració del sistema.

Passos habituals:

1. Obre la vista general d'**Activitats**  
2. Cerca **Usuaris**  
3. Fes clic a **Desbloqueja**  
4. Introdueix la contrasenya d'administrador  
5. Gestiona els comptes d'usuari

---

<!-- SLIDE 7 -->
# 🔸 **Afegir un usuari en mode gràfic**

Per crear un compte nou:

- prem **Afegeix usuari**  
- escull el tipus de compte  
- introdueix el nom complet  
- introdueix el nom del compte  
- defineix una contrasenya

També es pot permetre que l'usuari estableixi la contrasenya en el proper inici de sessió.

---

<!-- SLIDE 8 -->
# 🔸 **Tipus d'usuari a Ubuntu**

Quan es crea un compte, cal decidir el tipus d'usuari.

- **Usuari estàndard**  
  → pot utilitzar el sistema, però no administrar-lo

- **Administrador**  
  → pot instal·lar programes, modificar configuració i executar tasques amb permisos elevats

Idea clau: no tots els usuaris haurien de ser administradors.

---

<!-- SLIDE 9 -->
# 🔸 **Modificar o eliminar usuaris**

Des de la finestra d'**Usuaris** es pot:

- modificar informació del compte  
- activar o desactivar l'entrada automàtica  
- canviar el tipus d'usuari  
- eliminar un compte

Quan s'elimina un usuari, Ubuntu pot oferir dues opcions:

- conservar els fitxers personals  
- suprimir els fitxers personals

---

<!-- SLIDE 10 -->
# 🔸 **Compte amb l'entrada automàtica**

L'entrada automàtica permet iniciar sessió sense escriure contrasenya.

Pot semblar còmode, però té riscos:

- qualsevol persona pot accedir a l'equip  
- es redueix la seguretat  
- no és recomanable en equips compartits

En un entorn educatiu o professional, és millor mantenir l'autenticació activada.

---

<!-- SLIDE 11 -->
# 🔸 **Gestió d'usuaris per terminal**

El terminal permet administrar usuaris amb ordres.

Ordres principals:

```bash
useradd
passwd
usermod
userdel
```

Normalment cal executar-les amb permisos d'administrador:

```bash
sudo ordre opcions usuari
```

---

<!-- SLIDE 12 -->
# 🔸 **Crear usuaris amb `useradd`**

Sintaxi general:

```bash
sudo useradd [opcions] compte_usuari
```

Exemple senzill:

```bash
sudo useradd alumne1
```

Aquesta ordre crea el compte, però sovint cal afegir més opcions per definir correctament l'entorn de l'usuari.

---

<!-- SLIDE 13 -->
# 🔸 **Opcions habituals de `useradd`**

Opcions útils:

- `-d` → defineix el directori personal  
- `-g` → defineix el grup principal  
- `-G` → defineix grups addicionals  
- `-u` → defineix l'identificador d'usuari (**UID**)  
- `-s` → defineix el shell per defecte

Exemple:

```bash
sudo useradd -d /home/alumne1 -s /bin/bash alumne1
```

---

<!-- SLIDE 14 -->
# 🔸 **Crear usuari amb directori personal**

En molts sistemes és habitual usar l'opció `-m` per crear també el directori personal.

Exemple pràctic:

```bash
sudo useradd -m -s /bin/bash alumne1
sudo passwd alumne1
```

Què fa?

- crea l'usuari `alumne1`  
- crea `/home/alumne1`  
- assigna `/bin/bash` com a shell  
- permet definir una contrasenya

---

<!-- SLIDE 15 -->
# 🔸 **Assignar contrasenyes amb `passwd`**

Sintaxi general:

```bash
sudo passwd [compte_usuari]
```

Exemple:

```bash
sudo passwd alumne1
```

Aquesta ordre permet:

- assignar una contrasenya nova  
- canviar una contrasenya existent  
- gestionar l'estat de la contrasenya

---

<!-- SLIDE 16 -->
# 🔸 **Opcions útils de `passwd`**

Opcions destacades:

- `-l` → bloqueja temporalment el compte  
- `-x` → defineix la durada màxima de la contrasenya  
- `-e` → obliga a canviar la contrasenya en el proper inici de sessió  
- `-S` → mostra l'estat de la contrasenya

Exemples:

```bash
sudo passwd -l alumne1
sudo passwd -e alumne1
sudo passwd -S alumne1
```

---

<!-- SLIDE 17 -->
# 🔸 **Modificar usuaris amb `usermod`**

Sintaxi general:

```bash
sudo usermod [opcions] compte_usuari
```

Opcions habituals:

- `-c` → afegeix informació personal  
- `-d` → assigna un nou directori personal  
- `-g` → canvia el grup principal  
- `-G` → assigna grups addicionals

---

<!-- SLIDE 18 -->
# 🔸 **Exemples amb `usermod`**

Afegir informació descriptiva:

```bash
sudo usermod -c "Alumne SMX" alumne1
```

Canviar el directori personal:

```bash
sudo usermod -d /home/nou_alumne1 alumne1
```

Afegir l'usuari a un grup sense perdre els grups actuals:

```bash
sudo usermod -aG grupprojecte alumne1
```

---

<!-- SLIDE 19 -->
# 🔸 **Eliminar usuaris amb `userdel`**

Sintaxi general:

```bash
sudo userdel [opcions] compte_usuari
```

Exemple bàsic:

```bash
sudo userdel alumne1
```

Aquesta ordre elimina el compte, però no sempre elimina automàticament el directori personal.

---

<!-- SLIDE 20 -->
# 🔸 **Opcions útils de `userdel`**

Opcions habituals:

- `-r` o `--remove`  
  → elimina també el directori `/home` i els fitxers de l'usuari

- `-f` o `--force`  
  → força l'eliminació encara que hi hagi sessions obertes

Exemple:

```bash
sudo userdel -r alumne1
```

Idea clau: abans d'eliminar un usuari, cal decidir què passa amb els seus fitxers.

---

<!-- SLIDE 21 -->
# 🔸 **Fitxers de configuració d'usuaris**

GNU/Linux guarda informació dels usuaris en fitxers del sistema.

Els principals són:

- `/etc/passwd`  
  → conté informació bàsica dels comptes

- `/etc/shadow`  
  → conté informació de contrasenyes i caducitat

Aquests fitxers no s'han d'editar sense entendre'n bé l'estructura.

---

<!-- SLIDE 22 -->
# 🔸 **Format general dels fitxers**

Cada línia representa un usuari.

Els camps se separen amb dos punts:

```text
camp1:camp2:camp3:camp4:camp5:camp6:camp7
```

Això permet que el sistema interpreti cada dada de manera ordenada.

Exemple de camps habituals:

- nom d'usuari  
- UID  
- GID  
- directori personal  
- shell per defecte

---

<!-- SLIDE 23 -->
# 🔸 **Camps de `/etc/passwd`**

Cada línia de `/etc/passwd` té 7 camps:

1. nom d'usuari  
2. contrasenya indicada normalment amb `x`  
3. UID  
4. GID  
5. informació addicional  
6. directori personal  
7. shell per defecte

Exemple simplificat:

```text
alumne1:x:1001:1001:Alumne SMX:/home/alumne1:/bin/bash
```

---

<!-- SLIDE 24 -->
# 🔸 **Què significa la `x` a `/etc/passwd`?**

Antigament, la contrasenya podia aparèixer en `/etc/passwd`.

Actualment, per seguretat:

- `/etc/passwd` mostra una `x`  
- la contrasenya real no és visible  
- la informació sensible es guarda a `/etc/shadow`

Això separa la informació pública del compte de la informació sensible de seguretat.

---

<!-- SLIDE 25 -->
# 🔸 **Camps de `/etc/shadow`**

El fitxer `/etc/shadow` conté informació de seguretat:

- nom d'usuari  
- contrasenya encriptada  
- data de l'últim canvi de contrasenya  
- dies mínims fins a poder canviar-la  
- dies màxims fins que cal canviar-la  
- dies d'avís abans de caducar  
- data d'expiració del compte

Només usuaris amb permisos elevats poden consultar-lo completament.

---

<!-- SLIDE 26 -->
# 🔸 **Com interpretar un compte d'usuari**

Quan revisem un usuari, ens podem preguntar:

- quin és el seu **nom de compte**?  
- quin **UID** té?  
- quin és el seu **grup principal**?  
- quin directori personal utilitza?  
- quin shell té assignat?  
- la contrasenya està activa, caducada o bloquejada?

Aquestes preguntes ajuden a diagnosticar problemes d'accés.

---

<!-- SLIDE 27 -->
# 🔸 **Seqüència recomanada de treball**

Per crear un usuari de manera controlada:

1. planificar el nom del compte  
2. crear l'usuari  
3. crear o revisar el directori personal  
4. assignar contrasenya  
5. comprovar el compte  
6. iniciar sessió i verificar que funciona

Treballar pas a pas evita errors i facilita la documentació.

---

<!-- SLIDE 28 -->
# 🔸 **Exemple complet**

Crear un usuari anomenat `alumne1`:

```bash
sudo useradd -m -s /bin/bash alumne1
sudo passwd alumne1
id alumne1
grep alumne1 /etc/passwd
```

Què comprovem?

- que l'usuari existeix  
- que té UID i GID  
- que té directori personal  
- que té shell assignat

---

<!-- SLIDE 29 -->
# 🔸 **Errors habituals**

Errors que poden aparèixer:

- crear l'usuari sense directori `/home`  
- oblidar assignar contrasenya  
- posar un shell incorrecte  
- eliminar l'usuari però deixar fitxers personals  
- modificar grups sense comprovar el resultat

Solució: comprovar sempre amb ordres com `id`, `groups` i `grep`.

---

<!-- SLIDE 30 -->
# 🔸 **Relació amb la pràctica A1**

Aquest bloc ajuda a preparar la part Linux de la pràctica A1.

A la pràctica es treballa:

- creació d'usuaris a Ubuntu  
- observació del directori `/home`  
- comparació entre usuaris creats  
- documentació amb captures  
- explicació del que fa el sistema quan crea un compte

Aquest bloc dona la base teòrica per entendre aquests passos.

---

<!-- SLIDE 31 -->
# 🔸 **Resum del bloc 3**

- Ubuntu permet gestionar usuaris en mode gràfic i per terminal  
- `useradd` crea comptes d'usuari  
- `passwd` gestiona contrasenyes  
- `usermod` modifica comptes existents  
- `userdel` elimina usuaris  
- `/etc/passwd` guarda informació bàsica dels comptes  
- `/etc/shadow` guarda informació sensible de contrasenyes

---

<!-- SLIDE 32 -->
# **Fi del Bloc 3**
