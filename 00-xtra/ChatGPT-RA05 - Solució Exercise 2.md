# RA05 - Solució Exercise 2

**User:** Héctor Pascual Comín (hector.pascual@iescarlesvallbona.cat)  
**Created:** 11/25/2025 20:44:13  
**Updated:** 12/2/2025 14:05:50  
**Exported:** 12/4/2025 10:23:00  
**Link:** [https://chatgpt.com/g/g-p-692498384d248191b180cdd1859e66e9/c/6926070a-c0c0-8332-b696-36b2e57d9d9f](https://chatgpt.com/g/g-p-692498384d248191b180cdd1859e66e9/c/6926070a-c0c0-8332-b696-36b2e57d9d9f)  

## Prompt:
M02.RA5.A2 Creació i configuració de dues màquines virtuals (1).pdf

PDF

RA05 - Exercise - 2

## Response:
Aquí tens **la resolució completa i comentada de l’Exercise 2 de la RA05**, basada exactament en l’enunciat del PDF que has pujat → M02.RA5.A2 Creació i configurac…

Ho deixo preparat **perquè els alumnes ho entenguin pas a pas**, i tu ho puguis posar directament al Classroom o utilitzar-ho com a _solució oficial_.

* * *

✅ **RA05 — Exercise 2: Creació i configuració de dues màquines virtuals (Windows i Ubuntu)**
============================================================================================

**Solució completa i comentada**

* * *

🧩 **PART 1 — MÀQUINA VIRTUAL WINDOWS**
=======================================

### **1️⃣ Nom de la màquina virtual**

*   S’han d'escriure les **inicials en ordre normal**.  
    **Exemple:** _Héctor Pascual Comín → HPC_

### **2️⃣ Configuració del sistema**

A VirtualBox → _Nova màquina_:

| Paràmetre | Valor |
| --- | --- |
| **Tipus** | Microsoft Windows |
| **Versió** | Windows 10 (64-bit) |
| **RAM** | **3 GB** (3072 MB) |
| **Disc dur** | **40 GB**, dinàmic |
| **CPU** | **2 CPUs** |

### **3️⃣ Instal·lació**

*   Muntar la ISO de Windows → _Arxiu ISO de Windows 10_.
*   Iniciar la MV → seguir l’instal·lador.

📌 **Captures obligatòries en el lliurament**

*   Creació de la màquina amb el nom
*   Configuració de RAM, CPU i disc
*   ISO muntada
*   Primera pantalla d’instal·lació de Windows

* * *

🧩 **PART 2 — MÀQUINA VIRTUAL UBUNTU**
======================================

### **1️⃣ Nom de la màquina virtual**

*   Inicials **invertides**.  
    **Exemple:** _Héctor Pascual Comín → CPH_

### **2️⃣ Configuració del sistema**

A VirtualBox → _Nova màquina_:

| Paràmetre | Valor |
| --- | --- |
| **Tipus** | Linux |
| **Versió** | Ubuntu (64-bit) |
| **RAM** | **2 GB** (2048 MB) |
| **Disc dur** | **25 GB**, fix |
| **CPU** | **1 CPU** |

### **3️⃣ Instal·lació**

*   Muntar ISO d’Ubuntu.
*   Iniciar la MV → seguir instal·lació.

📌 **Captures obligatòries**

*   Nom invertit
*   RAM, CPU i disc
*   ISO d’Ubuntu muntada
*   Pantalla d’instal·lació

* * *

🧩 **PART 3 — PROVA DE CONNECTIVITAT (PING)**
=============================================

**1️⃣ Comprovar que la xarxa és NAT**
-------------------------------------

A _Configuració → Xarxa_ de la MV Ubuntu:  
✔ Mode d'adaptador **NAT** (ja ve per defecte)

Captura obligatòria:

*   Pantalla NAT

* * *

**2️⃣ Obtenir la IP d’Ubuntu**
------------------------------

A Ubuntu → Terminal:

```
ip a
```

Buscar la interfície **ens33**, **enp0s3**, **eth0**…  
Normalment tindrà una IP **10.x.x.x**.

Captura obligatòria:

*   Terminal mostrant la IP

* * *

**3️⃣ Fer ping des de l’amfitrió**
----------------------------------

A la màquina principal (Windows/Linux):

```
ping 10.x.x.x
```

Si està bé configurat:  
→ **Respostes amb “bytes=…” i “ttl”**

Captura obligatòria:

*   Ping correcte des de l’amfitrió

* * *

📝 **CRITERIS DE CORRECCIÓ (segons el PDF)**
============================================

| Criteri | Pes |
| --- | --- |
| ✔ Windows té el nom correcte | 1 punt |
| ✔ Ubuntu té el nom invertit | 1 punt |
| ✔ Configuracions de maquinari correctes | 2 punts |
| ✔ Ping correcte des de l’amfitrió | 3 punts |
| ✔ Captures clares i ordenades | 3 punts |

* * *

🎓 **Vols que et faci la plantilla oficial de lliurament en PDF?**
==================================================================

Puc generar-te:

*   **Plantilla A4** amb espais per a cada captura
*   Text guiat i formatat
*   Estil Instructor Héctor (informal però tècnic)
*   Títol, capçalera i peu de pàgina

Només digues: **“Genera la plantilla PDF"** o “Fes-m’ho en format Word/Markdown”.

Quan vulguis continuem amb l’Exercise 3.



---
Powered by [ChatGPT Exporter](https://www.chatgptexporter.com)