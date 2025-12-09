# RA05 - Resum virtualització RA05

**User:** Héctor Pascual Comín (hector.pascual@iescarlesvallbona.cat)  
**Created:** 11/25/2025 14:16:37  
**Updated:** 12/2/2025 14:05:25  
**Exported:** 12/4/2025 10:23:39  
**Link:** [https://chatgpt.com/g/g-p-692498384d248191b180cdd1859e66e9/c/6925ac33-2a2c-832b-b2a5-a306ee622b1e](https://chatgpt.com/g/g-p-692498384d248191b180cdd1859e66e9/c/6925ac33-2a2c-832b-b2a5-a306ee622b1e)  

## Prompt:
M02.RA5.TEORIA (1) (1) (1) (2).pdf

PDF

RA05 - Virtualització

## Response:
Perfecte, Héctor — ja he llegit **tot el teu document complet de RA05 – Virtualització** (88 pàgines) i el puc fer servir com a base per crear **tot el que necessitis**: temari, pràctiques, exercicis, exàmens, activitats guiades o una versió reescrita amb el “rol de Professor Héctor”.

A continuació et faig un **resum estructurat del contingut del PDF** (amb cites directes del document) i després em dius _què vols que generi exactament_.

* * *

📘 **RA05 – Virtualització**
============================

Basat en el document _M02.RA5.TEORIA_ M02.RA5.TEORIA (1) (1) (1) (2)

En aquesta RA, els alumnes aprenen:

* * *

**🔹 1. Introducció a la virtualització**
-----------------------------------------

**(Pàg. 2–14)**

El document explica:

*   Naixement de la virtualització (anys 60 → auge als 2000) M02.RA5.TEORIA (1) (1) (1) (2)
*   Objectiu: executar diversos sistemes dins d’un mateix equip, evita arrencada dual, optimitza recursos
*   Tipus:
    *   Virtualització de servidors
    *   Escriptori
    *   Xarxes
    *   Aplicacions
    *   Emmagatzematge M02.RA5.TEORIA (1) (1) (1) (2)
*   Diferència entre **màquina real** i **màquina virtual**
*   **Hipervisors tipus 1 i tipus 2**
*   **Contenidors** i comparativa clara amb hipervisors (taula de la pàg. 12) M02.RA5.TEORIA (1) (1) (1) (2)

* * *

**🔹 2. Avantatges i inconvenients**
------------------------------------

**(Pàg. 15–24)**

**Avantatges MV**

*   Execució simultània de SO
*   Compatibilitat d’aplicacions d’altres plataformes
*   Preservació de sistemes antics
*   Clonació, empaquetament, proves sense risc
*   Reducció de costos M02.RA5.TEORIA (1) (1) (1) (2)

**Inconvenients MV**

*   Rendiment inferior i variable
*   Dependència del hipervisor
*   Fallada de l’amfitrió = totes les VM afectades M02.RA5.TEORIA (1) (1) (1) (2)

**Avantatges / inconvenients contenidors**

*   Aïllament, transportables, pèrdua mínima de rendiment
*   Problemes amb aplicacions gràfiques, persistència de dades, dependència del SO host

* * *

**🔹 3. Programari lliure i propietari per virtualitzar**
---------------------------------------------------------

**(Pàg. 25–34)**

### Tipus d’hipervisors

*   **Tipus 1:** Hyper-V, VMware ESXi, XenServer
*   **Tipus 2:** VirtualBox, VMware Workstation, Parallels

### Llicències

*   Programari lliure: VirtualBox (GPL)
*   Propietari: VMware, Parallels (+ funcionalitats) M02.RA5.TEORIA (1) (1) (1) (2)

* * *

**🔹 4. Crear màquines virtuals**
---------------------------------

**(Pàg. 35–44)**

Guia pas a pas per VirtualBox:

1.  **Crear** màquina → Nom, SO, RAM, disc virtual
2.  **Tipus de disc:** VDI, VHD, VMDK, HDD
3.  Opció “_dinàmic_” o “_mida fixa_”
4.  Afegir ISO
5.  Explicació de les **Guest Additions**: resolució, carpetes compartides, copiar/enganxar… M02.RA5.TEORIA (1) (1) (1) (2)

* * *

**🔹 5. Configuració avançada de VM**
-------------------------------------

**(Pàg. 45–78)**

El document inclou:

### Configuració general

*   Bàsic, Avançat, Descripció, Xifratge del disc

### Sistema

*   Placa base (ordre arrencada, EFI, RAM)
*   Processadors (nuclis, PAE/NX)
*   Acceleració (VT-x/AMD-V, paravirtualització)

### Pantalla

*   Memòria de vídeo
*   Nombre de monitors
*   Acceleració 3D

### Emmagatzematge

*   Controladors IDE / SATA
*   Discs, ISO
*   SSD virtual, hot-plug

### Audio, Xarxa, USB, Ports sèrie, Carpetes compartides

Inclou captures i esquemes molt clars. M02.RA5.TEORIA (1) (1) (1) (2)

* * *

**🔹 6. Proves de rendiment (Benchmark)**
-----------------------------------------

**(Pàg. 79–88)**

*   Definició de benchmark
*   Fases: Planificació → Captura → Anàlisi → Pla acció → Millores
*   Eines: Geekbench, Novabench, UserBenchmark, VMMark
*   Conceptes d’escalabilitat, recursos, CPD, consum energètic M02.RA5.TEORIA (1) (1) (1) (2)

* * *

🔧 I ara, què vols que generi?
==============================

Puc fer qualsevol de les següents:

### ✔ **1\. Temari complet de la RA05 reescrit “en estil professor Héctor”**

Amb un to més humà, clar, pràctic i amb exemples.

### ✔ **2\. Activitats i exercicis per cada apartat**

*   Activitats tipus “fes-ho tu”
*   Exercicis de reflexió
*   Pràctiques amb VirtualBox
*   Preguntes per exàmens

### ✔ **3\. Pràctiques d’aula**

*   Crear 2 màquines virtuals
*   Configurar xarxes NAT → pont
*   Fer benchmark i analitzar resultats
*   Comparar hipervisors

### ✔ **4\. Examen teòric + examen pràctic**

*   Amb solucions
*   Format múltiple resposta, desenvolupament o mixt

### ✔ **5\. Versió resumida per alumnes**

*   1–2 pàgines tipus “chuleta” oficial

### ✔ **6\. Carpeta de professor**

Amb:

*   Rúbriques
*   Solucions
*   Guies d’avaluació contínua

* * *

👉 Digues: **què vols que et generi ara?**
==========================================

Temari? Pràctiques? Examen? Resum? Tot el paquet de la RA05?

## Prompt:
M02.RA5.A2 Creació i configuració de dues màquines virtuals (1).pdf

PDF

## Response:
Perfecte, Héctor. Ja tinc **la teoria de la RA05** i **l’activitat A2** completa (creació i configuració de dues màquines virtuals) carregada i revisada. A partir d’aquí puc generar exactament el que vulguis: la pràctica reformulada “Rol Professor Héctor”, la versió per alumnes, la guia de correcció, o afegir activitats extres.

De moment et deixo **una versió millorada i preparada per entregar als alumnes**, basada fidelment en el teu PDF **M02.RA5.A2** M02.RA5.A2 Creació i configurac…, però amb estructura molt més clara, llenguatge docent i espais per posar captures, tal com tu demanes a classe.

* * *

🖥️ **RA05 – A2 · Creació i configuració de dues màquines virtuals**
====================================================================

**Rol: Professor Héctor – ASIX / SMX**

🎯 **Objectiu**
---------------

En aquesta activitat crearàs **dues màquines virtuals** (Windows i Ubuntu), les configuraràs amb maquinari personalitzat i verificaràs la connectivitat entre **l’amfitrió → Ubuntu** mitjançant **ping**.

És imprescindible documentar **cada pas amb captures de pantalla** i comentaris, igual que fem al PWP de teoria.

* * *

🟦 **PART 1 — Màquina Virtual Windows**
=======================================

### **1\. Nom de la màquina**

El nom seran **les teves inicials en majúscules**.  
Exemple: _Joan Pérez García → JPG_

📸 _Captura 1: Creació de la màquina i nom introduït_

* * *

### **2\. Configuració del sistema**

*   **Tipus:** Microsoft Windows
*   **Versió:** Windows 10 (64-bit)
*   **RAM:** 3 GB
*   **Disc dur:** 40 GB (_mida dinàmica_)
*   **CPU:** 2 processadors

📸 _Captura 2: Pantalla de configuració general i maquinari_

* * *

### **3\. Instal·lació del sistema operatiu**

*   Muntar la **ISO de Windows 10** a la unitat òptica de VirtualBox
*   Arrencar la màquina
*   Seguir l’assistent d’instal·lació

📸 _Captura 3: ISO muntada / arrencada de Windows_  
📸 _Captura 4: Instal·lació iniciada_

* * *

🟧 **PART 2 — Màquina Virtual Ubuntu**
======================================

### **1\. Nom de la màquina**

El nom seran **les teves inicials al revés**.  
Exemple: _Joan Pérez García → GPJ_

📸 _Captura 5: Creació de la VM amb nom invertit_

* * *

### **2\. Configuració del sistema**

*   **Tipus:** Linux
*   **Versió:** Ubuntu (64-bit)
*   **RAM:** 2 GB
*   **Disc dur:** 25 GB (_mida fixa_)
*   **CPU:** 1 processador

📸 _Captura 6: Configuració de maquinari Ubuntu_

* * *

### **3\. Instal·lació del sistema operatiu**

*   Muntar la **ISO d’Ubuntu**
*   Arrencar
*   Seguir l’assistent

📸 _Captura 7: ISO muntada / arrencada d’Ubuntu_  
📸 _Captura 8: Instal·lació finalitzada_

* * *

🟩 **PART 3 — Prova de connexió (ping)**
========================================

### **1\. Comprovar configuració de xarxa**

A VirtualBox → Configuració → **Xarxa**  
✔ Assegura’t que està en **NAT** (ve per defecte)

📸 _Captura 9: Interfície configurada com NAT_

* * *

### **2\. Obtenir IP d’Ubuntu**

A Ubuntu, obre un **Terminal** i executa:

```
ip a
```

Busca la interfície _ens33_, _ens_, o _eth0_. Sol ser del rang **10.x.x.x**.

📸 _Captura 10: Resultat de `ip a` amb la IP remarcada_

* * *

### **3\. Fer ping des de l’amfitrió**

A la teva màquina principal (Windows o Linux):

```
ping [IP_de_Ubuntu]
```

Exemple:

```
ping 10.0.2.15
```

Ha de respondre correctament.

📸 _Captura 11: Ping exitós des de l’amfitrió_

* * *

📝 **Criteris d’avaluació**
===========================

✔ **Noms de les màquines correctes**  
(Windows = inicials normals · Ubuntu = inicials inverses)

✔ **Configuracions correctes**

*   Windows → 3GB RAM, 40GB dinàmic, 2 CPU
*   Ubuntu → 2GB RAM, 25GB fixa, 1 CPU

✔ **Captures clares i ordenades** per cada pas  
(com al PWP de classe)

✔ **Ping des de l’amfitrió → Ubuntu amb resposta OK**

* * *

📂 **Vols que et generi també...?**
===================================

Puc fer-te:

### 🔸 Versió PDF llesta per entregar

### 🔸 Rúbrica de correcció per professors

### 🔸 Solució del ping amb exemples reals

### 🔸 Plantilla perquè els alumnes la completin

### 🔸 Versió "pràctica 100% guiada" amb explicacions llargues

### 🔸 Activitat avançada (NAT + Host-Only + ping creuat)

Només digues **què vols exactament**.

## Prompt:
M02.RA5.A2 Creació i configuració de dues màquines virtuals (1).pdf

PDF

## Response:
Perfecte, Héctor — ja tinc carregat **l’arxiu correcte** _M02.RA5.A2 Creació i configuració de dues màquines virtuals_ M02.RA5.A2 Creació i configurac….

Abans de generar res més, necessito que em diguis **què vols que faci exactament amb aquest document**. Et deixo les opcions habituals que em demanes, així només has de triar:

* * *

🔧 **Què vols que generi amb l’A2?**
====================================

### ✔ **A) Reescriure l’activitat en estil “Professor Héctor”**

Molt clara, directa, amb estructura impecable i llesta per penjar a Classroom.

### ✔ **B) Fer la versió “per alumnes” amb espais per afegir captures**

Una plantilla editable perquè la completin.

### ✔ **C) Generar un PDF ja maquetat llest per entregar**

En format net, coherent i imprimible.

### ✔ **D) Fer la guia de correcció / rúbrica del professorat**

Amb criteris exactes, puntuació i errors habituals.

### ✔ **E) Fer una versió ampliada per SMX i una per ASIX**

Adaptant el nivell.

### ✔ **F) Afegir una Part 4 més avançada (host-only, pont, ping creuat, etc.)**

### ✔ **G) Transformar l’activitat en una pràctica llarga amb teoria + passos + preguntes**

### ✔ **H) Convertir-ho en un examen pràctic per aula / laboratori**

* * *

👉 **Quina opció vols?**
========================

Posa’m la lletra (A, B, C…) o digues “vull X i Y” i ho genero ara mateix.

## Prompt:
amfitrió i host, diferències

## Response:
Aquí tens una **explicació clara, curta i 100% correcta tècnicament** sobre les diferències entre **amfitrió** i **host**, que sovint generen confusió.

* * *

🖥️ **Amfitrió vs. Host — Són el mateix?**
==========================================

Sí: **“amfitrió” = “host”**  
La diferència és només d’idioma.

*   **Amfitrió** → terme en **català**
*   **Host** → terme en **anglès**

Tots dos signifiquen exactament el mateix en virtualització:

👉 **El sistema físic real on tens instal·lat l’hipervisor i des d’on crees i executes màquines virtuals.**

* * *

🔍 Lliçó ràpida
===============

| Terme | Idioma | Significat |
| --- | --- | --- |
| **Amfitrió** | Català | L’ordinador físic real (on s’instal·la VirtualBox, VMware, etc.) |
| **Host** | Anglès | Exactament el mateix: la màquina física real |
| **Convidat** | Català | El sistema operatiu que s’executa a dins d'una VM |
| **Guest** | Anglès | Equivalent al “convidat” |

* * *

🧠 Exemple:
===========

*   Tens un portàtil Windows → **això és l’amfitrió / host**
*   A dins instal·les VirtualBox
*   Crees una màquina virtual Ubuntu → **això és el convidat / guest**

* * *

❗ Important per a la RA05:
==========================

En el document de teoria (M02.RA5.TEORIA) diu:

> “La màquina real s'anomena màquina **amfitrió** i les màquines virtuals s'anomenen **màquines hosts**.” M02.RA5.TEORIA (1) (1) (1) (2)

Aquí hi ha una **confusió del document**, perquè en anglès:

*   **host** = amfitrió
*   **guest** = convidat

Per tant:  
✔ **Amfitrió = host**  
✔ **Convidat = guest**

* * *

Si vols, et preparo:
====================

✅ Una diapositiva per al PWP amb el quadre comparatiu  
✅ Una explicació curta per posar al Classroom  
✅ Una nota d’aclariment per afegir al PDF de teoria  
Només digues què prefereixes.



---
Powered by [ChatGPT Exporter](https://www.chatgptexporter.com)