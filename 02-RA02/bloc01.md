---
marp: true
paginate: true
theme: default

header: "RA02 – Instal·lació de Sistemes Operatius · Bloc 1 – Fonaments del Sistema Operatiu"
footer: "Mòdul 0374 – Administració de Sistemes Operatius"

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

**SMX01 — Administració de Sistemes Operatius**  
**Professor — Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **1.1 Què és un Sistema Operatiu?**

Un **Sistema Operatiu (S.O.)** és el programari que:  
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

El S.O. organitza les dades en forma de:  
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

El S.O. controla:  
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

RA02 (p. 9) detalla que el S.O. ha de garantir:  
- Bloqueig d'arxius o parts d'un arxiu  
- Evitar condicions de cursa  
- Assegurar integritat de la informació  

**Esquema conceptual:**

```

Procés A ----
--> Fitxer X (bloqueig exclusiu)
Procés B ----/

```

Només un procés pot modificar un recurs al mateix temps.

---

<!-- SLIDE 8 -->
# 🔸 **Gestió de l'Espai del Disc**

Mètodes d'assignació segons RA02 (p. 10):  
- **Assignació contigua** (ràpida, pot fragmentar)  
- **Assignació enllaçada** (flexible, lenta en accés seqüencial)  
- **Assignació indexada** (equilibri rendiment/eficiència)  

El S.O. també controla:
- Espai lliure  
- Expansió d'arxius  
- Recuperació davant errors  

---

<!-- SLIDE 9 -->
# 🔸 **Gestió de Memòria (1/2)**

La memòria es gestiona en capes (RA02 p. 11–14):  

```

+------------------+  Registres (CPU)
|      Ràpida      |
+------------------+  Memòria cau
|    Molt ràpida   |
+------------------+  RAM
|    Intermitja    |
+------------------+  Disc (swap)
|     Lenta        |

```

- El S.O. assigna memòria a processos  
- Allibera memòria quan ja no és necessària  
- Garanteix que diversos programes puguin conviure  

---

<!-- SLIDE 10 -->
# 🔸 **Gestió de Memòria (2/2)**

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

<!-- SLIDE 11 -->
# 🔸 **Gestió de Processos (1/2)**

Segons RA02 (p. 15):  
Un **procés** és una instància d'un programa en execució.

El S.O. gestiona:
- Creació i terminació  
- Planificació  
- Comunicació entre processos  
- Assignació de recursos  

---

<!-- SLIDE 12 -->
# 🔸 **Gestió de Processos (2/2): PCB**

El *Process Control Block* conté:  
- Identificador del procés (PID)  
- Estat  
- Comptadors de programa  
- Registres de CPU  
- Informació de memòria  
- Fitxers oberts  

**Esquema:**

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

<!-- SLIDE 13 -->
# 🔸 **Gestió d'Entrada/Sortida (1/2)**  
*(RA02 p. 16–18)*

Funcions:
- Gestionar comunicació amb dispositius  
- Coordinar velocitats i protocols  
- Abstreure maquinari amb controladors (drivers)  

Tipus de dispositius:
- Entrada: teclat, ratolí  
- Sortida: monitor, impressora  
- Entrada/Sortida: disc, USB, targeta de xarxa  

---

<!-- SLIDE 14 -->
# 🔸 **Gestió d'Entrada/Sortida (2/2)**

Mètodes de comunicació:
- **Programada:** la CPU espera  
- **Interrupcions:** el dispositiu avisa quan ha acabat  
- **DMA:** accés directe a memòria (molta eficiència)  

**Esquema conceptual del DMA:**

```

Dispositiu ──> Controlador DMA ──> Memòria
|
Notifica CPU

```

---

<!-- SLIDE 15 -->
# **Resum del Bloc 1**

- El S.O. gestiona processos, memòria, arxius i dispositius  
- Les rutes i permisos estructuren l'accés a la informació  
- La memòria es gestiona jeràrquicament i amb tècniques com paginació i swapping  
- Els processos són controlats a través del PCB  
- Els dispositius requereixen controladors i mecanismes com DMA per a un bon rendiment  

---

<!-- SLIDE 16 -->
# **Fi del Bloc 1**


