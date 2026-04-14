# Examen 2 – Respostes comentades (Versió B)

## Part teòrica

### 1. Quina afirmació descriu millor una ruta absoluta?

**Correcta: c) És una ruta que indica el camí complet des del directori arrel**

**Per què és correcta:** perquè una ruta absoluta comença des de l’arrel i indica tot el camí.

- **a) És una ruta que només funciona a Windows** → Incorrecta.
- **b) És una ruta que depèn del directori actual** → Incorrecta, perquè això descriu una ruta relativa.
- **d) És una ruta que només serveix per fitxers temporals** → Incorrecta.

---

### 2. Quin és l’objectiu principal dels permisos sobre arxius i directoris?

**Correcta: b) Protegir dades i controlar accessos**

**Per què és correcta:** perquè els permisos serveixen per controlar qui pot llegir, escriure o executar.

- **a) Augmentar la mida del disc** → Incorrecta.
- **c) Reduir la RAM necessària** → Incorrecta.
- **d) Fer més ràpida la BIOS** → Incorrecta.

---

### 3. En l’assignació indexada de l’espai en disc, què guarda el bloc especial?

**Correcta: b) La llista d’adreces dels blocs del fitxer**

**Per què és correcta:** perquè en l’assignació indexada hi ha un bloc que desa les adreces dels blocs del fitxer.

- **a) El nom de l’usuari propietari** → Incorrecta.
- **c) El sistema operatiu complet** → Incorrecta.
- **d) Els errors del disc** → Incorrecta.

---

### 4. Què fa el swapping?

**Correcta: a) Mou processos o dades entre RAM i disc quan falta memòria**

**Per què és correcta:** perquè el swapping allibera RAM movent contingut al disc.

- **b) Divideix la memòria en segments variables** → Incorrecta.
- **c) Tradueix adreces virtuals a físiques** → Incorrecta.
- **d) Instal·la el sistema operatiu al disc** → Incorrecta.

---

### 5. Per a què serveix principalment el PCB?

**Correcta: b) Per guardar la informació necessària d’un procés**

**Per què és correcta:** perquè el PCB permet al sistema gestionar i reprendre processos.

- **a) Per formatar particions Linux** → Incorrecta.
- **c) Per crear usuaris a Windows** → Incorrecta.
- **d) Per iniciar GRUB** → Incorrecta.

---

### 6. En la comunicació d’entrada/sortida, què passa en el mode programat?

**Correcta: b) La CPU espera i consulta l’estat del dispositiu**

**Per què és correcta:** perquè en la comunicació programada la CPU va consultant si el dispositiu ja ha acabat.

- **a) El dispositiu treballa sense CPU** → Incorrecta.
- **c) El disc escriu directament a la RAM** → Incorrecta.
- **d) El gestor d’arrencada decideix el sistema operatiu** → Incorrecta.

---

### 7. Quina és una característica pròpia d’un sistema de 64 bits?

**Correcta: c) Pot gestionar quantitats grans de memòria**

**Per què és correcta:** perquè els 64 bits permeten gestionar molta més memòria que 32 bits.

- **a) No pot gestionar més de 4 GB de RAM** → Incorrecta, això és propi dels 32 bits.
- **b) És una arquitectura històrica i obsoleta** → Incorrecta.
- **d) Només es pot utilitzar amb FAT32** → Incorrecta.

---

### 8. Quina afirmació és correcta sobre el micronucli?

**Correcta: c) Manté només funcions bàsiques al nucli i la resta com a serveis separats**

**Per què és correcta:** aquesta és la definició de micronucli.

- **a) Tots els serveis s’executen dins del nucli** → Incorrecta, això descriu més aviat monolític.
- **b) Té millor rendiment que una arquitectura monolítica en tots els casos** → Incorrecta.
- **d) No necessita comunicació entre processos** → Incorrecta.

---

### 9. Quina relació és la correcta?

**Correcta: c) BIOS → MBR i UEFI → GPT habitualment**

**Per què és correcta:** és la relació habitual entre tipus d’arrencada i esquema de particions.

- **a) BIOS → GPT** → Incorrecta.
- **b) UEFI → MBR obligatòriament** → Incorrecta.
- **d) UEFI → FAT32 només** → Incorrecta.

---

### 10. Quin és el gestor d’arrencada habitual en Linux segons la teoria treballada?

**Correcta: c) GRUB**

**Per què és correcta:** perquè GRUB és el gestor d’arrencada habitual en Linux.

- **a) BCD** → Incorrecta, perquè és de Windows.
- **b) bootmgr** → Incorrecta, perquè és part de l’arrencada de Windows.
- **d) msconfig** → Incorrecta, perquè és una eina gràfica de Windows.

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
