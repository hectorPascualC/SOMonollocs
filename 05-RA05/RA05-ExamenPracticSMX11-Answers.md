# RA05 – Examen Pràctic SMX11

## PART 1 - Comprensió pràctica (3 punts)

### **1. Màquina real i màquina virtual (1 punt)**

**A les pràctiques has treballat amb una màquina real (amfitriona) i diverses màquines virtuals.
Explica:
A. quin paper té la màquina real quan crees i executes una màquina virtual amb VirtualBox
B. posa un exemple pràctic de com la màquina real afecta el funcionament de la màquina virtual.**

La **màquina real o amfitriona** és l’ordinador físic sobre el qual treballem: és qui aporta **tots els recursos reals** (CPU, RAM, disc dur, targeta de xarxa).

Quan crees i executes una màquina virtual amb VirtualBox, la màquina real:

* allotja la màquina virtual,
* li cedeix una part dels seus recursos,
* i és imprescindible perquè la màquina virtual pugui funcionar.

La màquina virtual **no existeix de manera independent**, sempre depèn de l’amfitriona.

Un exemple pràctic molt clar és la **memòria RAM**:
si la màquina real té poca RAM disponible, la màquina virtual anirà lenta, encara que el sistema operatiu virtual estigui ben instal·lat. Això demostra que el rendiment de la màquina virtual està directament condicionat per l’estat i la potència de la màquina real.

Un error habitual és pensar que la màquina virtual “funciona sola”. No: **sense màquina real, no hi ha màquina virtual**.


### **2. Assignació de recursos (1 punt)**

**En crear una màquina virtual (Windows o Ubuntu) has assignat RAM i CPU.
A. Què pot passar a la màquina real si assignes massa RAM o CPU a una sola màquina virtual?
B. Per què és important repartir correctament aquests recursos?**

Si assignes **massa RAM o massa CPU** a una sola màquina virtual, la màquina real pot:

* tornar-se molt lenta,
* bloquejar-se,
* o fins i tot deixar de respondre.

Això passa perquè la màquina real necessita recursos **per funcionar ella mateixa**, a més de mantenir la màquina virtual.

És important repartir correctament els recursos perquè:

* la màquina real continuï sent usable,
* les màquines virtuals funcionin de manera estable,
* i s’evitin problemes de rendiment durant les pràctiques.

Aquest punt avalua si enteneu que **els recursos no són infinits** i que virtualitzar no vol dir “crear ordinadors gratis”, sinó **repartir el que hi ha**.


### **3. Connectivitat amb NAT (1 punt)**

**En una pràctica has configurat la xarxa NAT perquè la màquina virtual tingui accés a Internet.
Explica:
A. com obté connexió a Internet la màquina virtual amb NAT, i
B. per què no cal modificar la xarxa real del centre.**

Amb **NAT**, la màquina virtual obté connexió a Internet **a través de la màquina real**.
VirtualBox actua com un **router virtual**, que permet que la màquina virtual surti a Internet utilitzant la connexió de l’amfitrió.

No cal modificar la xarxa real del centre perquè:

* la màquina virtual no es connecta directament a la xarxa del centre,
* no rep cap IP del DHCP del centre,
* i no interfereix amb la infraestructura real.

Això fa que NAT sigui la configuració **més segura i més adequada en entorns educatius**.

Un error típic és confondre NAT amb adaptador pont: **no fan el mateix**, tot i que ambdós poden donar Internet.


## PART 2 - Supòsits pràctics (4 punts)


### **4. Prova de connectivitat amfitrió ↔ Ubuntu (2 punts)**

**Has creat dues màquines virtuals (Windows i Ubuntu). Des de la màquina real, vols comprovar que Ubuntu està ben connectada a la xarxa.
A. Quin tipus de xarxa has de tenir configurada a Ubuntu per fer aquesta prova tal com s’ha fet a classe?
B. Explica què comprova la prova de ping i què indica si la resposta és correcta.**

Per fer aquesta prova tal com s’ha fet a classe, Ubuntu ha de tenir configurada una **xarxa que permeti comunicació amb la màquina real**, com ara **adaptador pont** o **xarxa només amfitrió**, segons el cas treballat.

La prova de **ping** comprova:

* si hi ha connectivitat entre dos equips,
* i si els paquets arriben i tornen correctament.

Si la resposta és correcta, vol dir que:

* hi ha comunicació de xarxa,
* la configuració és funcional,
* i els equips es poden veure entre ells.

Aquesta pregunta no va d’Internet, sinó de **connectivitat i comunicació bàsica**.


### **5. Snapshots abans d’un canvi important (2 punts)**

**Abans d’instal·lar programari nou en una màquina virtual amb dades importants:
A. Explica què és un snapshot i per a què serveix.
B. Què pots fer si, després del canvi, el sistema no funciona correctament?**

Un **snapshot** és una **instantània de l’estat complet de la màquina virtual** en un moment concret.

Serveix per:

* guardar l’estat del sistema,
* i poder tornar enrere si alguna cosa falla.

Si després del canvi el sistema no funciona correctament, el que es pot fer és:

* **restaurar el snapshot**,
* i tornar exactament a l’estat anterior al canvi.

Aquesta eina és clau en entorns educatius perquè permet **aprendre sense por a espatllar res**.


## PART 3 - Reflexió tècnica i interpretació (3 punts)


### **6. Interpretació d’un pantallazo de VirtualBox (2 punts)**

**Observa la següent descripció de la configuració de VirtualBox:
L'alumne indica que no té accés a Internet dins la màquina virtual.
a) És normal que no tingui accés a Internet amb aquesta configuració? Per què?
b) Indica quin canvi faries a la configuració perquè la màquina virtual tingui accés a Internet i justifica’l.**

Sí, és **normal** que no tingui accés a Internet, perquè la configuració mostrada utilitza **xarxa interna**.

La xarxa interna:

* només permet comunicació entre màquines virtuals,
* **no dona accés a Internet**.

El canvi correcte és configurar l’adaptador com a **NAT**, perquè:

* proporciona Internet de manera immediata,
* no requereix configuracions addicionals,
* i és la millor opció per a pràctiques individuals.

Aquesta pregunta comprova si sabeu **interpretar una configuració real**, no memoritzar definicions.


### **7. Proves de rendiment amb Novabench (1 punt)**

**Després de fer una prova de rendiment amb Novabench en una màquina virtual Windows:
Explica per què és important fer aquestes proves abans d’afegir més màquines virtuals al mateix ordinador amfitrió i posa un exemple de problema que es podria evitar.**

És important fer proves de rendiment perquè l’ordinador amfitrió té **recursos limitats**.

Aquestes proves permeten saber:

* si la CPU està saturada,
* si falta memòria RAM,
* o si el disc és un coll d’ampolla.

Un exemple de problema que es podria evitar és:

* que totes les màquines virtuals vagin molt lentes,
* o que la màquina real es bloquegi durant una pràctica.

La idea clau és entendre que **virtualitzar requereix planificació**, no només crear màquines.


