---
marp: true
paginate: true
theme: default

header: "RA01 – Sistemes Operatius · Bloc 1 Complet"
footer: "Mòdul 0374 – Administració de Sistemes Operatius"

style: |
    header, footer {
        display: block;
        width: 100vw;
        font-size: .45rem;
        color: #bbbbbcff;
        z-index: 10;
    }
    header {
        text-align: right !important;
        padding-right: 50px;
    }
    section {
        display: flex;
        flex-direction: column;
        justify-content: flex-start !important;
    }
    section > * {
        margin-top: 0 !important;
    }    
    ul li::marker {
        color: #ff8800;
    }
---

<!-- Slide 01 -->
# **RA01 – Bloc 1**
## **Fonaments del sistema operatiu**
### Components · Codificació · Arquitectura · Processos · Arxius · Transaccions

Mòdul 0374 – Administració de Sistemes Operatius  
Professor: Hèctor Pascual

---

# **BLOC 1.1 – Components del sistema informàtic**

---

<!-- Slide 02 -->
# 1.1 Objectiu del bloc

- Entendre què és un sistema informàtic complet  
- Diferenciar maquinari, programari i personal  
- Identificar els components físics principals  
- Relacionar funcions amb arquitectura

---

<!-- Slide 03 -->
# 1.1.1 Definició de sistema informàtic

Un sistema informàtic és capaç de:

- Rebre dades  
- Processar instruccions  
- Emmagatzemar informació  
- Produir sortides significatives

---

<!-- Slide 04 -->
# 1.1.1 Components generals

- **Maquinari** – part física  
- **Programari** – instruccions, sistemes i aplicacions  
- **Personal** – usuaris, tècnics, administradors  

Sense un dels tres, el sistema no funciona.

---

<!-- Slide 05 -->
# 1.1.2 Maquinari: visió global

Inclou:

- CPU  
- RAM  
- Emmagatzematge  
- Placa base  
- Perifèrics  
- Busos de dades i control  

---

<!-- Slide 06 -->
# 1.1.2 Programari: visió global

Tipus:

- **Firmware (BIOS/UEFI)**  
- **Drivers**  
- **Sistema Operatiu**  
- **Aplicacions**

Cada capa depèn de la inferior.

---

<!-- Slide 07 -->
# 1.1.3 Arquitectura general d’un ordinador

```

```
      +--------------------+
      |        CPU         |
      |  CU      ALU       |
      +---------+----------+
                |
           Bus de dades
                |
```

+---------+    +---------+    +----------------+
| Memòria |    | Control |    |  Perifèrics    |
|  RAM    |    |  E/S    |    | Entrada/Sort.  |
+---------+    +---------+    +----------------+

```

---

<!-- Slide 08 -->
# 1.1.4 CPU: components interns

- **CU – Unitat de Control**  
- **ALU – Unitat Aritmètic-Lògica**  
- **Registres**  
- **Comptador de programa**  

Executa instruccions i gestiona fluxos.

---

<!-- Slide 08 -->
# 1.1.4 CPU: components interns

* **CPU**: Control  i execució de les operacions realitzant tractament automàtic de la informació
S'encarrega de controlar totes les tasques i processos que es realitzen
* **CU - Unitat de control**: Rep la informació, interpreta i processa mitjançant ordres que envia als components de l’ordinador
* **UNITAT ARITMÈTIC-LÒGICA (ALU)**: Realitzar operacions aritmètiques i lògiques

---

<!-- Slide 09 -->
# 1.1.5 Memòria interna

* **RAM (volàtil)**: Emmagatzemar i modificar informació. És la memòria principal, central o d'accés directe
* **CACHE (L1/L2/L3)**: Emmagatzena informació utilitzada amb més freqüència, solen ser intermèdies entre RAM i processador. Agilitza els càlculs  
* **ROM (Read Only Memori)**: Només lectura per poder inicialitzar el sistema. Conté programes especials per carregar i inicialitzar arrencada ordinador
    * **PROM (Programmable Read Only Memory)**: programables una sola vegada després d'haver estat muntades a la placa
    * **EPROM (Erasable Programmable Read Only Memory)**: s'utilitzen actualment. Permeten canviar la configuració assignada

---

<!-- Slide 09 -->
# 1.1.5 Memòria interna

* **BIOS (Basic Input Output System)** o **UEFI (Unified Extensible Firmware Interface)**: microprogramaris o firmware emmagatzemats en xips 
de memòria de tipus ROM, EPROM o EEPROM

La latència determina el rendiment.

---

<!-- Slide 10 -->
# 1.1.6 El bus del sistema

- Un **bus** és un conjunt de línies de comunicació que connecten:
  - CPU
  - Memòria principal
  - Mòduls d’entrada/sortida
- Transporta:
  - **Dades**
  - **Adreces**
  - **Senyals de control**

---
<!-- Slide 10 -->
# 1.1.6 El bus del sistema

- És simultàniament:
  - Un **element físic** (pistes, pins, connectors)
  - Un **protocol lògic** de comunicació

---

<!-- Slide 10 -->
# 1.1.6 Tipus de busos

- **Bus de dades**
  - Transporta els valors (bits) entre CPU, memòria i dispositius
- **Bus d'adreces**
  - Indica la posició de memòria o el dispositiu al qual es vol accedir
- **Bus de control**
  - Porta senyals com:
    - Lectura / escriptura
    - Interrupcions
    - Senyal de rellotge

---

<!-- Slide 10 -->
# 1.1.6 Tipus de busos

- **Bus d'E/S (I/O bus)**
  - Connecta la CPU/memòria amb els **controladors de perifèrics**
  - Exemple actual: **PCI Express (PCIe)** en PCs i servidors

---
<!-- Slide 11 -->
# 1.1.7 Perifèrics

Tipus:

- Entrada  
- Sortida  
- Entrada/Sortida  
- Emmagatzematge  
- Comunicació  

Drivers necessaris per interactuar-hi.

---

<!-- Slide 12 -->
# **BLOC 1.2 – Codificació de la informació**

---

<!-- Slide 13 -->
# 1.2 Objectiu

- Comprendre sistemes de numeració  
- Convertir bases  
- Conèixer codis alfanumèrics  
- Treballar unitats de mesura  

---

<!-- Slide 14 -->
# 1.2.1 Tipus de dades

Segons ús:

- Entrada  
- Sortida  
- Intermèdies  

Segons naturalesa:

- Constants  
- Variables  

Segons contingut:

- Numèriques, alfabètiques, alfanumèriques

---

<!-- Slide 15 -->
# 1.2.2 Sistemes de numeració

Bases:

- Binari (2)  
- Octal (8)  
- Decimal (10)  
- Hexadecimal (16)

Es representa com polinomi posicional.

---

<!-- Slide 16 -->
# Exemple: 1011₂

```

1·2³ + 0·2² + 1·2¹ + 1·2⁰ = 11₁₀

```

---

<!-- Slide 17 -->
# Exemple: 1B3₁₆ → decimal

```

1·256 + 11·16 + 3 = 435₁₀

```

---

<!-- Slide 18 -->
# Bases potències de 2

Agrupació de bits:

- Binari → Octal (3 bits)  
- Binari → Hexadecimal (4 bits)  

Exemple:

```

0000 0101 1101₂ → 05D₁₆

```

---

<!-- Slide 19 -->
# 1.2.3 Codis alfanumèrics

- **ASCII**  
- **EBCDIC**  
- **Unicode (UTF-8/16/32)**  

Unicode assigna un codi únic universal.

---

<!-- Slide 20 -->
# 1.2.4 Unitats d’informació

- 1 bit = {0,1}  
- 1 Byte = 8 bits  
- 1 KB = 1024 B  
- 1 MB = 1024 KB  
- 1 GB = 1024 MB  

---

<!-- Slide 21 -->
# Exemple

250 GB = 268.435.456.000 Bytes  
×8 = 2.147.483.648.000 bits  

---

# **BLOC 1.3 – El Sistema Operatiu**

---

<!-- Slide 22 -->
# 1.3 Objectiu

- Definir el SO  
- Estudiar elements interns  
- Revisar sistema d’arxius i interfícies  

---

<!-- Slide 23 -->
# 1.3.1 Què és el SO?

- Programari base  
- Gestor de recursos  
- Intermediari entre aplicacions i maquinari  

---

<!-- Slide 24 -->
# 1.3.2 Components principals

- Processos  
- Kernel  
- Gestor de memòria  
- E/S  
- Sistema d’arxius  
- Shell / GUI  

---

<!-- Slide 25 -->
# Procés

- És un programa en execució
- Té estat, recursos i memòria associada
- El SO crea, pausa, reprèn i finalitza processos
- Gestiona també **processos lleugers** (threads)
---

<!-- Slide 26 -->
# Nucli (kernel)

- Part central i privilegiada del SO
- Controla: CPU, memòria, E/S i interrupcions
- Implementa la planificació i la seguretat
- És responsable de fer complir el model de protecció

---

<!-- Slide 27 -->
# Gestió de memòria

- Assigna memòria als processos
- Implementa **paginació**, memòria virtual i protecció
- Evita que un procés accedeixi a espai d’un altre
- Optimitza l'ús de la RAM i redueix fallades de pàgina

---

<!-- Slide 28 -->
# Sistema d’arxius: estructura

Sistema de directoris estàndard de Linux/Unix

```
/
├── home
│   ├── usuari1
│   └── usuari2
├── etc
└── var

```

---

<!-- Slide 29 -->
# Permisos Unix

- r, w, x  
- Propietari / grup / altres  

Exemple:  
`rwxr-xr--`

---

<!-- Slide 30 -->
# Permisos Windows (ACL)

- Lectura  
- Escriptura  
- Modificació  
- Control total  

---

<!-- Slide 31 -->
# Shell i GUI

Shell:

- Bash, Zsh, PowerShell

GUI:

- Interfícies gràfiques basades en finestres

---

<!-- Slide 32 -->
# 📌 **FI DEL BLOC 1.3**

---

# **BLOC 1.4 – Gestió de processos**

---

<!-- Slide 33 -->
# 1.4 Objectiu

- Entendre PCB  
- Estats del procés  
- Algoritmes de planificació  

---

<!-- Slide 34 -->
# Programa vs procés

Programa = passiu  
Procés = actiu, en execució

---

<!-- Slide 35 -->
# PCB – Process Control Block

Conté:

- PID  
- Registres  
- Estat  
- Fitxers oberts  
- Taula de pàgines  
- Prioritat  

---

<!-- Slide 36 -->
# Estats del procés

- Nou  
- Preparat  
- Execució  
- Bloquejat  
- Finalitzat  

---

<!-- Slide 37 -->
# Diagrama d’estats

```

Nou → Preparat → Execució
↑      |
|      ↓
Bloquejat ← Fi

```

---

<!-- Slide 38 -->
# Canvi de context

El SO:

- Desa registres al PCB  
- Carrega registres del nou procés  
- Actualitza cues  

Cost elevat → cal optimització.

---

<!-- Slide 39 -->
# Algoritmes de planificació

- FCFS  
- SJF  
- SRTN  
- Round Robin  

---

<!-- Slide 40 -->
# Round Robin

Característiques:

- Quàntum fix  
- Preemptiu  
- Equitatiu  
- Ideal per sistemes interactius  

---

<!-- Slide 41 -->
# 📌 **FI DEL BLOC 1.4**

---

# **BLOC 1.5 – Gestió d’arxius**

---

<!-- Slide 42 -->
# 1.5 Objectiu

- Emmagatzematge  
- Assignació de blocs  
- Mètodes d’accés  

---

<!-- Slide 43 -->
# Arxiu

Unitat lògica amb:

- Nom  
- Contingut  
- Mida  
- Metadades  

---

<!-- Slide 44 -->
# Directori

Arxiu especial que conté referències a arxius i subdirectoris.

---

<!-- Slide 45 -->
# Assignació d’espai

- Contigua  
- Encadenada  
- Indexada  

---

<!-- Slide 46 -->
# Accés seqüencial

Processa registres en ordre.  
Ideal per logs.

---

<!-- Slide 47 -->
# Accés directe

Accés per posició lògica.  
Essencial per bases de dades.

---

<!-- Slide 48 -->
# 📌 **FI DEL BLOC 1.5**

---

# **BLOC 1.6 – Sistemes transaccionals**

---

<!-- Slide 49 -->
# 1.6 Objectiu

- Definir transacció  
- Conèixer ACID  
- Veure journaling  

---

<!-- Slide 50 -->
# ACID

- **Atomicitat**  
- **Consistència**  
- **Aïllament**  
- **Durabilitat**  

---

<!-- Slide 51 -->
# Journaling

- Registra operacions pendents  
- Permet revertir o completar en cas de fallada  
- Utilitzat a NTFS, ext4, APFS  

---

<!-- Slide 52 -->
# ZFS / APFS

Funcions:

- Instantànies  
- Clonació  
- Auto-reparació  
- Checksums  

---

<!-- Slide 53 -->
# Conclusió

Els sistemes transaccionals:

- Eviten corrupció  
- Milloren fiabilitat  
- Són crítics en entorns de dades sensibles  

---

<!-- Slide 54 -->
# **FI DEL BLOC 1**

---