---
marp: true
paginate: true
theme: default

header: "RA03 – Tasques bàsiques de configuració de sistemes operatius · Bloc 2 – Treball en mode ordre"
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
# **RA03 – Bloc 2**
## **Treball en mode ordre**

**SMX01 - Sistemes Operatius Monolloc**  
**Professor - Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **Què treballarem en aquest bloc**

Aquest bloc se centra en:

- Intèrpret d’ordres  
- Sintaxi bàsica  
- CMD i PowerShell  
- Bash i terminals TTY  
- `man` i `sudo`  
- Errors habituals en executar ordres  

Objectiu: entendre com treballar amb el sistema en **mode text**.

---

<!-- SLIDE 3 -->
# 🔸 **Mode gràfic vs mode ordre**

**Mode gràfic (GUI):**

- Interacció amb icones, finestres i menús  
- Més intuïtiu per a la majoria d’usuaris  
- Exemple: Windows, GNOME, KDE  

**Mode ordre (CLI):**

- Interacció escrivint ordres  
- Més ràpid per a tasques repetitives  
- Molt útil en administració i automatització  

**Idea clau:**

> El mode gràfic és més accessible; el mode ordre és més potent per gestionar el sistema
Et deixa fer més coses de gestió i automatització amb més control.

---

<!-- SLIDE 4 -->
# 🔸 **Intèrpret d’ordres i sintaxi**

Un **intèrpret d’ordres** és el programa que:

- Llegeix les ordres escrites per l’usuari  
- Les converteix en instruccions per al SO
- No necessita interfície gràfica  

La sintaxi de les ordres inclou:

```bash
    # ordre = què vols fer
    # opcions = com ho vols fer
    # arguments = sobre què ho vols fer
    # ordre [opcions] [arguments]

    ls # fitxers i carpetes dins carpeta
    ls -l # mostra el contingut del directori actual però format llarg
    ls Documents # contingut de la carpeta Documents, no actual
    ls -l Documents # contingut de la carpeta Documents en format llarg i detallat   
```

---

<!-- SLIDE 5 -->
# 🔸 **CMD a Windows**

**CMD (Command Prompt)** és:

- L’intèrpret d’ordres clàssic de Microsoft  
- Basat en MS-DOS  
- Integrat a Windows des de Windows NT  
- Basat en ordres de text  

Per obrir-lo:

- Inici → Sistema de Windows → Símbol del sistema  
- Escriure `cmd` al cercador  

---

<!-- SLIDE 6 -->
# 🔸 **Característiques bàsiques de CMD**

A CMD podem:

- Executar ordres del sistema  
- Obrir-lo com a administrador per tenir més permisos  
- Personalitzar colors, fonts i fons  

Directori inicial habitual:

```text
C:\Users\NomUsuari
```

És una eina simple però encara útil per a gestió bàsica del sistema

---

<!-- SLIDE 7 -->
# 🔸 **PowerShell: intèrpret avançat**

**PowerShell** és més potent que CMD perquè:

- Admet scripts avançats  
- Utilitza **.NET**  
- Té una sintaxi més rica  
- Permet gestionar serveis, processos i configuració  
- Treballa amb **objectes**, no només amb text  

Objecte: dada amb estructura i propietats pròpies

Per obrir-lo:

- Inici → Windows PowerShell  
- O escriure `powershell` al cercador  

---

<!-- SLIDE 8 -->
# 🔸 **CMD vs PowerShell**

**CMD:**

- Més simple  
- Ordres clàssiques  
- Útil per tasques bàsiques  

**PowerShell:**

- Més complet  
- Combina comandes i scripts  
- Millor per automatització i administració  

Exemple d’àlies:

```powershell
ls
```

és equivalent a:

```powershell
Get-ChildItem
```

---

<!-- SLIDE 9 -->
# 🔸 **PowerShell: detalls útils**

PowerShell també destaca perquè:

- És de **codi obert**  
- Es pot personalitzar com CMD  
- Té un directori inicial habitual com aquest:

```powershell
PS C:\Users\NomUsuari>
```

Facilita la transició d’usuaris que ja coneixen ordres de Linux.

---

<!-- SLIDE 10 -->
# 🔸 **Shell i Bash a GNU/Linux**

En GNU/Linux, el **shell** és la interfície que permet interactuar amb el sistema

En mode ordre, alguns shells habituals són:

- **Bash**  
- `sh`  
- `ksh`  
- `csh`  

**Bash** és:

- El shell més habitual  
- El predeterminat a moltes distribucions Linux  
- Una eina clau per administrar i automatitzar tasques  

---

<!-- SLIDE 11 -->
# 🔸 **Com utilitzar Bash**

Podem utilitzar Bash de dues maneres:

- Obrint un **terminal TTY** (Teletype terminals): Un TTY és un terminal en mode text que permet interactuar amb Linux escrivint ordres directament, sense interfície gràfica.
- Obrint un **emulador de terminal** dins del mode gràfic  

Exemple en Ubuntu:

- Terminal de GNOME  

Això permet treballar en mode text encara que el sistema tingui entorn gràfic

---

<!-- SLIDE 13 -->
# 🔸 **Sintaxi d’una ordre en Bash**

Format general:

```bash
nom_ordre [-opcions] [arguments]
```

Elements:

- `nom_ordre` → l’ordre que volem executar  
- `-opcions` → modifiquen el comportament  
- `arguments` → fitxers, directoris o valors  

Exemples:

```bash
ls
ls -l
ls /etc/shells
ls -l /etc/shells
```

---

<!-- SLIDE 14 -->
# 🔸 **Errors habituals en executar ordres**

En Bash, els espais en blanc són importants

Errors típics:

- Escriure `ls-l` en lloc de `ls -l`  
- No separar bé ordres, opcions i arguments  
- Posar una ordre que no existeix  

Idea clau:

> Si la sintaxi és incorrecta, l’ordre no s’executa bé

---

<!-- SLIDE 15 -->
# 🔸 **Ajuda amb `man`**

Per consultar informació sobre una ordre a Linux, fem servir:

```bash
man nom_ordre
```

Exemples:

```bash
man ls
man man
```

`man` serveix per:

- Consultar l’ajuda d’una ordre  
- Veure opcions disponibles  
- Entendre millor la sintaxi  

---

<!-- SLIDE 16 -->
# 🔸 **Permisos i ús de `sudo`**

Algunes ordres necessiten permisos d’administrador.

Exemple:

```bash
ls -l /root
```

pot donar error si l’usuari no té permisos

Per executar una ordre com a administrador:

```bash
sudo ls -l /root
```

`sudo`:

- Vol dir **superuser do**  
- Demana contrasenya  
- Només funciona per a usuaris autoritzats  

---

<!-- SLIDE 17 -->
# 🔸 **Resum del bloc 2**

- El mode ordre és clau en administració de sistemes  
- L’intèrpret d’ordres llegeix i executa ordres  
- A Windows destaquen **CMD** i **PowerShell**  
- A Linux destaca **Bash**  
- La sintaxi correcta és imprescindible  
- `man` ajuda a consultar ordres  
- `sudo` permet executar ordres amb privilegis  

---

<!-- SLIDE 18 -->
# **Fi del Bloc 2**
