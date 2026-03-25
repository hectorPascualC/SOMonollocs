---
marp: true
paginate: true
theme: default

header: "RA03 – Tasques bàsiques de configuració de sistemes operatius · Bloc 9 – Automatització de tasques"
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
# **RA03 – Bloc 9**
## **Automatització de tasques**

**SMX01 - Sistemes Operatius Monolloc**  
**Professor - Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **Què treballarem en aquest bloc**

Aquest bloc se centra en:

- Automatització de tasques a **Windows**  
- **Programador de tasques**  
- **Guions administratius** i **Execution Policy**    
- Automatització de tasques a **Linux**  
- **Cron**, **crontab** i **Anacron**  

Objectiu: entendre com programar tasques repetitives i com automatitzar accions tant a Windows com a Linux   

---

<!-- SLIDE 3 -->
# 🔸 **Automatització de tasques a Windows**

L’automatització de tasques permet:

- executar automàticament **tasques o programes** en moments determinats  
- iniciar accions després d’un **temps definit** o d’una **acció concreta**  
- automatitzar tasques com:
  - **còpies de seguretat**
  - **desfragmentació del disc**

---

<!-- SLIDE 4 -->
# 🔸 **Programador de tasques a Windows**

**Programador de tasques**

Permet:

- programar l’inici de **tasques**  
- executar **programes**  
- llançar **scripts**  

**Com accedir-hi?**

`Inici > Eines administratives > Programador de tasques`

Per a certes accions calen **permisos d’administrador**.

---

<!-- SLIDE 5 -->
# 🔸 **Interfície del Programador de tasques**

Dues zones principals:

- **Panell central**  
  → mostra les **tasques actives**

- **Dreta**  
  → conté les **accions específiques per programar**

Aquesta eina és la base per crear, modificar i executar tasques automàtiques dins de Windows.

---

<!-- SLIDE 6 -->
# 🔸 **Crear una nova tasca**

Quan es crea una nova tasca, el quadre de diàleg inclou aquestes pestanyes principals:

- **General**  
  → nom, descripció i opcions de seguretat

- **Desencadenant**  
  → quan o per quin motiu s’ha d’executar

- **Acció**  
  → què ha de fer la tasca

- **Condicions**  
  → requisits perquè s’executi

- **Configuració**  
  → altres paràmetres avançats

---

<!-- SLIDE 7 -->
# 🔸 **Guions administratius a Windows**

- arxius de text amb ordres  
- que s’executen **automàticament**  
- per lots o línia a línia  

**Formats habituals:**

- `.cmd`
- `.bat`
- `.ps1`
- `.js`

**Utilitat:**

- milloren la **productivitat**
- permeten automatitzar **tasques repetitives**

---

<!-- SLIDE 8 -->
# 🔸 **Risc i control dels guions**

- poden ser útils per administració i automatització  
- però també poden ser utilitzats per **atacar l’equip** si no es controla bé l’execució

Per això, a PowerShell es treballa amb una **política d’execució**.

---

<!-- SLIDE 9 -->
# 🔸 **Execution Policy a PowerShell**

Per consultar la política d’execució amb aquest ordre:

```powershell
Get-ExecutionPolicy -List
```

**Nivells de seguretat:**

- **Restricted** → no es pot executar cap guió  
- **RemoteSigned** → només guions signats i descarregats d’Internet  
- **AllSigned** → tots els guions han d’estar signats  
- **Unrestricted** → es poden executar tots, inclosos els no signats

---

<!-- SLIDE 10 -->
# 🔸 **Canvi de política d’execució**

Sintaxi:

```powershell
Set-ExecutionPolicy [política] -Scope [àmbit]
```

**Exemple que apareix al material:**

```powershell
Set-ExecutionPolicy Unrestricted -Scope CurrentUser
```

Això permet configurar el nivell d’execució per a l’usuari actual.

---

<!-- SLIDE 11 -->
# 🔸 **Guions + Programador de tasques**

Els guions administratius també es poden utilitzar amb el **Programador de tasques**.

**Passos bàsics:**

1. Crear una nova tasca  
2. A la pestanya **Accions**, seleccionar **Iniciar un programa**  
3. Indicar l’**intèrpret d’ordres** (`PowerShell`, `CMD`)  
4. Afegir el fitxer del **guió administratiu**

---

<!-- SLIDE 12 -->
# 🔸 **Automatització de tasques a Linux**

A Linux, l’automatització serveix per executar tasques repetitives com:

- **còpies de seguretat**  
- **actualització de programes**  
- **monitoratge del sistema**

Les eines principals:

- **Cron**
- **Anacron**

---

<!-- SLIDE 13 -->
# 🔸 **Cron i fitxers implicats**

**Cron** executa tasques a intervals regulars:

- minuts  
- hores  
- dies  

És especialment útil per al **manteniment del sistema**.

**Fitxers implicats:**

- `crontab` de cada usuari → programació personalitzada  
- `/etc/crontab` → afecta tot el sistema i indica quin usuari executa cada tasca  
- ubicació: `/var/spool/cron/crontabs`

---

<!-- SLIDE 14 -->
# 🔸 **Sintaxi de les expressions Cron**

Format bàsic d’una línia `crontab`:

```bash
minut hora dia_mes mes dia_setmana ordre
```

**Significat dels camps:**

- `minut` → `0–59`  
- `hora` → `0–23`  
- `dia_mes` → `1–31`  
- `mes` → `1–12`  
- `dia_setmana` → dia de la setmana  
- `ordre` → comanda o script a executar

---

<!-- SLIDE 15 -->
# 🔸 **Caràcters especials a Cron**

- `*` → tots els valors  
- `,` → llista de valors  
- `-` → rang de valors  
- `/` → interval

**Expressions abreujades:**

- `@hourly` → cada hora  
- `@daily` → cada dia  
- `@weekly` → cada setmana  
- `@monthly` → cada mes  
- `@yearly` → cada any

---

<!-- SLIDE 16 -->
# 🔸 **Editar l’arxiu crontab**

L’ordre recomanada és:

```bash
crontab -e
```

Això obre l’editor per modificar les tasques de l’usuari.

**Altres opcions útils:**

- `-l` → mostrar el contingut del `crontab`  
- `-r` → eliminar el `crontab`  
- `-i` → confirmar abans d’eliminar  
- `-u [usuari]` → gestionar el `crontab` d’un altre usuari amb `sudo`

---

<!-- SLIDE 17 -->
# 🔸 **Permisos amb crontab i Anacron**

**Permisos d’ús de `crontab`:**

- fitxers: `/etc/cron.allow` i `/etc/cron.deny`  
- només els usuaris presents a `cron.allow` i no a `cron.deny` poden editar `crontab`

**Què és Anacron?**

- és un complement de **Cron**  
- està pensat per sistemes que s’apaguen sovint  
- si el sistema està apagat en el moment programat, **Anacron** executa la tasca quan sigui possible

---

<!-- SLIDE 18 -->
# 🔸 **Fitxer /etc/anacrontab**

Sintaxi:

```bash
període retard identificador_tasca ordre
```

**Camps:**

- `període` → exemple: `1` (diari), `7` (setmanal), `30` (mensual)  
- `retard` → minuts d’espera després d’encendre l’equip  
- `identificador_tasca` → nom de la tasca  
- `ordre` → comanda a executar

---

<!-- SLIDE 19 -->
# 🔸 **Ordres i directoris d’Anacron**

**Ordres útils amb `anacron`:**

- `-f` → executa tasques ignorant el temps  
- `-T` → verifica si `/etc/anacrontab` és vàlid  
- `-n` → executa tasques immediatament sense esperar retard

**Directoris especials:**

- `/etc/cron.daily` → tasques diàries  
- `/etc/cron.weekly` → tasques setmanals  
- `/etc/cron.monthly` → tasques mensuals  
- `/etc/cron.hourly` → tasques cada hora

---

<!-- SLIDE 20 -->
# 🔸 **Resum del bloc 9**

- A **Windows**, el Programador de tasques permet automatitzar programes, tasques i scripts  
- Els **guions administratius** es poden controlar amb la **Execution Policy**  
- A **Linux**, `cron` permet programar tasques periòdiques  
- **Anacron** és útil quan el sistema no està sempre encès  
- Tant a Windows com a Linux, l’automatització millora la productivitat i el manteniment del sistema  

---

<!-- SLIDE 21 -->
# **Fi del Bloc 9**
