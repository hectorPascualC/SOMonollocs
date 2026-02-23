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

MBR (1983):

- Fins a 4 particions primàries  
  → Limitació històrica en nombre de particions.

- Limitacions de mida  
  → No suporta discs molt grans.

---

# 🔸 **Esquemes de Partició (II)**

GPT:

- Més particions  
  → Permet moltes més divisions del disc.

- Suport discs grans  
  → Adequat per discs moderns de gran capacitat.

- Identificadors GUID  
  → Cada partició té un identificador únic.

---

# 🔸 **Tipus de Particions**

- Primària → instal·lar SO  
  → Pot contenir directament un sistema operatiu.

- Estesa → contenidor  
  → Serveix per crear múltiples particions lògiques.

- Lògica → dins estesa  
  → Funcionen com particions independents.

Organitzen el disc en espais lògics.

---

# 🔸 **Sistemes d’Arxius (Propietaris)**

FAT / FAT32:

- Compatible  
  → Funciona en molts sistemes operatius.

- Limitació 4GB per fitxer  
  → No permet fitxers molt grans.

---

# 🔸 **Sistemes d’Arxius (Propietaris) (II)**

NTFS:

- Permisos  
  → Control d’accés per usuari.

- Seguretat  
  → Inclou mecanismes de protecció avançats.

- Grans volums  
  → Admet discs i fitxers de gran mida.

---

# 🔸 **Sistemes d’Arxius (Propietaris) (III)**

HFS+ / APFS (Apple):

- Optimitzats per ecosistema Apple  
  → Dissenyats per funcionar amb macOS.

---

# 🔸 **Formatació d’un Disc**

Procés de preparació del disc:

- Creació sistema d’arxius  
  → Defineix com s’organitzaran les dades.

- Organització en sectors i clústers  
  → Divideix físicament el disc en unitats gestionables.

- Permet llegir i escriure dades  
  → Fa que el disc sigui usable pel sistema operatiu.

---

# 🔸 **Clonació**

Còpia exacta d’un sistema.  
→ Replica sistema operatiu, configuracions i dades.

Tipus:

- Basada en sectors  
- Basada en dades  
- Imatge virtual  

---

# 🔸 **Clonació (II)**

Utilitat:
- Restauració  
- Desplegament massiu  
- Còpies seguretat  

---

# 🔸 **1.3 Instal·lació de Sistemes Operatius Lliures**

Permeten:

- Estudiar  
- Modificar  
- Distribuir  

Fases:

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

# 🔸 **Punts de Muntatge**

Directori on s’accedeix a una partició.

Exemples:

- /  
- /home  
- /var  
- /mnt  

Estructura jeràrquica en arbre invertit.

---

# 🔸 **Dual Boot**

Permet:

- Instal·lar dos SO en un mateix equip  
- Seleccionar a l’arrencada  

Requereix:

- Particions separades  
- Gestor d’arrencada  

---

# 🔸 **1.4 Gestor d’Arrencada**

BIOS → llegeix MBR  
UEFI → carrega fitxer EFI  

Transfereix control al carregador del sistema.

---

# 🔸 **Gestor d’Arrencada Windows (BCD)**

Magatzem de configuració:

- bcdedit (mode text)  
- msconfig (mode gràfic)  

Fitxers:

- bootmgr  
- winload  
- winresume  

---

# 🔸 **Gestor d’Arrencada Linux (GRUB)**

GRUB 2  

Fitxers:

- /etc/default/grub  
- /boot/grub/grub.cfg  

Comanda:

sudo update-grub  

---

# 🔸 **1.5 Llicències**

Tipus:

- OEM  
- Retail  
- Volum  

En sistemes lliures:

- GPL  
- BSD  
- MIT  
- Apache  

---

# 🔸 **Actualització del Sistema Operatiu**

Objectiu:

- Correcció errors  
- Millores seguretat  
- Noves funcionalitats  

A Ubuntu:

sudo apt update  
sudo apt upgrade  
snap refresh  

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