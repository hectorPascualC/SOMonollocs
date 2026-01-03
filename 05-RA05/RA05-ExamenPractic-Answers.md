## PART 1 - Comprensió pràctica (3 punts)

### **1. Màquina real vs màquina virtual (1 punt)**

**Explica amb les teves paraules, la diferència entre una màquina real (amfitriona) i una màquina virtual**
**Indica un avantatge pràctic d'utilitzar màquines virtuals en un centre educatiu**

Quan parlem de **màquina real o amfitriona**, ens referim a l’ordinador físic: el que té el processador, la memòria RAM, el disc dur i la targeta de xarxa reals. És l’equip que encenem i utilitzem directament.

Una **màquina virtual**, en canvi, **no és física**. És un ordinador “simulat” per programari que utilitza una part dels recursos de la màquina real. Funciona com si fos un ordinador independent, però en realitat està allotjat dins l’amfitrió.

L’avantatge pràctic més clar en un **centre educatiu** és que podem tenir **diversos sistemes operatius i entorns de prova** en un mateix ordinador sense risc. Si un alumne trenca alguna cosa, s’esborra o es restaura la màquina virtual i no passa res al sistema real del centre.

Un error habitual és dir que la màquina virtual “substitueix” la real. No és així: **sempre depèn de la màquina amfitriona**.

---

### **2. Hipervisors (1 punt)**

**Indica la diferència entre un hipervisor de tipus 1 i un hipervisor de tipus 2**
**Posa un exemple real de cadascun i explica en quin context és més habitual utilitzar-los**

La diferència clau està en **on s’executa l’hipervisor**.

Un **hipervisor de tipus 1** s’executa **directament sobre el maquinari**, sense sistema operatiu intermedi. Això fa que tingui **millor rendiment i estabilitat**, i per això s’utilitza en entorns professionals o centres de dades. Un exemple clar és **VMware ESXi** o **Hyper-V Server**.

Un **hipervisor de tipus 2** s’executa **com una aplicació dins d’un sistema operatiu**. És el cas de **VirtualBox** o **VMware Workstation**. Té menys rendiment, però és molt més fàcil d’instal·lar i utilitzar.

En un **context educatiu**, el tipus 2 és el més habitual perquè permet treballar sobre Windows o Linux sense modificar l’equip del centre.

Un error típic és pensar que el tipus 2 és “dolent”: no ho és, simplement està pensat per a un **altre context d’ús**.

---

### **3. Discs virtuals (1 punt)**

**Explica la diferència entre un disc virtual de mida fixa i un disc virtual de mida dinàmica**
**Indica quin triaries per a una màquina virtual d'ús educatiu i per què**

Un **disc virtual de mida fixa** reserva **tot l’espai al disc real des del primer moment**. Això garanteix un rendiment més estable, però consumeix molt espai encara que no s’utilitzi.

Un **disc virtual de mida dinàmica** només ocupa **l’espai que realment necessita** a mesura que s’hi van guardant dades. És molt més flexible i eficient en espai.

Per a una **màquina virtual d’ús educatiu**, la millor opció és el **disc dinàmic**, perquè:

* Estalvia espai als ordinadors del centre
* Permet crear moltes màquines sense saturar el disc
* El rendiment és suficient per a pràctiques docents

Un error habitual és pensar que el disc dinàmic “canvia de mida tot sol” dins la màquina virtual: en realitat el que creix és **l’arxiu del disc al sistema amfitrió**.

---

## PART 2 - Supòsits pràctics (4 punts)

---

### **4. Configuració de xarxa en VirtualBox (2 punts)**

**Un alumne ha creat dues màquines virtuals a VirtualBox (Windows i Ubuntu) i vol que:**

* **Ambdues tinguin accés a Internet**
* **No sigui necessari configurar res a la xarxa real del centre**

**a) Quin tipus de xarxa hauria de configurar a VirtualBox?**
**b) Explica per què aquesta configuració compleix els requisits.**

La configuració correcta és **NAT**.

Amb **NAT**, la màquina virtual surt a Internet **a través de la connexió de l’amfitrió**, sense necessitat de tocar la xarxa real del centre ni demanar permisos especials.

Això compleix perfectament els requisits perquè:

* Les dues màquines tindran accés a Internet
* No cal configurar IPs, routers ni switches del centre
* És la configuració més segura i habitual en entorns educatius

Un error molt comú és proposar **adaptador pont**. Aquesta opció també dona Internet, però **sí que interactua amb la xarxa real**, cosa que l’enunciat diu explícitament que s’ha d’evitar.

---

### **5. Snapshots (instantànies) (2 punts)**

**Un alumne està a punt d'instal·lar programari nou dins d'una màquina virtual amb dades importants**

**a) Explica què és un snapshot i per a què serveix.**
**b) Indica quan és recomanable crear-ne un i què passaria si el sistema falla després**

Un **snapshot** és una **instantània de l’estat complet d’una màquina virtual** en un moment concret: disc, sistema operatiu i configuració.

Serveix per poder **tornar enrere** si alguna cosa falla.

És recomanable crear-ne **abans de fer canvis importants**, com:

* Instal·lar programari
* Actualitzar el sistema
* Fer proves de configuració

Si el sistema falla després, simplement es **restaura el snapshot** i la màquina torna exactament a l’estat anterior, com si res no hagués passat.

Un error habitual és confondre un snapshot amb una còpia de seguretat tradicional: **no és el mateix**, però per a pràctiques educatives és una eina molt potent.

---

## PART 3 - Reflexió tècnica i interpretació (3 punts)

---

### **6. Pregunta sobre configuració de VirtualBox (2 punts)**

**Observa la següent descripció de la configuració de VirtualBox:**
**L'alumne indica que no té accés a Internet dins la màquina virtual.**

**a) És normal que no tingui accés a Internet amb aquesta configuració?**
**b) Indica quin canvi faries a la configuració i per què.**

Sí, **és totalment normal**.

La configuració mostrada utilitza **xarxa interna**, que **no dona accés a Internet**. Aquesta opció només permet comunicació entre màquines virtuals del mateix grup.

El canvi correcte seria configurar l’adaptador de xarxa com a **NAT**, perquè:

* Proporciona accés a Internet immediat
* No requereix cap configuració extra
* És ideal per a pràctiques individuals

Un error molt habitual és pensar que qualsevol tipus de xarxa “dona Internet”. **No totes ho fan**, i aquesta pregunta precisament comprova si això s’ha entès.

---

### **7. Proves de rendiment (1 punt)**

**Explica per què és important fer proves de rendiment (benchmarks) abans d'afegir més màquines virtuals a un mateix ordinador amfitrió.**
**Posa un exemple de problema que es podria evitar.**

Les proves de rendiment són importants perquè **els recursos de l’ordinador són limitats**. Si afegim massa màquines virtuals sense comprovar el rendiment, el sistema pot tornar-se lent o inestable.

Un benchmark permet saber si:

* La CPU està saturada
* Falta memòria RAM
* El disc dur és un coll d’ampolla

Un exemple de problema que es podria evitar és que **totes les màquines virtuals vagin lentes** o que fins i tot **l’ordinador amfitrió es bloquegi**, afectant tota la classe.

Aquesta pregunta busca veure si enteneu que **virtualitzar no és il·limitat**, i que cal dimensionar bé els recursos.

