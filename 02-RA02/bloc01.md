---
marp: true
paginate: true
theme: default

header: "RA02 – Instal·lació de Sistemes Operatius · Bloc 1 – Fonaments del Sistema Operatiu"
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
# **RA02 – Bloc 1**
## **Fonaments del Sistema Operatiu**

**SMX01 — SO Monolloc**  
**Instal·la sistemes operatius, relacionant-ne les característiques amb el maquinari de l'equip i el programari d'aplicació**
**Professor — Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **1.1 Què és un Sistema Operatiu?**

Un **SO** és el programari que:  
- Gestiona els recursos del sistema  
- Permet l'execució d'aplicacions  
- Ofereix un entorn d'interacció a l'usuari  
- Garanteix l'accés segur i ordenat al maquinari  
- Proporciona un entorn fàcil d'utilitzar  
- Gestiona memòria, processos, arxius i dispositius  
- Controla la seguretat i la protecció del sistema  
- Detecta i gestiona errors  

---

<!-- SLIDE 3 -->
# 🔸 **Funcions Bàsiques del Sistema Operatiu**

- **Gestió d'arxius**  
- **Gestió de processos**  
- **Gestió de dispositius d'E/S**  
- **Gestió de memòria**  
- **Seguretat i protecció**  
- **Monitoratge i detecció d'errors**  

Aquestes funcions permeten abstraure el maquinari i presentar-lo de manera usable a aplicacions i usuaris.

---

<!-- SLIDE 4 -->
# 🔸 **Gestió d'Arxius (1/3)**  

El SO organitza les dades en forma de:  
- **Arxius**  
- **Directoris**  
- **Rutes (absolutes i relatives)**

Funcions principals:

- Crear, eliminar, obrir i tancar arxius  
- Gestionar permisos i propietats  
- Controlar accessos simultanis  
- Mantenir la consistència del sistema d'arxius  

---

<!-- SLIDE 5 -->
# 🔸 **Jerarquia i Rutes d'Arxius (Esquema)**

```

/
├── home/
│   ├── pau/
│   └── marc/
├── etc/
├── var/
└── usr/

```

- **Ruta absoluta:** comença en `/`  
  Exemple: `/home/pau/document.txt`  
- **Ruta relativa:** depèn del directori actual  
  Exemple: `../marc/projecte/`  

---

<!-- SLIDE 6 -->
# 🔸 **Gestió de Permisos i Accessos**

El SO controla:  
- Propietari  
- Grup  
- Permisos (lectura, escriptura, execució)

Objectius:
- Protegir dades  
- Evitar accessos no autoritzats  
- Garantir coherència en entorns multiusuari  

---

<!-- SLIDE 7 -->
# 🔸 **Accés Simultani als Arxius**

El SO ha de garantir:  
- Bloqueig d'arxius o parts d'un arxiu  
- Evitar **condicions de cursa** (2 processos → mateix arxiu → mateix temps)
- Assegurar **integritat de la informació** (no corrompre dades, no perdua dades, fitxer no estat inconsistent)

> Només un procés pot modificar un recurs al mateix temps.

---

<!-- SLIDE 8 -->
# 🔸 **Gestió de l'Espai del Disc**

Mètodes d'assignació:  
- **Assignació contigua** (ràpida, pot fragmentar) → blocs seguits
- **Assignació enllaçada** (flexible, lenta en accés seqüencial) → blocs poden estar separats
- **Assignació indexada** (equilibri rendiment/eficiència) → bloc especial desa totes adreces 

El SO també controla:
- Espai lliure  
- Expansió d'arxius  
- Recuperació davant errors  

---

<!-- SLIDE 9 | 1 -->
# 🔸 **Gestió de Memòria (1/9)**

La memòria es gestiona en capes:  

```
+------------------+  
|      Ràpida      |  Registres (dins CPU, és la memòria immediata del processador)
+------------------+  
|    Molt ràpida   |  Memòria cau (emmagatzena temporalment les dades i instruccion)
+------------------+  
|    Intermitja    |  RAM (on carreguen els programes i les dades mentre s’estan executant)
+------------------+  
|     Lenta        |  Disc (SO mou dades, que no utilitzen des de RAM, cap al disc, àrea swap)
+------------------+ 

```

---

<!-- SLIDE 9 | 2 -->
# 🔸 **Gestió de Memòria (2/9)**  

**Com més a prop de la CPU, més ràpida és la memòria**
**Com més lluny, més lenta però més gran**

- El SO assigna memòria a processos  
- Allibera memòria quan ja no és necessària  
- Garanteix que diversos programes puguin conviure  

---

<!-- SLIDE 9 | 3 -->
# 🔸 **Gestió de Memòria (3/9)**

Tècniques principals:
- **Paginació** (mides fixes)  
- **Segmentació** (mides variables)  
- **Swapping** (intercanvi RAM ↔ disc)  
- **Memòria virtual** (espai lògic més gran que la RAM física)  

Objectius:
- Optimitzar rendiment  
- Evitar errors de memòria  
- Permetre multiprogramació  

---

<!-- SLIDE 9 | 4 -->
# 🔸 **Gestió de Memòria (4/9)**

🔹 **Paginació** (mides fixes)
La memòria es divideix en blocs de mida fixa → pàgines
El SO assigna pàgines als processos segons necessitat

- Evita **fragmentació externa** → forats entre blocs 
```bash
[ Procés A ][ FREE ][ Procés B ][ FREE ][ Procés C ]
```
- Permet memòria virtual
- Pot generar **fragmentació interna** → espai sobrant no utilitzat
```
[ 4KB ocupats ]
[ 2KB ocupats | 2KB buit ]
```

---

<!-- SLIDE 9 | 5 -->
# 🔸 **Gestió de Memòria (5/9)**

🔹 **Segmentació** (mides variables)
La memòria es divideix en segments de mida variable 
segons lògica del programa: codi, dades, pila…

- Organització més natural del programa
- Facilita protecció per segments
- Pot generar fragmentació externa

---

<!-- SLIDE 9 | 6 -->
# 🔸 **Gestió de Memòria (6/9)**

🔹 **Swapping** (intercanvi RAM ↔ disc)
El SO mou processos o dades entre la RAM i el disc (àrea swap) 
quan la memòria principal és insuficient

- Allibera RAM
- Permet continuar executant processos
- Disminueix el rendiment

> Aquest programa no s’està utilitzant → el trec complet de la RAM

---

<!-- SLIDE 9 | 7 -->
# 🔸 **Gestió de Memòria (7/9)**

Exemple swapping:
- Tens 8 GB de RAM
- Tens 7,8 GB ocupats
- Obres un programa nou
- El sistema mou dades inactives al swap
- Allibera RAM
- El sistema continua funcionant

---

<!-- SLIDE 9 | 8 -->
# 🔸 **Gestió de Memòria (8/9)**

🔹 **Memòria virtual** (espai lògic > RAM física)
Tècnica que permet que cada procés disposi d’un espai d’adreçament 
més gran que la RAM física real, utilitzant disc com a suport

- aïllament de processos
- Permet executar programes grans
- Basada en paginació 

> El programa el divideix en petites parts (pàgines) → mou només parts petites del programa

---

<!-- SLIDE 9 | 10 -->
# 🔸 **Gestió de Memòria (9/9)**

Exemple memòria virtual:
adreça → número que identifica una posició concreta dins de la memòria
- Usuari obre programa
- SO crea un espai de memòria virtual per al procés
- El programa rep adreces virtuals (0x00400000 - on està guardada la instrucció o dada dins RAM)
- La CPU accedeix a una adreça virtual 
- La MMU tradueix l'adreça virtual a una adreça física de la RAM (la posició real i exacta dins dels xips de memòria RAM)
- Si la dada és a la RAM → execució normal
- Si no hi és → es produeix un page fault
- El sistema carrega la pàgina necessària des del disc
- Es continua l’execució

---

<!-- SLIDE 10 | 1 -->
# 🔸 **Gestió de Processos (1/3)**

Un **procés** és programa en execució

El SO gestiona:
- Creació i terminació  
- Planificació  
- Comunicació entre processos  
- Assignació de recursos  

---

<!-- SLIDE 10 | 2 -->
# 🔸 **Gestió de Processos (2/3): PCB**

El **Process Control Block** conté:  
- Identificador del procés (PID)  
- Estat: executant, esperant, bloqueig
- Comptadors de programa: següent instrucció a executar
- Registres de CPU: valors instrucció actual
- Informació de memòria: adreces assignades al procès
- Fitxers oberts: recursos utilitzats oberts  

---

<!-- SLIDE 10 | 3 -->
# 🔸 **Gestió de Processos (3/3): PCB**

**Esquema:** (representació lògica i conceptual)

```

PCB {
PID: 1042
Estat: Running
Registres: [...]
Memòria: base=0x0040, limit=0x0AFF
Fitxers oberts: [fd0, fd1, ...]
}

```

---

<!-- SLIDE 11 | 1 -->
# 🔸 **Gestió d'Entrada/Sortida (1/2)**  

Funcions:
- Gestionar comunicació amb dispositius  
- Coordinar velocitats i protocols  
- Abstreure maquinari amb controladors (drivers)  

Tipus de dispositius:
- Entrada: teclat, ratolí  
- Sortida: monitor, impressora  
- Entrada/Sortida: disc, USB, targeta de xarxa  

---

<!-- SLIDE 11 | 2 -->
# 🔸 **Gestió d'Entrada/Sortida (2/2)**

Mètodes de comunicació:
- **Programada:** la CPU consulta repetidament estat dispositiu  
- **Interrupcions:** el dispositiu envia un senyal quan finalitza  
- **DMA:** accés directe a memòria (molta eficiència)  

**DMA**: Direct Memory Access, un dispositiu pot transmetre dades directes a la RAM 
sense que CPU hagi de copiar-les byte a byte

---

<!-- SLIDE 12 -->
# **Resum del Bloc 1**

- El SO gestiona processos, memòria, arxius i dispositius  
- Les rutes i permisos estructuren l'accés a la informació  
- La memòria es gestiona jeràrquicament i amb tècniques com paginació i swapping  
- Els processos són controlats a través del PCB  
- Els dispositius requereixen controladors i mecanismes com DMA per a un bon rendiment  

---

<!-- SLIDE 16 -->
# **Fi del Bloc 1**


