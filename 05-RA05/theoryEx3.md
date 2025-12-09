# **Conceptes tècnics de VirtualBox**

# **1. SATA i la interfície PATA (IDE)**

## **1.1. Què és SATA?**

SATA (Serial ATA) és un bus d’entrada/sortida (I/O bus) dissenyat específicament per a la comunicació entre el controlador d'emmagatzematge de la placa base i els dispositius de bloc, com discos HDD, SSDs i unitats òptiques

Un bus d’entrada/sortida (I/O bus) és el camí físic i l’estàndard de comunicació que permet que els dispositius (discs, targetes de xarxa, USB, gràfiques…) es comuniquin amb la CPU i la memòria. És un conjunt de pistes de coure a la placa base

Va substituir l’antiga interfície PATA (IDE) i aporta:
* Major velocitat de transferència (fins a 6 Gb/s en SATA III)
* Cable més fi i flexible
* Connexions punt-a-punt (no compartides)
* Hot-plug (es poden connectar/disconnectar en calent, si el sistema ho suporta)

VirtualBox també simula un controlador SATA virtual que emmagatzema i gestiona els discos virtuals

## **1.2. L’antiga interfície PATA (IDE)**

PATA (Parallel ATA), també anomenada IDE, era l'estàndard antic per connectar discos durs i unitats òptiques als ordinadors abans que SATA existís

Característiques principals:

* Transmissió paral·lela (16 bits alhora)
* Connectors amples, de 40 o 80 fils
* Un sol cable podia transportar fins a 2 dispositius
* Velocitats baixes comparades amb SATA (ATA/33, ATA/66, ATA/100…)

Per què va desaparèixer?

* Era lent
* Era sensible a interferències
* Compartir canal amb dos dispositius generava conflictes (MA/SL: Master/Slave)

SATA el substitueix perquè:

* És més ràpid
* Fa servir transmissió serial (1 bit cada cop), però a molta més freqüència
* Cada dispositiu té el seu propi cable independent

## **1.3. Connexions punt-a-punt (no compartides)**

Quan diem *connexions punt-a-punt*:
**Cada dispositiu SATA té la seva pròpia connexió dedicada amb el controlador.**

Ex:

**PATA (compartit)**
```
[Placa base] --- CABLE PATA --- [Dispositiu 1]
                                [Dispositiu 2]
```

**SATA (punt-a-punt)**
```
[Placa base] --- Cable SATA 1 --- [Dispositiu 1]

[Placa base] --- Cable SATA 2 --- [Dispositiu 2]
```

Avantatges:
* Cada disc pot treballar al màxim rendiment
* No hi ha competició per l’ample de banda
* Es redueix la latència
* Arquitectura més senzilla

# **2. Formats de disc a VirtualBox**

## **2.1. Què és un VDI?**

El VDI és el format de disc virtual nadiu de VirtualBox, és el disc dur
Un fitxer VDI conté tot el contingut del disc dur virtual d’una màquina virtual: sistema operatiu, fitxers, particions…

Característiques tècniques:
* Permet redimensionament
* Pot ser dinàmicament assignat (només ocupa l’espai real utilitzat)
* Compatible amb snapshots

## **2.2. Permet redimensionament**

Un fitxer VDI es pot fer més gran si tu ho demanes

Ex:
* Crees un VDI de 10 GB
* Et quedes curt
* Pots ampliar-lo a 20 GB sense crear un disc nou

Important:
Ampliar el fitxer no amplia la partició del sistema operatiu, que s’ha d’estendre després manualment

## **2.3. Dinàmicament assignat**

Quan crees un disc VDI pots triar:

### a) Fixat

Si dius “20 GB”, el fitxer físic **ocupa 20 GB des del primer moment**.

### b) Dinàmicament assignat

El fitxer **creix només quan el sistema virtual utilitza espai**.
Si dins la VM s’utilitzen 5 GB → el fitxer físic ocupa uns 5 GB.

# **3. Conceptes de xarxa a VirtualBox**

## **3.1. Adreça MAC**

* L’adreça MAC (Media Access Control) és un identificador únic assignat a cada interfície de xarxa.
* VirtualBox genera MACs aleatòries. No són úniques al món, però sí úniques per a la teva VM.
* Es pot modificar
* On es troba a VirtualBox?
```
Configurar màquina → Xarxa → Adaptador 1 → Avançat → Adreça MAC
```

## **3.2. NAT**

NAT no només existeix a VirtualBox

El NAT és una tecnologia general de xarxa utilitzada en routers domèstics, tallafocs, proxys, Docker, VMware, Hyper-V…

VirtualBox la utilitza per:
- Tenir Internet
- Sense exposar la màquina virtual a la xarxa real

## **3.3. Xarxa interna**

És una xarxa completament aïllada.
Només es comuniquen entre elles les màquines virtuals connectades a aquesta xarxa.
Ni Internet, ni el PC amfitrió, ni el router hi tenen accés.

## **3.4. Adaptador pont**

**“L’adaptador pont connecta la màquina virtual directament a la teva xarxa física”**:

1. La VM rep **una IP del router real**
2. La VM apareix com **un dispositiu més** de la xarxa local
3. Pot comunicar-se amb ordinadors reals i altres VMs
4. És visible a la xarxa com qualsevol altre PC

Ex de LAN real amb adaptador pont:

```
PC amfitrió:   192.168.1.20
VM Windows:    192.168.1.34
VM Ubuntu:     192.168.1.35
Mòbil:         192.168.1.41
SmartTV:       192.168.1.12
```

# **4. Controladors USB**

VirtualBox pot virtualitzar USBs amb tres modes:

## **4.1. USB 1.1 (OHCI)**

* Velocitat màxima: 12 Mbps
* Per dispositius antics
* Molt compatible

## **4.2. USB 2.0 (EHCI)**

* Velocitat: 480 Mbps
* Per la majoria de memòries USB
* Requereix Extensions Pack

## **4.3. USB 3.0 (xHCI)**

* Velocitat: 5 Gbps
* Per dispositius moderns
* Requereix Extensions Pack
* Depèn més de la compatibilitat amb el sistema amfitrió

---

# **5. Resum final**

| Concepte              | Explicació breu                                             |
| --------------------- | ----------------------------------------------------------- |
| PATA (IDE)            | Antic estàndard, cable ample, dos dispositius per cable     |
| SATA                  | Nova interfície, connexions punt-a-punt, ràpid              |
| VDI                   | Disc virtual nadiu de VirtualBox                            |
| Dinàmicament assignat | El disc creix segons ús                                     |
| MAC                   | Identificador de xarxa; editable; visible a Xarxa → Avançat |
| NAT                   | Fa de router virtual (Internet però aïllat)                 |
| Adaptador pont        | La VM rep IP real i entra a la xarxa física                 |
| Xarxa interna         | Xarxa privada entre VMs                                     |
| USB 1/2/3             | Controladors USB virtuals segons tipus                      |


