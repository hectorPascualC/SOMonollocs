🟦🟦🟦   🟦🟦🟦   🟦⬛🟦  
🟦⬛⬛   🟦⬛⬛   🟦⬛🟦  
🟦🟦🟦   🟦🟦🟦   🟦🟦🟦  
⬛⬛🟦   ⬛⬛🟦   🟦⬛🟦  
🟦🟦🟦   🟦🟦🟦   🟦⬛🟦  

─────────────────────     
◾ **Author**: Hèctor Pascual   
◾ **Description**: Warm up exercise for SMX  
◾ **Date**: 2025-2026 Academic Year 

# Pràctica SMX - Connexió SSH entre Ubuntu (client) i Windows Server (servidor) - VirtualBox + Netplan + SSH  

## 0. Objectius de la pràctica

En aquesta pràctica aprendràs:

- Què és **Netplan** i com configura la xarxa a Ubuntu.
- Què és **SSH** i per què és fonamental en administració de sistemes.
- Com crear dues màquines virtuals en **VirtualBox** amb xarxa interna.
- Com posar **IPs estàtiques** amb Netplan i Windows.
- Com instal·lar i activar **OpenSSH Server** a Windows.
- Com connectar-te des d'Ubuntu al Windows Server per **SSH**.

---

## 1. Conceptes previs

### 1.1. Què és Netplan?

Netplan és el sistema modern per configurar la xarxa a Ubuntu.  
Utilitza fitxers **YAML** per definir:

- IPs
- DNS
- Passarel·les (gateway)
- DHCP o IP estàtica

Tu edites un fitxer, fas `sudo netplan apply` i la xarxa es reconfigura automàticament.

---

### 1.2. Què és SSH?

SSH significa **Secure Shell**.  
Serveix per:

- Connectar-se remotament a un servidor
- Fer administració de sistemes sense estar físicament davant
- Enviar dades xifrades i segures

És l’eina principal d’administradors de Linux i Windows Server.

---

### 1.3. Què és una xarxa interna de VirtualBox?

Una **xarxa interna**:

- Connecta només les màquines virtuals
- No té sortida a internet
- És molt segura per pràctiques de xarxa i ciberseguretat

El nom proposat és: **XarxaSMX**

---

## 2. Configuració inicial a VirtualBox

### 2.1. Crear les màquines

- **Ubuntu Desktop** → Client  
- **Windows Server 2019/2022** → Servidor

### 2.2. Posar-les a la mateixa xarxa

Per a cada màquina:

1. Configuració  
2. Xarxa  
3. Adaptador 1  
   - ✔ Activat  
   - Mode: **Xarxa interna**  
   - Nom: **XarxaSMX**

Ara ja estan connectades entre elles.

---

## 3. Configurar IP estàtica a Ubuntu amb Netplan

### 3.1. Obrir el fitxer de configuració

A Ubuntu, obre terminal i executa:

```bash
sudo nano /etc/netplan/01-netcfg.yaml
```

### 3.2. Configuració Netplan

```yaml
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: no
      addresses:
        - 192.168.10.2/24
      gateway4: 192.168.10.1
      nameservers:
        addresses: [8.8.8.8]
```

Explicació:

* `dhcp4: no` → No volem DHCP
* `addresses` → IP + màscara /24
* `gateway4` → Porta d’enllaç
* `nameservers` → DNS de Google

### 3.3. Aplicar canvis

```bash
sudo netplan apply
```

### 3.4. Verificar

```bash
ip a
```

---

## 4. Configurar IP estàtica a Windows Server

1. Ves a:
   **Control Panel → Network and Sharing Center**

2. Clica "Change adapter settings".

3. Clic dret a **Ethernet → Properties**.

4. A “IPv4”, posa:

* IP: `192.168.10.3`
* Mask: `255.255.255.0`
* Gateway: `192.168.10.1`
* DNS: `8.8.8.8`

### Prova de connexió

Des del Windows:

```
ping 192.168.10.2
```

---

## 5. Instal·lar i activar OpenSSH Server al Windows Server

### 5.1. Instal·lar

Obre **PowerShell com a administrador**:

```powershell
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
```

### 5.2. Iniciar servei SSH

```powershell
Start-Service sshd
```

### 5.3. Fer-lo permanent

```powershell
Set-Service -Name sshd -StartupType Automatic
```

### 5.4. Comprovar que funciona

```powershell
netstat -an | findstr :22
```

Ha d'aparèixer **LISTENING**.

---

## 6. Connexió SSH des d'Ubuntu al Windows Server

A Ubuntu:

```bash
ssh administrator@192.168.10.3
```

Si demana:

```
Are you sure you want to continue connecting? (yes/no)?
```

Escriu:

```
yes
```

Introdueix la contrasenya del Windows Server.

---

## 7. Validació final

Dins de la sessió SSH, prova:

```powershell
hostname
```

```powershell
dir C:\Users
```

```powershell
Get-Service
```
