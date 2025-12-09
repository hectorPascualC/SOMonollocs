# 🖥️ Tipus de Virtualització  

### 1. **Virtualització de servidors**

És la més típica en entorns professionals.
Amb un sol servidor físic **pots crear molts servidors virtuals**, cadascun fent una funció diferent (AD, web, firewall, etc.).
**Objectiu:** estalviar diners, espai i consum elèctric.

*Exemple*: un sol servidor pot tenir un Windows Server, un Ubuntu Server i un firewall virtual.

---

### 2. **Virtualització d’escriptori (VDI)**

Els ordinadors dels usuaris **no treballen en local**.
Tot l’escriptori (Windows, aplicacions, documents) s'executa en un **servidor central** i l’usuari només hi accedeix per xarxa.

*Exemple*: els alumnes entren en un “escriptori virtual” que s’esborra cada dia.

---

### 3. **Virtualització de xarxes**

Consisteix a substituir dispositius físics (switches, routers, firewalls) per **versions virtuals** que funcionen amb programari.

*Benefici:* desplegar una xarxa complexa en minuts i sense comprar maquinari físic.

---

### 4. **Virtualització d’aplicacions**

L’aplicació no s’instal·la al PC de l’usuari.
S'executa dins d'un entorn encapsulat (com un contenidor o sandbox).

*Exemple*: executar una app de Windows dins de Linux gràcies a un entorn virtualitzat.

---

### 5. **Virtualització d’emmagatzematge**

Agrupa diferents discos o cabines en un **únic espai d’emmagatzematge virtual**.
Això facilita molt la gestió i la replicació.

*Exemple*: combinar 10 discos físics en un “gran disc virtual” per als servidors.

<br>
<br>

# 🖥️ Com entendre un Hipervisor de Tipus 1

### 2. Tipus 2

És **un programa instal·lat dins d’un sistema operatiu**:

* Tens **Windows** → instal·les **VirtualBox**
* Tens **Linux**   → instal·les **VMware Workstation**

Estan virtualitzes DINS del sistema operatiu

---

### 1. Tipus 1

**NO hi ha Windows.
NO hi ha Linux.
Només hi ha l’hipervisor.**

---

### 🔸Com funciona

Tu arranques el servidor i en comptes de carregar Windows, **carrega directament l'hipervisor**.

És com si l'hipervisor fos **el SO principal del servidor**, però està pensat només per crear i gestionar MV


