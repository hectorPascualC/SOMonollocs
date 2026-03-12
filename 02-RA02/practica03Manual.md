# Resolució de la pràctica

## Configuració de gestors d’arrencada i Dual Boot en VirtualBox

---

# 1. Configuració del gestor d’arrencada a Windows

Tot aquest apartat es realitza dins d'una **màquina virtual de Windows 10 a VirtualBox**. 

## 1.1 Obrir el símbol del sistema com administrador

1. Iniciar la màquina virtual **Windows 10**.
2. A la barra de cerca escriure:

```
cmd
```

3. Fer **clic dret** sobre **Símbol del sistema**.
4. Seleccionar:

```
Executar com a administrador
```

Això és necessari perquè **bcdedit només funciona amb permisos d’administrador**.

---

# 1.2 Veure la configuració actual de l’arrencada

Al terminal executar:

```
bcdedit /enum
```

Aquest comandament mostra la configuració actual del **Boot Configuration Data (BCD)**.

A la pantalla apareixerà informació com:

```
Windows Boot Manager
identifier {bootmgr}

Windows Boot Loader
identifier {current}
description Windows 10
```

Aquí podem veure:

* l'identificador del sistema
* el nom del sistema operatiu
* la configuració d’arrencada

---

# 1.3 Canviar el nom del sistema operatiu

Ara canviem el nom que apareix al gestor d’arrencada.

Executar:

```
bcdedit /set {current} description "Windows 10 VM"
```

Explicació:

* `{current}` indica el sistema operatiu actual
* `description` és el text que apareixerà al menú d’arrencada

Després del canvi, el sistema apareixerà com:

```
Windows 10 VM
```

---

# 1.4 Configurar el temps d’espera

Ara definirem el temps que el gestor d’arrencada espera abans d’iniciar el sistema per defecte.

Executar:

```
bcdedit /timeout 10
```

Això significa:

* el menú d’arrencada esperarà **10 segons**

Si hi hagués diversos sistemes operatius, l’usuari tindria aquest temps per seleccionar-ne un.

---

# 1.5 Configurar l’arrencada amb msconfig

Ara utilitzarem una eina gràfica.

## Pas 1

Premer:

```
Windows + R
```

Escrivim:

```
msconfig
```

---

## Pas 2

Anar a la pestanya:

```
Arrencada
```

Aquí es poden veure els sistemes instal·lats.

Opcions disponibles:

* seleccionar sistema operatiu predeterminat
* modificar el temps d’espera
* aplicar canvis

---

# 1.6 Verificació

1. Reiniciar la màquina virtual.
2. Comprovar:

* que el **nom del sistema és "Windows 10 VM"**
* que el temps d’espera és **10 segons**

Si els canvis s’han aplicat correctament, el gestor d’arrencada funcionarà amb la nova configuració.

---

# 2. Configuració del gestor d’arrencada GRUB a Ubuntu

Aquest apartat es realitza en una **màquina virtual Ubuntu 20.04**. 

---

# 2.1 Obrir el fitxer de configuració de GRUB

Obrir un terminal.

Executar:

```
sudo nano /etc/default/grub
```

Aquest fitxer conté els **paràmetres principals de GRUB**.

---

# 2.2 Configurar el sistema per defecte

Buscar la línia:

```
GRUB_DEFAULT=0
```

Significat:

* GRUB iniciarà **el primer sistema operatiu de la llista**

---

# 2.3 Configurar el temps d’espera

Buscar la línia:

```
GRUB_TIMEOUT=10
```

Modificar-la a:

```
GRUB_TIMEOUT=5
```

Això farà que el menú d’arrencada es mostri durant **5 segons**.

---

# 2.4 Afegir una imatge de fons

Afegir o modificar la línia:

```
GRUB_BACKGROUND="/usr/share/backgrounds/default.jpg"
```

Això permet mostrar una **imatge de fons al menú d’arrencada**.

---

# 2.5 Desar els canvis

Dins de nano:

```
CTRL + X
Y
ENTER
```

---

# 2.6 Actualitzar GRUB

Executar:

```
sudo update-grub
```

Aquest comandament:

* regenera la configuració del menú d’arrencada
* detecta sistemes operatius instal·lats
* aplica els canvis realitzats

---

# 2.7 Verificació

Reiniciar la màquina virtual.

Comprovar:

* que el menú de GRUB apareix
* que el temps d’espera és **5 segons**
* que es mostra la imatge de fons

---

# 3. Creació d’un sistema Dual Boot en VirtualBox

Aquest apartat consisteix en crear una nova màquina virtual amb **Windows i Ubuntu instal·lats al mateix disc**. 

---

# 3.1 Crear la màquina virtual

A VirtualBox:

1. Clicar **New**
2. Nom:

```
DualBoot_VM
```

3. Tipus:

```
Microsoft Windows
```

4. Versió:

```
Windows 10
```

---

# 3.2 Configuració de recursos

RAM recomanada:

```
4096 MB
```

CPU:

```
2 cores
```

---

# 3.3 Crear el disc virtual

Seleccionar:

```
VDI
```

Mode:

```
Dynamically allocated
```

Mida:

```
60 GB
```

---

# 3.4 Instal·lar Windows primer

Muntar la ISO de Windows.

Iniciar la VM.

Seguir la instal·lació normal de Windows.

Important:

**No utilitzar tot el disc.**

Deixar espai lliure per Ubuntu.

Exemple:

```
Windows → 35 GB
espai lliure → 25 GB
```

---

# 3.5 Instal·lar Ubuntu

Muntar la ISO d’Ubuntu.

Iniciar la instal·lació.

Seleccionar:

```
Install Ubuntu
```

Quan aparegui el tipus d’instal·lació:

Seleccionar

```
Install Ubuntu alongside Windows
```

L’instal·lador:

* detectarà Windows
* crearà particions Linux
* instal·larà GRUB

---

# 3.6 Finalitzar la instal·lació

Completar:

* usuari
* contrasenya
* configuració regional

Finalitzar instal·lació.

---

# 3.7 Verificació del Dual Boot

Reiniciar la màquina virtual.

Ha d’aparèixer el menú:

```
Ubuntu
Windows Boot Manager
Advanced options
```

Ara es pot seleccionar quin sistema operatiu iniciar.

