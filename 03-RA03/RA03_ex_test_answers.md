# RA03 — Respostes de la part teòrica

## Pregunta 1
**En la configuració de xarxa de Windows, quin perfil és el més restrictiu i està pensat per a entorns no confiables?**

### Resposta correcta
**b. Perfil públic**

### Per què és correcta
Al `bloc08.md`, dins de **Perfils de xarxa a Windows**, es diu:
- **Públic** → “l'equip es manté ocult i no permet compartir arxius ni impressores”
- “Pensat per a xarxes no confiables”
- “La detecció de xarxa i l’ús compartit d’arxius i impressores solen estar desactivats o restringits”

També, a **Tipus de xarxes al Firewall de Windows**, es diu:
- **Xarxa pública** → “aplica més restriccions i bloqueja connexions externes no autoritzades”

### Per què les altres no
- **a. Perfil de domini** → incorrecta perquè al material surt com a pensat per a entorns corporatius amb polítiques de seguretat gestionades.
- **c. Perfil privat** → incorrecta perquè és per a xarxes de confiança, com casa o feina.
- **d. Perfil VPN** → incorrecta perquè la VPN al material és una connexió segura, no un perfil de xarxa dins d’aquesta classificació.

### On surt exactament
- `bloc08.md` → **Perfils de xarxa a Windows**
- `bloc08.md` → **Tipus de xarxes al Firewall de Windows**

---

## Pregunta 2
**Quina afirmació és correcta sobre `man` i `sudo` a Linux?**

### Resposta correcta
**c. `man` serveix per consultar l’ajuda d’una ordre i `sudo` permet executar-la amb privilegis elevats si l’usuari està autoritzat**

### Per què és correcta
Al `bloc02.md` es diu:
- `man` serveix per:
  - “Consultar l’ajuda d’una ordre”
  - “Veure opcions disponibles”
  - “Entendre millor la sintaxi”
- `sudo`:
  - “Vol dir superuser do”
  - “Només funciona per a usuaris autoritzats”
  - “Per executar una ordre com a administrador”

### Per què les altres no
- **a. `man` i `sudo` són dues ordres exclusives d’Ubuntu Server** → incorrecta; el material no diu això.
- **b. `sudo` només es pot utilitzar amb ordres de xarxa** → incorrecta; al material s’exemplifica amb `sudo ls -l /root`.
- **d. `man` permet executar ordres com a administrador i `sudo` mostra el manual** → incorrecta perquè intercanvia les funcions.

### On surt exactament
- `bloc02.md` → **Ajuda amb `man`**
- `bloc02.md` → **Permisos i ús de `sudo`**

---

## Pregunta 3
**Quin enunciat descriu millor un punt de restauració de Windows?**

### Resposta correcta
**a. És una còpia automàtica de l’estat del sistema que permet tornar enrere després de canvis problemàtics, sense afectar els arxius personals**

### Per què és correcta
Al `bloc05.md` es diu:
- “Els punts de restauració són: còpies automàtiques del sistema operatiu”
- “recuperació del sistema en cas de problemes”
- “mecanisme que no afecta els arxius personals”

### Per què les altres no
- **b. És el mateix que una còpia mirall del disc dur** → incorrecta; la còpia mirall és un altre tipus de còpia de seguretat.
- **c. És una eina de recuperació exclusiva del mode segur amb xarxa** → incorrecta; el material no diu això.
- **d. És una còpia completa de tots els fitxers personals i de totes les particions del disc** → incorrecta; al contrari, diu que no afecta els arxius personals.

### On surt exactament
- `bloc05.md` → **Punts de restauració a Windows**

---

## Pregunta 4
**Quina associació ordre-funció és correcta a Ubuntu?**

### Resposta correcta
**d. `lspci` → mostra busos i dispositius PCI**

### Per què és correcta
Al `bloc08.md` es diu:
- `lspci` → mostra els **busos i dispositius PCI**

Al `bloc06.md` també surt:
- `lspci` → mostra **dispositius PCI**

### Per què les altres no
- **a. `fdisk -l` → mostra exclusivament dispositius USB** → incorrecta; al material `fdisk -l` mostra dispositius d’emmagatzematge.
- **b. `lsusb` → mostra dispositius PCI** → incorrecta; `lsusb` mostra dispositius USB.
- **c. `dmesg` → llista només paquets `.deb`** → incorrecta; `dmesg` mostra controladors detectats o reconeguts pel nucli.

### On surt exactament
- `bloc08.md` → **Per a què serveixen aquestes ordres**
- `bloc06.md` → **Ordres per llistar maquinari i controladors**

---

## Pregunta 5
**Quina afirmació descriu millor la diferència entre CMD i PowerShell?**

### Resposta correcta
**c. CMD està orientat a ordres bàsiques, mentre que PowerShell treballa amb objectes i facilita l’administració i l’automatització**

### Per què és correcta
Al `bloc02.md` es diu:
- **CMD**:
  - “Més simple”
  - “Ordres clàssiques”
  - “Útil per tasques bàsiques”
- **PowerShell**:
  - “Treballa amb objectes, no només amb text”
  - “Millor per automatització i administració”

### Per què les altres no
- **a. PowerShell és un substitut del kernel de Windows** → incorrecta; el material no ho diu.
- **b. CMD només existeix a Windows 7 i PowerShell només a Windows 11** → incorrecta; no surt al material.
- **d. CMD i PowerShell treballen igual, però PowerShell només canvia el color de la consola** → incorrecta; el material remarca diferències importants de capacitat.

### On surt exactament
- `bloc02.md` → **PowerShell: intèrpret avançat**
- `bloc02.md` → **CMD vs PowerShell**

---

## Pregunta 6
**Quina afirmació descriu millor el paper dels mòduls del nucli a GNU/Linux?**

### Resposta correcta
**b. Permeten que el nucli carregui o descarregui controladors segons el maquinari detectat**

### Per què és correcta
Al `bloc08.md` es diu:
- “el nucli utilitza mòduls que es poden carregar o descarregar segons el maquinari detectat”
- “Aquests mòduls del nucli també s’anomenen controladors”

### Per què les altres no
- **a. Només es fan servir per gestionar usuaris i grups** → incorrecta; el material els relaciona amb maquinari i controladors.
- **c. Són còpies de seguretat automàtiques del sistema** → incorrecta; això no apareix al material.
- **d. Són fitxers d’usuari que només serveixen per personalitzar l’escriptori** → incorrecta; no és el que diu el bloc.

### On surt exactament
- `bloc08.md` → **Nucli modular i controladors**

---

## Pregunta 7
**Quina afirmació diferencia correctament una còpia incremental d’una còpia diferencial?**

### Resposta correcta
**c. La incremental guarda els canvis des de l’última còpia feta, mentre que la diferencial guarda els canvis des de l’última còpia completa**

### Per què és correcta
Al `bloc05.md` es diu:
- **Còpia incremental** → “guarda els canvis des de l’última còpia que s’hagi fet, sigui completa o incremental”
- **Còpia diferencial** → “guarda només els canvis des de l’última còpia completa”

### Per què les altres no
- **a. La diferencial guarda menys informació que la incremental perquè només desa fitxers comprimits** → incorrecta; això no surt al material.
- **b. Totes dues guarden sempre exactament el mateix conjunt d’arxius** → incorrecta; el material les diferencia clarament.
- **d. La incremental només es pot fer a Windows i la diferencial només a Ubuntu** → incorrecta; el material no diu això.

### On surt exactament
- `bloc05.md` → **Tipus de còpies de seguretat**

---

## Pregunta 8
**Quina diferència és correcta entre configuració automàtica i manual d’un proxy a Windows?**

### Resposta correcta
**d. La configuració automàtica detecta o carrega la configuració del proxy, mentre que la manual obliga a introduir adreça i port del servidor proxy**

### Per què és correcta
Al `bloc08.md` es diu:
- **Configuració automàtica** → “detecta automàticament la configuració del proxy” i “pot fer servir un script de configuració (PAC)”
- **Configuració manual** → “permet introduir manualment l'adreça i el port del servidor proxy”

### Per què les altres no
- **a. No hi ha cap diferència real entre totes dues** → incorrecta; el material sí que diferencia clarament els dos tipus.
- **b. La configuració automàtica sempre bloqueja Internet i la manual l’activa** → incorrecta; això no surt al material.
- **c. La configuració manual només funciona amb VPN i la configuració automàtica només amb firewall** → incorrecta; tampoc surt al material.

### On surt exactament
- `bloc08.md` → **Tipus de configuració del proxy**

---

## Pregunta 9
**Quina afirmació és correcta sobre firewall, VPN i proxy a Windows?**

### Resposta correcta
**a. La VPN estableix una connexió segura amb una xarxa privada, el firewall controla connexions d’entrada i sortida, i el proxy actua com a intermediari entre l’equip i Internet**

### Per què és correcta
Al `bloc08.md` es diu:
- **Firewall** → “controla les connexions d'entrada i sortida de la xarxa”
- **VPN** → “permet establir una connexió segura i encriptada a una xarxa privada a través d'Internet”
- **Proxy** → “actua com a intermediari entre l'ordinador i Internet”

### Per què les altres no
- **b. El firewall només s’utilitza en xarxes públiques i no en xarxes privades o de domini** → incorrecta; el material no diu això.
- **c. El firewall xifra la connexió, la VPN filtra aplicacions i el proxy substitueix els controladors de xarxa** → incorrecta; això no coincideix amb les definicions del material.
- **d. El proxy i la VPN són exactament el mateix, però amb noms diferents** → incorrecta; el material els descriu com a eines diferents.

### On surt exactament
- `bloc08.md` → **Firewall i protecció de xarxa a Windows**
- `bloc08.md` → **Configuració de VPN a Windows**
- `bloc08.md` → **Configuració de proxy a Windows**

---

## Pregunta 10
**Quin és el sentit correcte de la sintaxi general d’una ordre en Bash?**

### Resposta correcta
**b. `nom_ordre [opcions] [arguments]`**

### Per què és correcta
Al `bloc02.md` es diu:
- “La sintaxi de les ordres inclou: `ordre [opcions] [arguments]`”
- “Format general: `nom_ordre [-opcions] [arguments]`”

### Per què les altres no
- **a. `[opcions] nom_ordre [arguments]` obligatòriament sense espais** → incorrecta; el material diu que els espais són importants i dona el format amb el nom de l’ordre primer.
- **c. `arguments [opcions] nom_ordre`** → incorrecta; no coincideix amb la sintaxi explicada.
- **d. `nom_ordre [arguments] [opcions]` sempre en aquest ordre fix i únic** → incorrecta; el material no dona aquest ordre com a model general.

### On surt exactament
- `bloc02.md` → **Intèrpret d’ordres i sintaxi**
- `bloc02.md` → **Sintaxi d’una ordre en Bash**
- `bloc02.md` → **Errors habituals en executar ordres**

---

# RESPOSTES CORRECTES

## Versió B
1. **b**
2. **c**
3. **a**
4. **d**
5. **c**
6. **b**
7. **c**
8. **d**
9. **a**
10. **b**

## Versió A
1. **b**
2. **b**
3. **b**
4. **b**
5. **b**
6. **a**
7. **a**
8. **b**
9. **b**
10. **b**


