---
marp: true
paginate: true
theme: default

header: "RA03 – Tasques bàsiques de configuració de sistemes operatius · Bloc 6 – Actualització del sistema i inventari"
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
# **RA03 – Bloc 6**
## **Actualització del sistema i inventari**

**SMX01 - Sistemes Operatius Monolloc**  
**Professor - Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **Què treballarem en aquest bloc**

Aquest bloc se centra en:

- Actualització del sistema a **Windows**  
- **Windows Update** i les seves opcions  
- Inventari del programari a **Ubuntu**  
- Comprovació de **controladors i maquinari** a Ubuntu  

Objectiu: entendre com mantenir el sistema al dia i com comprovar què hi ha instal·lat o detectat a l'equip  

---

<!-- SLIDE 3 -->
# 🔸 **Per què és important actualitzar Windows**

Actualitzar Windows és important perquè:

- millora la **seguretat** i protegeix contra amenaces  
- corregeix **errors** i millora el rendiment del sistema  
- afegeix **noves funcionalitats**  
- millora la **compatibilitat amb maquinari**  

---

<!-- SLIDE 4 -->
# 🔸 **Tipus d'actualitzacions a Windows**

- **Crítiques**  
  → s'instal·len automàticament per garantir la seguretat  

- **Recomanades**  
  → milloren el rendiment i afegeixen funcionalitats  

- **Opcionals i de maquinari**  
  → poden incloure controladors nous i programari de prova  

---

<!-- SLIDE 5 -->
# 🔸 **Opcions de configuració a Windows Update**

Diferenciem tres maneres de configurar les actualitzacions:

1. **Automàtiques**  
   → Windows descarrega i instal·la les actualitzacions sense intervenció

2. **Personalitzades**  
   → l'usuari pot escollir quines actualitzacions instal·lar

3. **Desactivades**  
   → es bloqueja la recepció d'actualitzacions (**no recomanat**)

---

<!-- SLIDE 6 -->
# 🔸 **Què és Windows Update**

**Windows Update** és el sistema integrat que:

- verifica les actualitzacions del sistema operatiu  
- comprova la versió actual  
- descarrega les millores disponibles  
- instal·la actualitzacions de seguretat, compatibilitat i maquinari  

---

<!-- SLIDE 7 -->
# 🔸 **Opcions útils de Windows Update a Windows 10**

A Windows 10, des d'aquesta eina es pot:

- descarregar actualitzacions des de **Microsoft** o altres equips  
- triar quines actualitzacions instal·lar  
- desinstal·lar actualitzacions si hi ha problemes  

Ruta que surt al PowerPoint:

`Veure historial d'actualitzacions → Desinstal·lar actualitzacions`

Nota:

- només a **Windows 10 Pro i Enterprise** es poden definir polítiques d'actualització amb directives del sistema

---

<!-- SLIDE 8 -->
# 🔸 **Apartat Ubuntu dins d'aquest bloc**

A Ubuntu trobem 2 idees:

- **inventari del programari**  
- **comprovació de controladors i maquinari**  

Això vol dir:

- saber quins programes hi ha instal·lats  
- saber quins dispositius detecta el sistema  
- poder diagnosticar problemes de compatibilitat  

---

<!-- SLIDE 9 -->
# 🔸 **Inventari del programari a Ubuntu**

L'**inventari del programari** és:

- la llista de tots els programes instal·lats al sistema  
- una manera de detectar instal·lacions no autoritzades  
- una ajuda per localitzar aplicacions que ja no s'utilitzen  

Per consultar-lo des de la interfície gràfica:

`Ubuntu Software → Instal·lats`

---

<!-- SLIDE 10 -->
# 🔸 **Ordres per consultar programes instal·lats a Ubuntu**

Des del terminal:

```bash
dpkg -l
apt list --installed
snap list
```

Interpretació bàsica:

- `dpkg -l` → paquets `.deb`  
- `apt list --installed` → paquets gestionats per `apt`  
- `snap list` → paquets `snap`  

- **dpkg**: eina per instal.lar paquets deb   
- **deb**: fitxers d’instal·lació de programes que fan servir Debian, Ubuntu i altres distribucions derivades  
- **apt**: és una eina més còmoda i més moderna que dpkg   
- **snap**: altre sistema de d'instal.lació de paquets   

---

<!-- SLIDE 11 -->
# 🔸 **Comprovar controladors i maquinari a Ubuntu**

Per què és útil?

- permet veure quins dispositius detecta el sistema  
- permet veure quins controladors hi ha associats  
- ajuda a diagnosticar problemes de compatibilitat amb el maquinari  

---

<!-- SLIDE 12 -->
# 🔸 **Ordres per llistar maquinari i controladors**

```bash
lshw
fdisk -l
lsusb
lspci
dmesg
```

- `lshw` → llista el maquinari detectat  
- `fdisk -l` → mostra dispositius d'emmagatzematge  
- `lsusb` → mostra dispositius USB connectats  
- `lspci` → mostra dispositius PCI  
- `dmesg` → mostra controladors detectats pel nucli  

---

<!-- SLIDE 13 -->
# 🔸 **Resum del bloc 6**

- Actualitzar Windows millora seguretat, rendiment i compatibilitat  
- Windows Update permet automatitzar, personalitzar o revisar actualitzacions  
- A Ubuntu, l'inventari del programari ajuda a saber què hi ha instal·lat  
- Les ordres de maquinari i controladors ajuden a diagnosticar l'estat del sistema  

---

<!-- SLIDE 14 -->
# **Fi del Bloc 6**
