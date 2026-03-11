---
marp: true
paginate: true
theme: default

header: "RA02 - Instal·lació de Sistemes Operatius · Bloc 3 – Preparació i Instal·lació"
footer: "Mòdul 0222 - SO Monolloc"

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

# **RA02 – Bloc 3**
## **Preparació del Maquinari i Instal·lació del Sistema Operatiu**

SMX01 — SO Monolloc  
Professor — Hèctor Pascual

---

# 🔸 **1.3 Instal·lació de Sistemes Operatius Propietaris**

Factors de planificació:

- Compatibilitat amb el maquinari  
  → Comprovar que el sistema operatiu suporta el processador, RAM i dispositius de l’equip.

- Compatibilitat amb aplicacions  
  → Verificar que els programes que necessitem funcionin en aquest sistema operatiu.

- Ús previst de l’equip  
  → No és el mateix un equip domèstic que un servidor o un equip empresarial.

---

# 🔸 **1.3 Instal·lació de Sistemes Operatius Propietaris (II)**

- Suport tècnic del fabricant  
  → Important per rebre actualitzacions i assistència en cas de problemes.

Objectiu: garantir instal·lació estable i funcional.

---

# 🔸 **Requisits Tècnics del Sistema Operatiu**

Requisits principals:

- Processador  
  → Ha de ser compatible amb l’arquitectura (32 o 64 bits).

- Memòria RAM  
  → Determina quants programes podran funcionar alhora.

- Disc dur  
  → Espai necessari per instal·lar el sistema i aplicacions.

---

# 🔸 **Requisits Tècnics del Sistema Operatiu (II)**

- Targeta gràfica  
  → Necessària per suportar interfícies gràfiques modernes.

Altres requisits:

- Connexió Internet  
  → Per activacions, actualitzacions i descàrrega de controladors.

- Dispositius específics (micròfon, biometria…)  
  → Només necessaris si es vol utilitzar aquestes funcionalitats.

Mínims → funcionament bàsic  
Recomanats → millor rendiment

---

# 🔸 **Selecció del Sistema Operatiu**

Factors:

- Tipus d’equip (servidor, escriptori…)  
  → Cada sistema està optimitzat per un ús concret.

- Compatibilitat amb aplicacions  
  → Ha de suportar el programari necessari.

- Suport tècnic  
  → Important en entorns professionals.

---

# 🔸 **Selecció del Sistema Operatiu (II)**

- Seguretat  
  → Sistemes amb millors mecanismes de protecció.

- Tipus de llicència  
  → Condicions legals d’ús del programari.

Exemples propietaris:
- Windows (Microsoft)  
- macOS (Apple)

---

# 🔸 **Esquemes de Partició**

La manera com s’organitza i es realitza la divisió d'un disc dur en particions

MBR - Master Boot Record - (1983):

- Fins a 4 particions primàries  
  → Limitació històrica en nombre de particions

- Limitacions de mida  
  → No suporta discs molt grans

---

# 🔸 **Esquemes de Partició (II)**

GPT (GUID Partition Table):

- Més particions  
  → Permet moltes més divisions del disc.

- Suport discs grans  
  → Adequat per discs moderns de gran capacitat.

- Identificadors GUID  
  → Cada partició té un identificador únic

---

# 🔸 **Tipus de Particions**

- Primària → instal·lar SO  
  → Pot contenir directament un SO
  → Divisió principal del disc

- Estesa o secundària → contenidor  
  → Serveix per crear múltiples particions lògiques
  → Serveix com a contenidor, no acepta stemes arxius

- Lògica → dins estesa  
  → Funcionen com particions independents
  → Amb el seu propi stemes d'arxiu

Organitzen el disc en espais lògics

---

# 🔸 **Nomenclatura entre SO**
- Windows: Les particions s'identifiquen amb lletres (C:, D:, etc.).
- GNU/Linux: Utilitza nomenclatura basada en /dev/sdX (X és la lletra del dispositiu) i /dev/sdXY (Y és el número de partició)

/dev/sda: Primer disc
/dev/sda1: Primera partició del primer disc
/dev/sdb: Segon disc

---

# 🔸 **Sistemes d’Arxius (Propietaris)**

Defineix com es guarden, organitzen i gestionen les dades 
en dispositius d'emmagatzematge: discs durs, memòries USB...

Propietari: Desenvolupats per una empresa i controlat per aquesta.
El codi no és lliure

FAT / FAT32:

- Compatible  
  → Funciona en molts sistemes operatius

- Limitació 4GB per fitxer  
  → No permet fitxers molt grans

---

# 🔸 **Sistemes d’Arxius (Propietaris) (II)**

NTFS:

- Permisos  
  → Control d'accés per usuari: qui pot fer què sobre un fitxer o carpeta

- Seguretat  
  → Inclou mecanismes de protecció avançats

- Grans volums  
  → Admet discs i fitxers de gran mida

---

# 🔸 **Sistemes d’Arxius (Propietaris) (III)**

HFS+ / APFS (Apple):

- Optimitzats per ecosistema Apple  
  → Dissenyats per funcionar amb macOS

---

# 🔸 **Formatació d’un Disc**

Procés de preparació del disc:

- Creació sistema d’arxius  
  → Defineix com s’organitzaran les dades

- Organització en sectors i clústers  
  → Sector: És la unitat física mínima del disc
  → Clúster: És una agrupació de sectors. El sistema d’arxius no treballa amb sectors individuals, sinó amb clústers
  → Divideix físicament el disc en unitats gestionables

- Permet llegir i escriure dades  
  → Fa que el disc sigui usable pel sistema operatiu

---

# 🔸 **Clonació**

Còpia exacta d’un sistema   
→ Replica sistema operatiu, configuracions i dades.

Tipus:

- Basada en sectors: còpia completa amb tots sectors. Replicació exacta
- Basada en dades: nomès còpia de fitxers i dades existents
- Imatge virtual: creació d’imatges per virtualitzar o clonar completament un sistema

---

# 🔸 **Clonació (II)**

Utilitat:
- Restauració  
- Desplegament massiu  
- Còpies seguretat  

---

# 🔸 **1.3 Instal·lació de Sistemes Operatius Lliures**

Permeten respecte al codi font:

- Estudiar  
- Modificar  
- Distribuir  

Fases instal.lació:

- Planificació  
- Preparació  
- Execució  

---

# 🔸 **1.3 Instal·lació de Sistemes Operatius Lliures (II)**

- Configuració  
- Documentació  

---

# 🔸 **Distribucions Linux**

Exemples:

- Ubuntu  
- Debian  
- Fedora  
- Arch  
- Mint  

---

# 🔸 **Distribucions Linux (II)**

Escollir segons:

- Finalitat  
- Comunitat  
- Rendiment  

---

# 🔸 **Sistemes d’Arxius Linux**

ext4:

- Estàndard actual  
- Alta eficiència  

XFS:

- Grans volums  

swap:

- Memòria virtual  

---

# 🔸 **Punts de Muntatge (I)**

Directori on s'accedeix a una partició  

```
/
├── home
│   ├── hector
│   └── alumne
├── var
│   └── log
├── tmp
└── usr
    └── bin
```

---

# 🔸 **Punts de Muntatge (II)**

- /: fitxers essencials del SO
- /home: configuració, dades i fitxers usuaris
- /var: registres del stma
- /tmp: fitxers temporals  
- /usr: aplicacions instal.lades

Estructura jeràrquica en arbre invertit

---

<!-- SLIDE CONTINUACIÓ -->

# 🔸 **Instal·lació del sistema operatiu Windows**

Durant la instal·lació del sistema operatiu es realitzen diverses fases:

- Selecció de l’idioma i configuració regional  
  → permet definir idioma del sistema i del teclat.

- Selecció del disc o partició  
  → l’usuari escull on instal·lar el sistema operatiu.

- Còpia de fitxers del sistema  
  → el sistema copia els fitxers necessaris al disc.

- Configuració inicial  
  → creació d’usuari i configuració bàsica del sistema.

---

<!-- SLIDE -->

# 🔸 **Planificació de la instal·lació**

Abans d’instal·lar un sistema operatiu cal planificar:

- Requisits de maquinari  
  → comprovar si l’equip compleix els requisits mínims.

- Espai disponible al disc  
  → verificar que hi ha espai suficient per instal·lar el sistema.

- Compatibilitat del sistema  
  → assegurar que el maquinari és compatible amb el sistema operatiu.

- Còpia de seguretat  
  → guardar les dades importants abans de començar la instal·lació.

---

<!-- SLIDE -->

# 🔸 **Suport tècnic del sistema operatiu**

El suport tècnic és important per garantir el correcte funcionament del sistema.

Pot provenir de:

- Fabricant del sistema operatiu  
  → actualitzacions i assistència oficial.

- Comunitat d’usuaris  
  → fòrums i documentació.

- Empreses especialitzades  
  → serveis professionals de suport.

---

<!-- SLIDE -->

# 🔸 **Llicència del sistema operatiu**

Els sistemes operatius poden tenir diferents tipus de llicència:

- Llicència propietària  
  → el codi font no és accessible ni modificable.

- Llicència lliure  
  → permet estudiar, modificar i redistribuir el programari.

La llicència determina:

- condicions d’ús  
- distribució del programari  
- possibilitat de modificació.

---

<!-- SLIDE -->

# 🔸 **Noms dels dispositius i de les particions**

En sistemes GNU/Linux els dispositius tenen una nomenclatura específica.

Exemples:

- /dev/sda  
  → primer disc del sistema.

- /dev/sda1  
  → primera partició del primer disc.

- /dev/sdb  
  → segon disc del sistema.

Aquest sistema permet identificar fàcilment discs i particions.

---

<!-- SLIDE -->

# 🔸 **Esquemes de particions**

Abans d’instal·lar el sistema operatiu cal definir com es dividirà el disc.

Es poden crear diferents particions per:

- sistema operatiu  
- dades d’usuari  
- memòria d’intercanvi (swap)

La planificació de particions permet organitzar millor el disc.

---

<!-- SLIDE -->

# 🔸 **Instal·lació del sistema operatiu Ubuntu**

La instal·lació d’Ubuntu es realitza mitjançant un assistent.

Fases principals:

- selecció d’idioma  
  → idioma del sistema.

- configuració del teclat  
  → tipus de teclat utilitzat.

- selecció del disc  
  → particions on s’instal·larà el sistema.

- creació d’usuari  
  → configuració del compte principal.

Un cop finalitzat el procés, el sistema queda preparat per utilitzar.

---

<!-- SLIDE -->

# 🔸 **Sistema Dual Boot**

El dual boot permet instal·lar **dos sistemes operatius en el mateix equip**

En iniciar l’ordinador l’usuari pot escollir quin sistema vol utilitzar

Per configurar-lo cal:
- instal·lar primer un sistema operatiu
- crear una nova partició al disc
- instal·lar el segon sistema operatiu

El gestor d’arrencada permet seleccionar el sistema

---

<!-- SLIDE -->

# 🔸 **Creació d’escenaris Dual Boot**

Per crear un sistema dual boot cal:

- redimensionar una partició existent  
  → alliberar espai al disc.

- crear una nova partició  
  → utilitzar-la per instal·lar el segon sistema operatiu.

- instal·lar el segon sistema operatiu  
  → el gestor d’arrencada permetrà seleccionar-lo

---

# 🔸 Dual Boot vs Màquina Virtual

## Dual Boot

- Accés complet al maquinari
- Millor rendiment
- Només es pot utilitzar **un sistema operatiu alhora**

## Màquina virtual

- Permet executar diversos sistemes simultàniament
- Comparteixen recursos del sistema
- Rendiment inferior

---

# 🔸 Instal·lació Dual Boot

Exemple habitual:

**Windows + Ubuntu**

Procés general:

1. Instal·lar primer **Windows**
2. **Redimensionar la partició** del disc
3. Instal·lar **Ubuntu** a l'espai lliure

Durant la instal·lació es defineixen:

- sistema d’arxius
- mida de partició
- punt de muntatge

---

# 🔸 Configuració de particions en Linux

Paràmetres principals durant la instal·lació:

- **Mida de la partició**
- **Tipus de partició**
  - primària
  - lògica
- **Sistema d’arxius**
  - habitualment **ext4**
- **Punt de muntatge**

---

# 🔸 Resultat final del Dual Boot

Després de completar la instal·lació:

1. Es reinicia l’ordinador
2. Apareix el **gestor d’arrencada**
3. Es pot seleccionar el sistema operatiu

Exemple:

```

Ubuntu
Windows Boot Manager
Advanced options

```

---

# 🔸 Gestor d’arrencada (Bootloader)

Un **gestor d’arrencada** és el programa que:

- s’executa quan s’encén l’ordinador
- permet seleccionar el sistema operatiu
- inicia el sistema operatiu escollit

Sense un gestor d’arrencada **no seria possible utilitzar un dual boot**

---

# 🔸 BIOS i UEFI

El procés d’arrencada d’un ordinador comença al firmware, que és el programari integrat a la placa base

## BIOS

- sistema tradicional d’arrencada
- utilitzat en equips antics

## UEFI

- sistema modern
- més ràpid i segur
- permet discs **GPT**

Aquest firmware inicia el **gestor d’arrencada**

---

# 🔸 Gestor d’arrencada a Windows

Procés d’arrencada de Windows

```
Firmware (BIOS/UEFI)
↓
bootmgr - gestor d’arrencada: seleccio sistema operatiu
↓
BCD (Boot Configuration Data) - base de dades amb la configuració d'arrencada del sistema
↓
winload.exe - carrega el nucli i els drivers essencials
↓
Nucli de Windows - inicia el sistema operatiu
```

Eines d’administració

bcdedit → gestió del BCD per línia de comandes

msconfig → configuració d’arrencada amb interfície gràfica

---

# 🔸 Gestor d’arrencada a Linux

En sistemes Linux s’utilitza habitualment:

**GRUB**

Funcions:

- mostrar menú d’arrencada
- seleccionar sistema operatiu
- iniciar el sistema

Comanda habitual per actualitzar-lo:

```

update-grub

```

# **Resum del Bloc 3**

- Planificar abans d’instal·lar  
- Conèixer particions i sistemes d’arxius  
- Entendre dual boot  
- Configurar gestor d’arrencada  
- Respectar llicències  
- Mantenir sistema actualitzat  

---

# **Fi del Bloc 3**