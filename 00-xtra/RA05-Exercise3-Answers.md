# ✅ **RA05 – Solució Exercise 3 (Resolució tècnica)**

## **1) Quina és la puntuació de CPU i la velocitat de RAM obtinguda? És adequada per a ús bàsic? Per què?**

En entorns virtualitzats, la puntuació de **CPU** i la **velocitat de RAM** que dona Novabench reflecteixen la capacitat del *vCPU assignat* i del *subsystem de memòria virtualitzada*.

En general, per a un ús bàsic (navegació, ofimàtica, eines simples), són adequades si:

* **CPU Score > 300** (en VirtualBox és habitual entre 250 i 350 amb 2 vCPU)
* **RAM Speed > 3.000 MB/s**
  Aquesta velocitat és típicament inferior a la màquina física, però suficient.

**Justificació tècnica:**
Windows, fins i tot en entorns virtualitzats, només necessita entre 1–2 vCPU i 2–4 GB de RAM per a tasques bàsiques. La limitació ve per processos intensius (compressió, vídeo, compilació), no per tasques estàndard.

---

## **2) Com varia l’ús de CPU i RAM durant el test? Relació entre Novabench i el Gestor de Tasques**

### CPU

Durant el benchmark, el consum acostuma a arribar a **90–100% del vCPU**, ja que Novabench executa operacions aritmètic-lògiques intensives.

### RAM

L’ús de RAM augmenta lleugerament (10–20%) perquè Novabench prova la velocitat de lectura/escriptura en blocs.

### Relació tècnica

* **Novabench** calcula puntuacions sintètiques basades en operacions matemàtiques, memòries i I/O.
* **Task Manager** mostra l’ús *en temps real* del scheduler del SO i del hypervisor.

És normal que el Task Manager mostri saturació encara que la puntuació de Novabench no sigui alta, perquè el vCPU es comparteix amb l’amfitrió.

---

## **3) Si assignem menys recursos (ex.: 1 GB de RAM), com canvien els resultats?**

### Efectes tècnics:

* **Disminució de la velocitat de RAM** → menys memòria disponible implica més *pagefile* i més latència.
* **Augment de la latència del disc** → Windows fa swapping constant.
* **Pitjor CPU Score** → el processador ha d’esperar més per accedir a dades (bottleneck de memòria).
* **Rendiment global inferior** (especialment en IO i RAM benchmark).

### Per què?

Perquè la RAM és un recurs fonamental: reduir-la provoca *thrashing* i saturació del bus d’E/S.

---

## **4) Si executéssim dues màquines virtuals iguals, què passaria? Com afecta l’amfitrió?**

Executar dues VM amb la mateixa configuració significa duplicar la demanda sobre:

* **vCPU** → el hypervisor ha de “time-slicear” els nuclis, provocant latència.
* **RAM** → pot provocar *ballooning* o swapping a l’amfitrió.
* **Disk I/O** → competència pel mateix fitxer .VDI o .VMDK.

### Impacte en l’amfitrió:

* Ralentització general del sistema.
* Increment del temps de resposta.
* Possibles “pauses” o micro-lags per pressió d’E/S.

En entorns professionals, això es controla amb *overcommit ratios* (70–80% màxim recomanat).

---

## **5) Per què és important fer proves de rendiment abans d’afegir més màquines virtuals a un servidor?**

Perquè permet:

* **Detectar saturacions** de CPU, RAM o disc.
* **Avaluar si l’overcommit** és possible sense penalitzar el rendiment.
* **Dimensionar recursos** de manera adequada (capacity planning).
* **Garantir QoS** (Quality of Service).
* **Evitar col·lapses** del servidor en hora punta.

En enginyeria de sistemes això forma part del **Performance Baseline**.

---

## **6) Si la velocitat de lectura/escriptura del disc és baixa, què podem fer per millorar-la?**

Accions tècniques habituals:

### A nivell de VM:

* Canviar el control·lador del disc a **VirtIO**, **AHCI** o **SCSI** (millora latències).
* Activar **cache d’escriptura** al VirtualBox/VMware.

### A nivell d’amfitrió:

* Moure les VM a un **SSD NVMe**.
* Separar discos d’amfitrió i discos de VM.
* Incrementar la **RAM** (evita swapping).
* Defragmentar (si és un HDD).

### A nivell d’infraestructura:

* Utilitzar **RAID 10** (millor IOPS).
* Utilitzar **storage dedicat** (NAS/SAN).

---

## **7) Per què una màquina virtual té un rendiment inferior a una màquina física equivalent?**

Raons essencials:

### ➤ **Intermediació del hypervisor**

Cada instrucció passa pel hypervisor → augmenta la latència.

### ➤ **Virtualització del hardware**

Les operacions de CPU, memòria i E/S no s’executen directament sobre el hardware.

### ➤ **Compartició de recursos**

Les VM comparteixen CPU, RAM i disc amb altres processos de l’amfitrió.

### ➤ **Drivers virtualitzats**

Els drivers virtuals (virtIO, VBoxGuest) són més eficients però no arriben mai al 100% del rendiment natiu.

### ➤ **Overhead en I/O**

Els accessos a disc del .VDI són molt més lents que un disc físic.

---

## **8) Són útils eines com Novabench en entorns professionals? Exemple pràctic**

Sí. Aquest tipus d’eines s’utilitzen en:

### ✔ **QA i homologació de hardware**

Abans de desplegar 200 equips nous, es fa un test baseline.

### ✔ **Benchmarking d’infraestructures virtuals**

Per comparar rendiment entre VMware, Proxmox, Hyper-V o VirtualBox.

### ✔ **Capacity Planning en CPDs**

Decidir quantes VM suporta un servidor sense degradació.

### ✔ **Detecció d’anomalies**

Si un disc NVMe passa de 2500 MB/s a 300 MB/s, indica problema imminent.

Exemple real:

> En una empresa, abans de migrar els servidors de Windows Server a VMware, es va utilitzar Novabench i PassMark per comparar diferents cabines SAN i determinar quina tenia millor IOPS sota càrrega.


