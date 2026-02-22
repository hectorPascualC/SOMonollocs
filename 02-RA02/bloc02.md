---
marp: true
paginate: true
theme: default

header: "RA02 – Instal·lació de Sistemes Operatius · Bloc 2 – Arquitectura del Sistema Operatiu"
footer: "Mòdul 0374 – SO Monolloc"

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
# **RA02 – Bloc 2**
## **Arquitectura del Sistema Operatiu**

**SMX01 — SO Monolloc**  
**Professor — Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **Arquitectura del Sistema Operatiu**

L’arquitectura defineix:
- Com es representen les dades internament  
- Com s’organitzen els components del sistema  
- Com interactuen nucli, serveis i maquinari  

Actualment:
- 32 bits (antic)
- 64 bits (estàndard actual)

CPU, sistema operatiu i aplicacions han de compartir arquitectura.

---

<!-- SLIDE 3 -->
# 🔸 **Arquitectura segons mida de dades**

```
8 bits  → sistemes antics
16 bits → sistemes històrics
32 bits → límit 4 GB RAM
64 bits → grans capacitats de memòria

```

✔ Major mida → més capacitat de càlcul  
✔ Millor rendiment  
✔ Millor gestió de memòria  

---

<!-- SLIDE 4 -->
# 🔸 **Tipus d'Arquitectura del SO**

- **Arquitectura Monolítica**
- **Arquitectura de Micronucli**

Cada model té avantatges i inconvenients.

---

<!-- SLIDE 5 -->
# 🔸 **Arquitectura Monolítica**

Exemple: **Linux**

Característiques:

- Tot s'executa dins del nucli
- Drivers integrats al kernel
- Accés directe al maquinari

**Esquema:**

```

Aplicacions
↓
Nucli (tot integrat)
↓
Maquinari

```

---

<!-- SLIDE 6 -->
# 🔸 **Avantatges i Inconvenients (Monolítica)**

- Alt rendiment  
- Comunicació interna ràpida  
- Simplicitat estructural  

- Si falla el nucli → cau tot el sistema  
- Difícil manteniment  
- Poc modular  

---

<!-- SLIDE 7 -->
# 🔸 **Arquitectura de Micronucli**

Exemple: **Windows / macOS**

Característiques:

- Nucli mínim
- Serveis executats en mode usuari
- Comunicació mitjançant missatges

**Esquema:**

```
Aplicacions
↓
Serveis (drivers, FS, xarxa)
↓
Micronucli
↓
Maquinari

```

---

<!-- SLIDE 8 -->
# 🔸 **Avantatges i Inconvenients (Micronucli)**

- Millor seguretat  
- Major modularitat  
- Errors aïllats  

- Lleugerament menys rendiment  
- Comunicació més complexa  

---

<!-- SLIDE 9 -->
# 🔸 **Comparativa Directa**

| Aspecte | Monolítica | Micronucli |
|----------|------------|------------|
| Rendiment | Molt alt | Alt |
| Modularitat | Baixa | Alta |
| Seguretat | Mitjana | Alta |
| Manteniment | Complex | Flexible |

---

<!-- SLIDE 10 -->
# 🔸 **Gestió d’Operacions d’Entrada/Sortida**

En escenaris amb:

- Teclat
- Impressora
- Disc dur
- Xarxa

El sistema ha de:

- Coordinar interrupcions
- Gestionar buffers
- Prioritzar processos

---

<!-- SLIDE 11 -->
# 🔸 **Paper dels Controladors (Drivers)**

Els drivers:
- Permeten comunicar SO ↔ maquinari
- S’integren al nucli o com a servei
- Traduixen ordres genèriques a ordres específiques

Sense drivers → el dispositiu no funciona.

---

<!-- SLIDE 12 -->
# 🔸 **DMA (Direct Memory Access)**

DMA permet:
- Transferir dades directament a memòria
- Alliberar la CPU
- Millorar rendiment

**Esquema:**

```

Dispositiu
↓
Controlador DMA
↓
Memòria
↘
CPU (només notificació)

```

---

<!-- SLIDE 13 -->
# 🔸 **Optimització del Rendiment**

Per millorar rendiment:

- Utilitzar DMA (aprofitar el SO i drivers al màxim)
- Drivers actualitzats
- Arquitectura adequada
- 64 bits
- RAM suficient

---

<!-- SLIDE 14 -->
# **Resum del Bloc 2**

- L’arquitectura defineix l’estructura interna del SO  
- 64 bits és l’estàndard actual  
- Monolítica → rendiment alt  
- Micronucli → més modular i segura  
- Drivers i DMA són clau per al rendiment  

---

<!-- SLIDE 15 -->
# **Fi del Bloc 2**

