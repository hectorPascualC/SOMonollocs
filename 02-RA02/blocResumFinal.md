---
marp: true
paginate: true
theme: default

header: "RA02 – RESUM EXAMEN"
footer: "SO Monolloc · SMX"

---

# **RESUM RA02 – SISTEMES OPERATIUS**

Què has de saber per l'examen

---

# 🔸 **QUÈ ÉS UN SO**

El sistema operatiu:

- Gestiona el maquinari  
- Executa aplicacions  
- Controla memòria, processos i dispositius  

És el **pont entre usuari i hardware**

---

# 🔸 **FUNCIONS CLAU DEL SO**

- Gestió d’arxius  
- Gestió de memòria  
- Gestió de processos  
- Gestió d’entrada/sortida  

TOT l’examen gira aquí

---

# 🔸 **GESTIÓ DE MEMÒRIA (IDEA CLAU)**

Memòria en capes:

CPU → Cache → RAM → Disc  

Com més lluny → més lent

---

# 🔸 **TÈCNIQUES DE MEMÒRIA**

- Paginació → blocs fixes  
- Segmentació → blocs variables  
- Swapping → mou processos al disc  
- Memòria virtual → més RAM “fictícia”  

Pregunta típica d'examen

---

# 🔸 **MEMÒRIA VIRTUAL**

- El programa usa **adreces virtuals**
- La CPU treballa amb **adreces físiques**
- La MMU tradueix  (Memory Management Unit)

Si no està a RAM → page fault (dada o instrucció que necessita el programa no està a la memòria RAM)

---

# 🔸 **PROCESSOS**

Procés = programa en execució  

El SO controla:

- execució  
- recursos  
- planificació  

---

# 🔸 **PCB (Process Control Block)**

Conté:

- PID → identificador  
- Estat → running, waiting  
- Registres → dades CPU  
- Memòria → adreces  
- Fitxers → recursos oberts  

És el “DNI del procés”

---

# 🔸 **ENTRADA / SORTIDA**

Mètodes:

- Programada → CPU espera  
- Interrupcions → dispositiu avisa  
- DMA → directe a RAM  

DMA = més eficient

---

# 🔸 **ARQUITECTURA DEL SO**

- 32 bits → limit 4GB RAM  
- 64 bits → actual  

determina capacitat

---

# 🔸 **TIPUS D’ARQUITECTURA**

Monolítica:
- ràpida
- menys segura

Micronucli:
- més segura
- més modular

---

# 🔸 **PARTICIONS (CLAU)**

MBR:
- màx 4 particions  
- limitació mida  

GPT:
- moltes particions  
- discs grans  

---

# 🔸 **TIPUS DE PARTICIONS**

- Primària → SO  
- Estesa → contenidor  
- Lògica → dins estesa  

---

# 🔸 **SISTEMES D’ARXIUS**

Windows:
- FAT → compatible  
- NTFS → seguretat  

Linux:
- ext4  
- swap  

defineix com es guarden dades

---

# 🔸 **FORMATACIÓ**

- crea sistema d’arxius  
- organitza en sectors i clústers  

fa usable el disc

---

# 🔸 **CLONACIÓ**

- còpia exacta del sistema  

Tipus:
- sectors  
- dades  
- imatge  

útil per backups

---

# 🔸 **LINUX**

Distribucions:
- Ubuntu, Debian, etc.

Sistema lliure:
- modificar  
- distribuir  

---

# 🔸 **PUNTS DE MUNTATGE**

Tot penja de:

```

/

```

Exemples:

- /home  
- /var  
- /usr  

arbre invertit

---

# 🔸 **DUAL BOOT (MOLT IMPORTANT)**

- 2 sistemes operatius  
- 2 particions  

només un funciona cada vegada

---

# 🔸 **INSTAL·LACIÓ DUAL BOOT**

1. Instal·lar Windows  
2. Redimensionar disc  
3. Instal·lar Ubuntu  

---

# 🔸 **GESTOR D’ARRENCADA**

És el programa que:

- s'executa en iniciar  
- permet triar SO  

Exemples:
- GRUB (Linux)  
- bootmgr (Windows)

---

# 🔸 **BIOS vs UEFI**
Firmware ordinador. Programari s'excuta abans del SO

BIOS:
- antic  

UEFI:
- modern  
- GPT  

---

# 🔸 **RESUM FINAL**

- SO gestiona TOT  
- Memòria → paginació, virtual  
- Processos → PCB  
- Disc → particions + FS  
- Instal·lació → Windows + Linux  
- Dual boot → gestor arrencada  

---

# **FI – PREPARAT PER EXAMEN**
