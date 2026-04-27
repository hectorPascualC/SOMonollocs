---
marp: true
paginate: true
theme: default

header: "RA04 – Administració bàsica de sistemes operatius · Bloc 6 – Sistema d'arxius a GNU/Linux"
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
# **RA04 – Bloc 6**
## **Sistema d'arxius a GNU/Linux**

**SMX01 - Sistemes Operatius Monolloc**  
**Professor - Hèctor Pascual**

---

<!-- SLIDE 2 -->
# 🔸 **Què treballarem en aquest bloc**

Aquest bloc se centra en:

- què és un **sistema d'arxius** a GNU/Linux  
- què vol dir **muntar** i **desmuntar** particions  
- diferències entre Windows i Linux  
- ordres bàsiques: `mount` i `umount`  
- fitxers de configuració: `/etc/mtab` i `/etc/fstab`  
- opcions habituals de muntatge

Objectiu: entendre com Linux fa accessibles els dispositius d'emmagatzematge dins l'arbre de directoris

---

<!-- SLIDE 3 -->
# 🔸 **Punt de partida**

En GNU/Linux, els discos, particions i dispositius no apareixen com a unitats independents amb lletra.

Tot queda integrat dins d'una única estructura:

```text
/
├── home
├── etc
├── media
├── mnt
└── var
```

Aquesta estructura rep el nom d'**arbre de directoris**.

---

<!-- SLIDE 4 -->
# 🔸 **Tasques bàsiques d'administració**

En la gestió del sistema d'arxius, l'administrador pot fer tasques com:

- **muntar** sistemes d'arxius  
- **desmuntar** dispositius o particions  
- revisar l'estat del sistema d'arxius  
- reparar errors o incoherències  
- gestionar l'espai disponible

En aquest bloc ens centrarem sobretot en el muntatge i desmuntatge.

---

<!-- SLIDE 5 -->
# 🔸 **Què és muntar una partició?**

**Muntar** una partició vol dir fer que el seu contingut sigui accessible des d'un directori del sistema.

Aquest directori s'anomena:

## **punt de muntatge**

Exemples habituals:

```bash
/mnt
/media
/media/usuari/USB
```

---

<!-- SLIDE 6 -->
# 🔸 **Idea visual del muntatge**

Abans de muntar:

```text
/dev/sdb1    → partició detectada, però no accessible directament
```

Després de muntar:

```text
/dev/sdb1    → /media/usb
```

Ara l'usuari pot entrar a:

```bash
/media/usb
```

i veure el contingut del dispositiu.

---

<!-- SLIDE 7 -->
# 🔸 **Diferència amb Windows**

A Windows, les unitats solen identificar-se amb lletres:

```text
C:\
D:\
E:\
```

A GNU/Linux, els dispositius es munten dins de l'arbre de directoris:

```text
/
├── home
├── media
│   └── usb
└── mnt
```

Idea clau: Linux no necessita una lletra d'unitat per accedir a una partició.

---

<!-- SLIDE 8 -->
# 🔸 **Dispositius i punts de muntatge**

En una ordre de muntatge apareixen dos elements importants:

- **dispositiu**  
  → partició o dispositiu que volem muntar  
  → exemple: `/dev/sda1`, `/dev/sdb1`, `/dev/cdrom`

- **punt de muntatge**  
  → directori des d'on s'accedirà al contingut  
  → exemple: `/mnt/usb`, `/media/cdrom`

---

<!-- SLIDE 9 -->
# 🔸 **Muntatge en mode gràfic**

En entorns d'escriptori com Ubuntu, molts dispositius es munten automàticament.

Exemple habitual:

- connectem un USB  
- apareix al gestor d'arxius  
- fem doble clic  
- el sistema el munta i mostra el contingut

Això és còmode per a l'usuari, però l'administrador també ha de saber fer-ho per terminal.

---

<!-- SLIDE 10 -->
# 🔸 **Muntatge per terminal**

La comanda principal és:

```bash
mount
```

Sintaxi general:

```bash
mount [opcions] [dispositiu] [punt_de_muntatge]
```

Exemple:

```bash
sudo mount /dev/sdb1 /mnt/usb
```

Això fa accessible `/dev/sdb1` dins de `/mnt/usb`.

---

<!-- SLIDE 11 -->
# 🔸 **Preparar el punt de muntatge**

Abans de muntar manualment, normalment cal crear el directori:

```bash
sudo mkdir /mnt/usb
```

Després es pot muntar el dispositiu:

```bash
sudo mount /dev/sdb1 /mnt/usb
```

I consultar-ne el contingut:

```bash
ls /mnt/usb
```

---

<!-- SLIDE 12 -->
# 🔸 **Opcions bàsiques de mount**

Opcions habituals:

- `-a`  
  → munta tots els sistemes definits a `/etc/fstab`

- `-r`  
  → munta en mode només lectura

- `-t`  
  → indica el tipus de sistema d'arxius

Exemple:

```bash
sudo mount -t ext4 /dev/sdb1 /mnt/dades
```

---

<!-- SLIDE 13 -->
# 🔸 **Tipus de sistema d'arxius**

Amb l'opció `-t` podem indicar el tipus de sistema d'arxius.

Exemples habituals:

```text
ext4
ntfs
vfat
exfat
iso9660
```

Exemple:

```bash
sudo mount -t ntfs /dev/sdb1 /mnt/windows
```

---

<!-- SLIDE 14 -->
# 🔸 **Què passa si el directori ja té contingut?**

Si muntem una partició sobre un directori que ja conté fitxers, aquests fitxers no s'esborren.

Però queden **ocults temporalment** mentre el dispositiu està muntat.

Exemple:

```text
/mnt/dades    → contingut original
/dev/sdb1     → muntat sobre /mnt/dades
```

Mentre estigui muntat, veurem el contingut de `/dev/sdb1`.

---

<!-- SLIDE 15 -->
# 🔸 **Com veure què està muntat?**

Podem executar:

```bash
mount
```

També podem consultar el fitxer:

```bash
/etc/mtab
```

Aquest fitxer mostra els sistemes d'arxius muntats actualment.

Idea clau: `/etc/mtab` descriu l'estat actual del muntatge.

---

<!-- SLIDE 16 -->
# 🔸 **Desmuntar un sistema d'arxius**

Per desconnectar correctament un dispositiu, fem servir:

```bash
umount
```

Sintaxi bàsica:

```bash
umount [dispositiu | punt_de_muntatge]
```

Es pot indicar el dispositiu o el punt de muntatge.

---

<!-- SLIDE 17 -->
# 🔸 **Exemples amb umount**

Desmuntar indicant el punt de muntatge:

```bash
sudo umount /media/cdrom
```

Desmuntar indicant el dispositiu:

```bash
sudo umount /dev/cdrom
```

Totes dues opcions poden ser vàlides si el sistema identifica correctament el muntatge.

---

<!-- SLIDE 18 -->
# 🔸 **Opcions bàsiques de umount**

Opcions destacades:

- `-a`  
  → desmunta tots els sistemes d'arxius indicats a `/etc/mtab`, excepte els essencials

- `-r`  
  → si no pot desmuntar, intenta remuntar en mode només lectura

Exemple:

```bash
sudo umount -r /mnt/usb
```

---

<!-- SLIDE 19 -->
# 🔸 **Quan pot fallar un umount?**

Pot fallar si el dispositiu està en ús.

Per exemple:

- hi ha una terminal oberta dins del directori  
- un programa està llegint un fitxer  
- s'està copiant informació  
- un procés manté el dispositiu ocupat

Abans de desmuntar, cal tancar fitxers, finestres o terminals que estiguin utilitzant el recurs.

---

<!-- SLIDE 20 -->
# 🔸 **El fitxer /etc/fstab**

El fitxer:

```bash
/etc/fstab
```

conté la configuració dels sistemes d'arxius que s'han de muntar automàticament.

S'utilitza sobretot per:

- particions internes  
- discos de dades  
- punts de muntatge permanents  
- configuracions que han de mantenir-se després de reiniciar

---

<!-- SLIDE 21 -->
# 🔸 **Diferència entre /etc/mtab i /etc/fstab**

`/etc/mtab`

- mostra què està muntat **ara mateix**  
- representa l'estat actual del sistema

`/etc/fstab`

- indica què s'ha de muntar **automàticament**  
- és una configuració permanent

Idea clau: `mtab` informa; `fstab` configura.

---

<!-- SLIDE 22 -->
# 🔸 **Estructura d'una línia de /etc/fstab**

Una línia de `/etc/fstab` acostuma a tenir aquests camps:

```text
dispositiu  punt_muntatge  tipus  opcions  backup  revisió
```

Exemple simplificat:

```text
UUID=xxxx  /dades  ext4  defaults  0  2
```

Cada camp té una funció concreta.

---

<!-- SLIDE 23 -->
# 🔸 **Camp 1: dispositiu**

El primer camp identifica què volem muntar.

Pot aparèixer com:

```bash
/dev/sda1
```

o com:

```bash
UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

El **UUID** identifica la partició de manera més estable que el nom `/dev/sdX`.

---

<!-- SLIDE 24 -->
# 🔸 **Camps 2 i 3: punt i tipus**

Segon camp:

```text
punt de muntatge
```

Exemple:

```bash
/dades
```

Tercer camp:

```text
tipus de sistema d'arxius
```

Exemples:

```text
ext4, ntfs, vfat
```

---

<!-- SLIDE 25 -->
# 🔸 **Camp 4: opcions de muntatge**

Opcions habituals:

- `auto` / `noauto`  
  → muntar automàticament o no

- `exec` / `noexec`  
  → permetre o impedir executar binaris

- `ro` / `rw`  
  → només lectura o lectura-escriptura

- `user` / `nouser`  
  → permetre o no que un usuari pugui muntar

- `sync` / `async`  
  → escriptura immediata o diferida

---

<!-- SLIDE 26 -->
# 🔸 **Camps 5 i 6: còpia i revisió**

Cinquè camp:

```text
backup
```

- `1` → activa còpia de seguretat  
- `0` → no activa còpia de seguretat

Sisè camp:

```text
revisió del sistema d'arxius
```

- `0` → no revisar  
- `1` → revisar primer  
- `2` → revisar després de l'arrel

---

<!-- SLIDE 27 -->
# 🔸 **Exemple complet de /etc/fstab**

Exemple orientatiu:

```text
UUID=1234-ABCD  /mnt/dades  ext4  defaults  0  2
```

Interpretació:

- munta la partició identificada pel UUID  
- la fa accessible a `/mnt/dades`  
- utilitza sistema d'arxius `ext4`  
- aplica opcions per defecte  
- no fa backup  
- la revisa després del sistema principal

---

<!-- SLIDE 28 -->
# 🔸 **Seqüència recomanada de treball**

Per muntar manualment un dispositiu:

1. identificar el dispositiu  
2. crear el punt de muntatge  
3. executar `mount`  
4. comprovar el contingut  
5. desmuntar amb `umount` quan ja no calgui

Aquesta seqüència evita errors i ajuda a entendre què està passant en cada pas.

---

<!-- SLIDE 29 -->
# 🔸 **Exemple pas a pas**

```bash
sudo mkdir /mnt/usb
```

```bash
sudo mount /dev/sdb1 /mnt/usb
```

```bash
ls /mnt/usb
```

```bash
sudo umount /mnt/usb
```

Objectiu: practicar el cicle complet de muntar, consultar i desmuntar.

---

<!-- SLIDE 30 -->
# 🔸 **Errors habituals**

Errors freqüents:

- escriure malament el dispositiu  
- no crear el punt de muntatge  
- muntar sobre un directori amb contingut important  
- intentar desmuntar mentre el dispositiu està en ús  
- editar `/etc/fstab` sense comprovar la sintaxi

Idea clau: en administració, és millor anar pas a pas i verificar cada acció.

---

<!-- SLIDE 31 -->
# 🔸 **Relació amb la pràctica A3**

Aquest bloc ajuda a entendre part de la pràctica A3, especialment quan es treballa amb:

- gestió d'arxius i directoris  
- espai de disc  
- dispositius d'emmagatzematge  
- comprovacions del sistema  
- captures explicades del que s'està fent

Encara que A3 també inclou monitoratge, xarxa i registres, aquí ens centrem en la base del sistema d'arxius.

---

<!-- SLIDE 32 -->
# 🔸 **Resum del bloc 6**

- GNU/Linux organitza els dispositius dins d'un únic arbre de directoris  
- muntar vol dir fer accessible una partició des d'un directori  
- `mount` permet muntar sistemes d'arxius manualment  
- `umount` permet desmuntar-los correctament  
- `/etc/mtab` mostra muntatges actuals  
- `/etc/fstab` defineix muntatges automàtics i permanents

---

<!-- SLIDE 33 -->
# **Fi del Bloc 6**
