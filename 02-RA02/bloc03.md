---
marp: true
paginate: true
theme: default

header: "RA02 – Instal·lació de Sistemes Operatius · Bloc 3 – Preparació i Instal·lació"
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

# **Resum del Bloc 3**

- Planificar abans d’instal·lar  
- Conèixer particions i sistemes d’arxius  
- Entendre dual boot  
- Configurar gestor d’arrencada  
- Respectar llicències  
- Mantenir sistema actualitzat  

---

# **Fi del Bloc 3**