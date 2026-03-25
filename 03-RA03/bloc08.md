---
marp: true
paginate: true
theme: default

header: "RA03 – Tasques bàsiques de configuració de sistemes operatius · Bloc 8 – Assistents de configuració i xarxa"
footer: "Mòdul 0222 – SO Monolloc"

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
# **RA03 – Bloc 8**
## **Assistents de configuració i xarxa**

**SMX01 - Sistemes Operatius Monolloc**  
**Professor - Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **Què treballarem en aquest bloc**

Aquest bloc se centra en:

- Assistents de configuració del sistema a **Windows**  
- Configuració de **dispositius** i **xarxes** a Windows  
- **Firewall**, **VPN** i **proxy**  
- Detecció de **maquinari** i **controladors** a GNU/Linux  
- Instal·lació de **controladors addicionals** i ordres útils

Objectiu: entendre quines eines ofereix el sistema per configurar l'equip i com comprovar dispositius, xarxa i controladors  

---

<!-- SLIDE 3 -->
# 🔸 **Assistents de configuració del sistema a Windows**

Windows inclou diversos assistents que faciliten la configuració del sistema operatiu sense necessitat de coneixements avançats.

Ajuden en tasques com:

- connexió a **xarxes**  
- configuració de **dispositius**  
- gestió general del **sistema**

---

<!-- SLIDE 4 -->
# 🔸 **Exemples d'assistents a Windows**

Assistents habituals:

- **assistent de configuració inicial**  
  → guia l'usuari en la primera configuració del sistema

- **assistent de xarxes**  
  → configura connexions **Wi‑Fi, Ethernet i VPN**

- **assistent d'impressió**  
  → instal·la i configura impressores

---

<!-- SLIDE 5 -->
# 🔸 **Altres assistents de Windows**

- **assistent de solució de problemes**  
  → ajuda a diagnosticar i resoldre errors de xarxa, so i altres components

- **assistent d'actualitzacions**  
  → gestiona la instal·lació de noves versions de Windows i de controladors

Objectiu general:

- simplificar la configuració del sistema  
- millorar l'experiència de l'usuari

---

<!-- SLIDE 6 -->
# 🔸 **Configuració de dispositius a Windows**

La idea general és que Windows permet:

- detectar dispositius connectats  
- configurar-los des del sistema  
- adaptar-ne el funcionament segons les necessitats de l'usuari

---

<!-- SLIDE 7 -->
# 🔸 **Configuració de xarxes a Windows**

Windows permet gestionar i configurar la connexió a Internet i les xarxes locals des del menú de configuració

Això inclou:

- veure l'**estat de la xarxa**  
- accedir a opcions avançades  
- configurar el perfil de connexió

---

<!-- SLIDE 8 -->
# 🔸 **Estat de la xarxa a Windows**

Des d'aquest apartat es pot:

- veure si la connexió és **Wi‑Fi** o **Ethernet**  
- convertir la connexió en **mèdida** per controlar l'ús de dades  
- accedir a opcions avançades d'**adaptadors** i **recursos compartits**

---

<!-- SLIDE 9 -->
# 🔸 **Perfils de xarxa a Windows**

Dos perfils principals:

- **Públic**  
  → l'equip es manté ocult i no permet compartir arxius ni impressores

- **Privat**  
  → recomanat per a xarxes de confiança, com casa o feina, i permet compartir recursos

---

<!-- SLIDE 10 -->
# 🔸 **Opcions avançades de xarxa**

A Windows també es pot accedir a opcions com:

- configuració del **tallafoc**  
- diagnòstic de problemes de **xarxa**  
- restabliment de la **connexió**

---

<!-- SLIDE 11 -->
# 🔸 **Firewall i protecció de xarxa a Windows**

El **Firewall de Windows** és una eina de seguretat que controla les connexions d'entrada i sortida de la xarxa  

La seva funció és protegir el sistema davant possibles amenaces   

---

<!-- SLIDE 12 -->
# 🔸 **Tipus de xarxes al Firewall de Windows**

- **Xarxa de domini**  
  → pensada per a entorns corporatius amb polítiques de seguretat gestionades

- **Xarxa privada**  
  → pensada per a entorns de confiança, com casa o feina

- **Xarxa pública**  
  → aplica més restriccions i bloqueja connexions externes no autoritzades

---

<!-- SLIDE 13 -->
# 🔸 **Opcions del Firewall**

Entre les opcions avançades:

- permetre o bloquejar **aplicacions**  
- solucionar problemes de **xarxa i Internet**  
- configurar **notificacions** i **regles personalitzades**  
- restaurar el firewall als **valors predeterminats**  

Idea clau: mantenir el firewall activat millora la seguretat del sistema.

---

<!-- SLIDE 14 -->
# 🔸 **Configuració de VPN a Windows**

Una **VPN** permet establir una connexió segura i encriptada a una xarxa privada a través d'Internet  

Des de Windows es pot:

- afegir una **connexió VPN**  
- permetre VPN en **xarxes d'ús mèdit**  
- permetre VPN en **itinerància**

---

<!-- SLIDE 15 -->
# 🔸 **Opcions avançades de la VPN**

També es poden configurar aspectes com:

- opcions de l'**adaptador de xarxa**  
- opcions d'**ús compartit**  
- comportament del **Firewall de Windows** per permetre o bloquejar connexions VPN

Beneficis:

- més **seguretat**  
- accés remot a xarxes corporatives  
- més **privacitat** en la navegació

---

<!-- SLIDE 16 -->
# 🔸 **Configuració de proxy a Windows**

Un **servidor proxy** actua com a intermediari entre l'ordinador i Internet  

Millora:

- la **seguretat**  
- la **privacitat**  
- la gestió del **trànsit de xarxa**

---

<!-- SLIDE 17 -->
# 🔸 **Tipus de configuració del proxy**

- **Configuració automàtica**  
  → detecta automàticament la configuració del proxy  
  → pot fer servir un script de configuració (**PAC**)

- **Configuració manual**  
  → permet introduir manualment l'adreça i el port del servidor proxy  
  → permet excloure adreces específiques

---

<!-- SLIDE 18 -->
# 🔸 **Avantatges del proxy**

Avantatges destacats:

- control del trànsit de xarxa en entorns corporatius  
- millora de la seguretat evitant connexions directes a Internet  
- possibilitat d'accedir a continguts restringits geogràficament

---

<!-- SLIDE 19 -->
# 🔸 **Assistents de configuració del sistema Linux**

En la part de GNU/Linux, el bloc se centra sobretot en:

- detecció de **maquinari**  
- funcionament dels **mòduls del nucli**  
- ús de **controladors**  
- instal·lació de controladors addicionals

---

<!-- SLIDE 20 -->
# 🔸 **Detecció de maquinari a GNU/Linux**

Segons el PowerPoint:

- el **nucli** detecta el maquinari en iniciar-se  
- també pot reconèixer dispositius nous connectats després, sense reiniciar

Això fa que el sistema pugui adaptar-se a molts canvis de maquinari de manera dinàmica.

---

<!-- SLIDE 21 -->
# 🔸 **Nucli modular i controladors**

El PowerPoint explica que:

- el nucli utilitza **mòduls** que es poden carregar o descarregar segons el maquinari detectat  
- si s'afegeix maquinari nou, es pot carregar el mòdul adequat en aquell moment

Aquests mòduls del nucli també s'anomenen **controladors**.

---

<!-- SLIDE 22 -->
# 🔸 **Origen dels controladors a Linux**

Els controladors poden ser desenvolupats per:

- el projecte **Linux**  
- els **fabricants** del maquinari

Per això, en alguns casos hi ha controladors lliures i controladors específics del fabricant   

---

<!-- SLIDE 23 -->
# 🔸 **Controladors addicionals a Ubuntu**

Per instal·lar controladors addicionals a Ubuntu 20.04:

`Programari i actualitzacions → Controladors addicionals`

Des d'aquí es poden instal·lar drivers propietaris o específics que no venen inclosos per defecte   

---

<!-- SLIDE 24 -->
# 🔸 **Ordres útils per comprovar maquinari i dispositius**

Ordres de terminal:

```bash
lshw
fdisk -l
lsusb
lspci
dmesg
```

---

<!-- SLIDE 25 -->
# 🔸 **Per a què serveixen aquestes ordres**

- `lshw` → llista tot el **maquinari detectat**  
- `fdisk -l` → mostra els **dispositius d'emmagatzematge**  
- `lsusb` → mostra els **dispositius USB**  
- `lspci` → mostra els **busos i dispositius PCI**  
- `dmesg` → mostra **controladors reconeguts pel nucli**

---

<!-- SLIDE 26 -->
# 🔸 **Resum del bloc 8**

- Windows disposa d'assistents que faciliten la configuració del sistema  
- La configuració de xarxa inclou perfils, firewall, VPN i proxy  
- A GNU/Linux, el nucli detecta el maquinari i carrega mòduls segons calgui  
- Ubuntu permet instal·lar controladors addicionals i comprovar el maquinari des del terminal

---

<!-- SLIDE 27 -->
# **Fi del Bloc 8**
