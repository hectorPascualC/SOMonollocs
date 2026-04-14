# Examen 1 – Respostes comentades

## Part teòrica

### 1. Quin és el paper principal del sistema operatiu?

**Correcta: b) Gestionar els recursos del sistema i permetre executar aplicacions**

**Per què és correcta:** perquè el sistema operatiu és el programari que gestiona el maquinari i permet que altres aplicacions funcionin.

- **a) Fabricar components del maquinari** → Incorrecta, perquè el sistema operatiu no fabrica maquinari.
- **c) Substituir la BIOS** → Incorrecta, perquè la BIOS o UEFI arrenca abans del sistema operatiu.
- **d) Crear particions automàticament** → Incorrecta, perquè això pot ser una funció puntual d’eines del sistema, però no és el seu paper principal.

---

### 2. Quina de les següents és una funció bàsica del sistema operatiu?

**Correcta: b) Gestionar memòria, processos i dispositius**

**Per què és correcta:** perquè aquestes són funcions bàsiques del sistema operatiu.

- **a) Soldar components de la placa base** → Incorrecta, perquè és una tasca física de maquinari.
- **c) Augmentar físicament la RAM** → Incorrecta, perquè el SO no augmenta físicament la RAM.
- **d) Crear usuaris a Internet** → Incorrecta, perquè no és una funció bàsica del SO.

---

### 3. Quin element tradueix adreces virtuals a adreces físiques?

**Correcta: c) MMU**

**Per què és correcta:** perquè la MMU és la unitat de gestió de memòria que tradueix adreces virtuals a físiques.

- **a) PCB** → Incorrecta, perquè el PCB guarda informació del procés.
- **b) DMA** → Incorrecta, perquè DMA serveix per transferir dades directament a la RAM.
- **d) GPT** → Incorrecta, perquè GPT és un esquema de particions.

---

### 4. Què és un page fault?

**Correcta: b) Que la dada o instrucció que necessita el programa no és a la RAM**

**Per què és correcta:** perquè un page fault passa quan la pàgina no és a la memòria principal i el sistema l’ha de carregar.

- **a) Un error de teclat** → Incorrecta.
- **c) Una fallada del disc dur** → Incorrecta, perquè no és directament una fallada del disc.
- **d) Un error del gestor d’arrencada** → Incorrecta.

---

### 5. Què és el PCB?

**Correcta: b) Una estructura que guarda la informació d’un procés**

**Per què és correcta:** perquè el PCB conté el PID, estat, registres, memòria i fitxers oberts del procés.

- **a) Una partició de Linux** → Incorrecta.
- **c) El gestor d’arrencada de Windows** → Incorrecta.
- **d) Una tècnica de clonació** → Incorrecta.

---

### 6. Quin mètode de comunicació d’E/S és més eficient perquè allibera la CPU?

**Correcta: c) DMA**

**Per què és correcta:** perquè el DMA permet transferir dades directament a memòria i la CPU només inicia i és avisada quan acaba.

- **a) Comunicació programada** → Incorrecta, perquè la CPU espera.
- **b) Interrupcions** → Incorrecta, perquè milloren l’eficiència, però DMA encara allibera més la CPU en la transferència de dades.
- **d) Segmentació** → Incorrecta, perquè és una tècnica de memòria, no d’E/S.

---

### 7. Quin és un avantatge principal de l’arquitectura monolítica?

**Correcta: b) Alt rendiment**

**Per què és correcta:** perquè a la monolítica tot o gairebé tot funciona dins del nucli i això dona molt rendiment.

- **a) Més modularitat** → Incorrecta, perquè és més pròpia del micronucli.
- **c) Més seguretat que el micronucli** → Incorrecta.
- **d) No utilitza drivers** → Incorrecta, perquè sí que utilitza drivers.

---

### 8. Quina afirmació sobre MBR és correcta?

**Correcta: c) Té limitacions de mida i nombre de particions**

**Per què és correcta:** perquè MBR és antic, permet fins a 4 particions primàries i té limitacions de mida.

- **a) Permet un nombre il·limitat de particions** → Incorrecta.
- **b) És més modern que GPT** → Incorrecta.
- **d) Només funciona amb Linux** → Incorrecta.

---

### 9. Quin sistema d’arxius és habitual a Linux per a la partició principal?

**Correcta: c) ext4**

**Per què és correcta:** perquè ext4 és l’estàndard actual més habitual per a la partició principal Linux.

- **a) NTFS** → Incorrecta, perquè és habitual a Windows.
- **b) FAT32** → Incorrecta, perquè no és l’habitual per a la partició principal Linux.
- **d) APFS** → Incorrecta, perquè és propi d’Apple.

---

### 10. Quina afirmació és correcta sobre dual boot?

**Correcta: b) Permet tenir dos sistemes operatius instal·lats, però només se’n pot usar un cada vegada**

**Per què és correcta:** perquè en un dual boot hi ha diversos sistemes instal·lats, però només se’n pot arrencar un cada vegada.

- **a) Permet executar dos sistemes operatius alhora sobre el mateix maquinari sense virtualització** → Incorrecta.
- **c) No necessita gestor d’arrencada** → Incorrecta.
- **d) Obliga a utilitzar MBR** → Incorrecta.

---

## Part pràctica – Resposta model

### 1. Verificació i planificació prèvia

Abans d’instal·lar Windows 10 i Ubuntu en un mateix equip, comprovaria el **processador**, perquè ha de ser compatible amb l’arquitectura del sistema operatiu, per exemple 32 o 64 bits. També revisaria la **RAM**, perquè condiciona el rendiment i el nombre de programes que es poden utilitzar alhora. Després comprovaria l’**espai de disc**, perquè cal tenir prou espai per als dos sistemes operatius i per a les particions necessàries. Finalment, revisaria **altres requisits o perifèrics**, com la targeta gràfica, connexió a Internet i dispositius específics si s’han d’utilitzar.

Planificar és important perquè assegura compatibilitat, evita errors durant la instal·lació i permet decidir correctament particions, sistemes d’arxius i distribució de l’espai.

### 2. Particions i sistemes d’arxius

Per a un dual boot bàsic, **Windows** faria servir una partició principal amb **NTFS**. **Ubuntu** faria servir una partició principal amb **ext4** i una partició **swap** per a memòria virtual. També es podria afegir una partició **/home** separada amb ext4 per a dades d’usuari.

### 3. Procés general d’instal·lació del dual boot

L’ordre correcte és:

1. Instal·lar **Windows**
2. **Redimensionar la partició** o reservar espai lliure
3. Instal·lar **Ubuntu** a l’espai lliure

Durant la instal·lació d’Ubuntu es defineixen mida de partició, sistema d’arxius i punt de muntatge. Quan es reinicia l’equip, apareix el gestor d’arrencada i es pot seleccionar quin sistema operatiu iniciar.

### 4. Gestor d’arrencada

Un **gestor d’arrencada** és el programa que s’executa quan s’encén l’ordinador i permet seleccionar quin sistema operatiu es vol iniciar. A Linux s’utilitza habitualment **GRUB**.

A **Windows**, per revisar o modificar l’arrencada es poden utilitzar:

- `bcdedit`
- `msconfig`

A **Ubuntu**, es pot editar:

- `/etc/default/grub`

i aplicar els canvis amb:

```bash
sudo update-grub
```
