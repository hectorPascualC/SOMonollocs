# **Kahoot RA05 – Preguntes 1 a 42 amb Explicacions (Versió Markdown)**

## **1) ¿Qué es la virtualización?**

**Correcta: “La abstracción de los recursos de un ordenador.”**

Per què és correcta:
La virtualització consisteix a crear una capa d’abstracció que simula maquinari (CPU, RAM, disc, xarxa) perquè un SO convidat cregui que està en una màquina física.

Per què les altres són incorrectes:

* “La implementación de un sistema integrado dentro de otro” → Descriu integració, no virtualització.
* “La encapsulación de un sistema operativo” → Això és més propi de contenidors, no de virtualització tradicional.
* “Ninguna es correcta” → Fals, la primera és exacta.

## **2) Las máquinas virtuales…**

**Correcta: “son unos programas que nos permiten simular otro SO.”**

Per què és correcta:
Una MV és software (hipervisor) que emula maquinari i permet executar un SO convidat.

Per què les altres són incorrectes:

* “son unos chips” → Les MV no són maquinari físic.
* “son unas web que nos permiten simular otro SO” → Web ≠ hipervisor.
* “son unos locos que nos permiten simular otro SO” → Distractor sense sentit tècnic.

## **3) ¿Cuántas máquinas virtuales puede tener abiertas el ordenador?**

**Correcta: “No hay número exacto.”**

Per què és correcta:
Depèn dels recursos disponibles: RAM, CPU i disc. No hi ha límit fix imposat pel hipervisor.

Per què les altres són incorrectes:

* “5” → Número arbitrari.
* “7, pero 14 con una opción de pago” → No és cert.
* “10” → També arbitrari.

## **4) Indica cuál es una ventaja de las máquinas virtuales**

**Correcta: “a y c” (Creación de entorno de pruebas + Aislamiento y seguridad)**

Per què és correcta:
El principal avantatge és l’aïllament i poder crear entorns controlats.

Per què les altres són incorrectes:

* “Creación de entorno de pruebas” → Correcta però incompleta sola.
* “Aislamiento y seguridad” → Correcta però incompleta sola.
* “Rendimiento inferior a la máquina real” → És un inconvenient, no un avantatge.

## **5) ¿Cuál de las siguientes opciones es un software que utilizamos para correr las máquinas virtuales?**

**Correcta: “VMware”**

Per què és correcta:
VMware Workstation/Player són hipervisors de tipus 2, igual que VirtualBox.

Per què les altres són incorrectes:

* “C++” → Llenguatge de programació.
* “Zinjal” → No és un hipervisor.
* “Arduino” → Maquinari, no virtualització.

## **6) ¿Para qué nos sirven las máquinas virtuales?**

**Correcta: “Todas son correctas.”**

Per què és correcta:
Serveixen per simular un SO, provar programes i aprendre nous sistemes.

Per què les altres són incorrectes individualment:
Cap és falsa, totes descriuen usos reals.

## **7) Se puede configurar las máquinas virtuales a tu gusto como: Discos duros, Carpetas compartidas, Modo de red, etc.**

**Correcta: “True”**

Per què és correcta:
VirtualBox permet configurar hardware virtual de manera flexible.

Per què és incorrecta l’altra:

* “False” → Incorrecte.

## **8) ¿Qué es VirtualBox?**

**Correcta: “Software de creación de máquinas virtuales.”**

Per què és correcta:
És un hipervisor de tipus 2.

Per què les altres són incorrectes:

* “Una nube de datos” → No és cloud.
* “Una Xbox” → No és una consola.
* “Una caja virtual” → Resposta absurda.

## **9) ¿Para qué sirven las instantáneas en VirtualBox?**

**Correcta: “Para guardar el estado de la máquina.”**

Per què és correcta:
Snapshot = estat complet (RAM, CPU, disc) guardat.

Per què les altres són incorrectes:

* “Para hacer capturas de pantalla” → No és una foto.
* “Para congelarla” → No exactament; guarda estat.
* “Para mudarlas de host” → Això és exportació, no snapshot.

## **10) ¿Qué es Guest Additions de VirtualBox?**

**Correcta: “Addiciones de invitado.”**

Per què és correcta:
Drivers i eines per millorar la integració del guest amb el host.

Per què les altres són incorrectes:

* “Un clic de pago” → No és de pagament.
* “Un sponsor de VirtualBox” → Fals.
* “Un paquete de software que añade funcionalidades a VirtualBox” → Semblaria correcta, però les Guest Additions s’instal·len al guest, no al VirtualBox.

## **11) Nombra dos programas de virtualización.**

**Correcta: “Nativo y alojado.”**

Per què és “correcta”:
El Kahoot ho planteja com categories teòriques (bare-metal i hosted), tot i que tècnicament hauria de ser “VMware y VirtualBox”.

Per què les altres són incorrectes:

* “algo y virtualbox” → No és correcte.
* “VMWare y VirtualBox.” → Tècnicament correcte, però el Kahoot ho marca com incorrecte.
* “Nativo y alojado” → La que el Kahoot vol.

## **12) VirtualBox es software libre gratuito.**

**Correcta: True**

Per què és correcta:
VirtualBox és gratuït i part del codi és lliure (GPLv2).

Per què l’altra és incorrecta:

* “False” → Incorrecte.

## **13) ¿Cómo se llama la máquina física sobre la que se instalan las máquinas virtuales?**

**Correcta: “HOST o anfitrión”**

Per què és correcta:
Host = equip físic. Guest = MV.

Per què les altres són incorrectes:

* “GUEST o invitado” → És la MV.
* “GUEST o anfitrión” → Incorrecte.
* “HOST o invitado” → Contradictori.

## **14) ¿Qué ventajas tienen las máquinas virtuales?**

**Correcta: “Probar un SO sin borrar el que tienes de manera segura.”**

Per què és correcta:
L’aïllament permet provar sistemes sense risc.

Per què les altres són incorrectes:

* “Es más rápido que el anfitrión” → Mai.
* “Ninguna de las anteriores” → Sí que hi ha avantatges.
* “Sus archivos no ocupan tanto…” → Els VDI poden ocupar molt.

## **15) ¿Qué son las máquinas virtuales?**

**Correcta: “simuladores de computadores”**

Per què és correcta:
Simulen hardware per executar sistemes operatius convidats.

Per què les altres són incorrectes:

* “máquinas que no existen” → Ambigu.
* “máquinas en línea” → No és definició.
* “máquinas distribuidas” → És un concepte diferent.

## **16) Si el ordenador anfitrión tiene un SO de 32 bits, el SO de las máquinas virtuales…**

**Correcta: “Debe ser obligatoriamente de 32 bits.”**

Per què és correcta:
Un host de 32 bits no pot virtualitzar SO de 64 bits.

Per què les altres són incorrectes:

* “Puede ser de 32 o de 64 bits” → No es pot.
* “Debe ser de 64 bits” → Impossible.
* “No es válido para VirtualBox” → Incorrecte.

## **17) El sistema operativo de los ordenadores virtuales…**

**Correcta: “Puede ser diferente al del ordenador anfitrión.”**

Per què és correcta:
És el principi de la virtualització.

Per què les altres són incorrectes:

* “Debe ser igual” → Fals.
* “No puede ser una versión superior” → Sí pot.
* “Debe ser Windows” → No.

## **18) ¿Qué es la virtualización?**

**Correcta: “Simular con hardware un S.O.”**

Per què és correcta:
El hardware virtualitzat fa creure al sistema convidat que és real.

Per què les altres són incorrectes:

* “Programar un software nuevo” → No és virtualització.
* “Utilizar gafas VR” → No té relació.
* “Todas son correctas” → Fals.

## **19) Nombra dos programas de virtualización.**

**Correcta: “VMWare y VirtualBox.”**

Per què és correcta:
Dos hipervisors molt utilitzats.

Per què les altres són incorrectes:

* “Linux” → No és virtualització.
* “Samsung” → Marca de hardware.
* “Mi casa” → Absurd.

## **20) La virtualización consiste en la creación de…**

**Correcta: “De una versión virtual.”**

Per què és correcta:
Simular maquinari.

Per què les altres són incorrectes:

* “Un sistema operativo” → És el convidat.
* “Software de programación” → No té relació.
* “De hardware real” → No es crea hardware físic.

## **21) ¿Cómo pueden comunicarse el sistema anfitrión y el huésped?**

**Correcta: “Todas son correctas.”**

Per què és correcta:
Pots usar arrossegar fitxers, xarxa i carpetes compartides.

## **22) La instalación de una máquina virtual la podemos hacer…**

**Correcta: “Las roja y amarilla son correctas.”**

És a dir:

* Des de CD/DVD/ISO
* Des d’un pendrive

Per què les altres són incorrectes:

* “Arrastrando ficheros” → No instal·la SO.

## **23) ¿Cuál es la diferencia entre anfitrión y huésped?**

**Correcta: “El equipo sobre el que se virtualiza es el anfitrión.”**

Per què és correcta:
Host = físic. Guest = virtual.

Per què les altres són incorrectes:

* “el huésped visualiza en poca calidad” → Sense sentit.
* “el equipo virtualiza desde el huésped” → Incorrecte.
* “anfitrión es el mejor visualizador” → Fals.

## **24) ¿Qué es la virtualización?**

**Correcta: “Simular con software un S.O.”**

Per què és correcta:
El hipervisor simula maquinari amb software.

Per què les altres són incorrectes:

* “Programar software” → No és virtualització.
* “Gafas VR” → No té relació.
* “Todas son correctas” → Fals.

## **25) ¿Cómo se puede mejorar la pantalla de una máquina virtual?**

**Correcta: “Instalando Guest Additions.”**

Per què és correcta:
Drivers optimitzats.

Per què les altres són incorrectes:

* “Instalando VirtualBox en otro PC” → No afecta.
* “Arrastrando la ventana” → No modifica resolució real.
* “Reiniciando” → No afegeix funcionalitats.

## **26) ¿Cuál es una razón para usar máquinas virtuales?**

**Correcta: “Para probar software en diferentes sistemas operativos.”**

Per què és correcta:
La virtualització permet proves multiplataforma.

Per què les altres són incorrectes:

* “Más rápidas que el host” → Mai.
* “Requieren menos recursos” → No sempre.
* “Ninguna” → Sí que hi ha raons vàlides.

## **27) ¿Qué se necesita para crear una máquina virtual?**

**Correcta: “Ram, disco duro y CPU.”**

Per què és correcta:
Són els recursos essencials.

Per què les altres són incorrectes:

* “Solo disco duro” → No funciona.
* “Un joystick” → No té sentit.
* “Solo CPU” → Faltaria RAM i disc.

## **28) ¿Cómo accede una máquina virtual al hardware físico?**

**Correcta: “A través del hipervisor.”**

Per què és correcta:
El hipervisor fa d’intermedi.

Per què les altres són incorrectes:

* “Directamente” → No en hipervisors de tipus 2.
* “Cable virtual” → No existeix.
* “Drivers del BIOS” → No interactuen així.

## **29) ¿Qué es un archivo .VDI?**

**Correcta: “Un disco duro virtual.”**

Per què és correcta:
Conté tot el sistema del guest.

Per què les altres són incorrectes:

* “Carpeta compartida” → No és disc.
* “ISO” → És mitjà d’instal·lació.
* “Archivo de configuración” → És .vbox.

## **30) ¿Qué tipo de red permite que la MV se conecte a Internet pero no sea visible desde el exterior?**

**Correcta: “NAT.”**

Per què és correcta:
NAT fa de router virtual.

Per què les altres són incorrectes:

* “Puente” → Fa visible la MV.
* “Interna” → Sense Internet.
* “Host-only” → Sense Internet.

## **31) ¿Qué tipo de almacenamiento puede crecer dinámicamente según lo que use el usuario?**

**Correcta: “Disco dinámico.”**

Per què és correcta:
Els VDI dinàmics s’expandeixen segons ús.

Per què les altres són incorrectes:

* “Disco fijo” → Espai preassignat.
* “ISO” → No creix.
* “Carpeta compartida” → No és disc.

## **32) ¿Qué red permite que la máquina virtual se comunique solo con el anfitrión?**

**Correcta: “Host-only.”**

Per què és correcta:
Xarxa privada entre MV i host.

Per què les altres són incorrectes:

* “NAT” → Té Internet.
* “Puente” → A la LAN real.
* “Interna” → MV↔MV només.

## **33) ¿Qué archivo guarda la configuración de la máquina virtual?**

**Correcta: “.vbox.”**

Per què és correcta:
És el fitxer de configuració.

Per què les altres són incorrectes:

* “.vdi” → Disc dur virtual.
* “.iso” → Imatge de SO.
* “.ova” → Exportació.

## **34) ¿Qué pasa si la máquina anfitriona se queda sin RAM mientras ejecuta varias máquinas virtuales?**

**Correcta: “El sistema puede volverse muy lento o bloquearse.”**

Per què és correcta:
Sense RAM → swapping → col·lapse.

Per què les altres són incorrectes:

* “Más rápido” → Impossible.
* “Nada” → Fals.
* “Se acelera” → Incorrecte.

## **35) ¿Qué permite crear y gestionar varias máquinas virtuales?**

**Correcta: “Un hipervisor.”**

Per què és correcta:
VirtualBox, VMware, Hyper-V.

Per què les altres són incorrectes:

* “Router” → No crea MV.
* “API” → No gestiona MV.
* “Kernel” → No és un hipervisor.

## **36) ¿Qué permite que los archivos de la MV estén en una carpeta del anfitrión accesible para ambos?**

**Correcta: “Carpetas compartidas.”**

Per què és correcta:
Permeten intercanvi host↔guest.

Per què les altres són incorrectes:

* “NAT” → Només xarxa.
* “Puente” → No té res a veure.
* “Snapshot” → Estat, no fitxers.

## **37) ¿Qué permite instalar un sistema operativo en una máquina virtual?**

**Correcta: “Una imagen ISO.”**

Per què és correcta:
Conté els fitxers d’instal·lació del SO.

Per què les altres són incorrectes:

* “Carpeta compartida” → No instal·la SO.
* “.vbox” → Configuració.
* “Snapshot” → Estat.

## **38) ¿Qué pasa si eliminas el archivo .VDI de una máquina virtual?**

**Correcta: “La MV pierde todo su contenido.”**

Per què és correcta:
És el disc dur virtual.

Per què les altres són incorrectes:

* “Funciona igual” → Impossible.
* “Configuación” → Seria .vbox.
* “Se regenera” → No passa.

## **39) ¿Qué tipo de red permite que la MV acceda a Internet usando la IP del anfitrión?**

**Correcta: “NAT.”**

Per què és correcta:
Comparteix IP del host.

Per què les altres són incorrectes:

* “Puente” → IP pròpia.
* “Interna” → Sense Internet.
* “Host-only” → Sense Internet.

## **40) ¿Qué opción permite copiar archivos arrastrando desde el anfitrión al huésped?**

**Correcta: “Guest Additions.”**

Per què és correcta:
Habilita drag-and-drop.

Per què les altres són incorrectes:

* “Puente” → Res a veure.
* “CPU virtual” → No aplica.
* “Instantánea” → No és per copiar.

## **41) ¿Qué característica NO pertenece a la virtualización?**

**Correcta: “Mejora el rendimiento frente al anfitrión.”**

Per què és correcta:
Mai és més ràpida que el host.

Per què les altres són correctes:
Permet provar SO, aïllar entorns i usar diversos SO.

## **42) ¿Qué archivo contiene el disco duro de la máquina virtual?**

**Correcta: “.vdi.”**

Per què és correcta:
És el disc virtual.

Per què les altres són incorrectes:

* “.vbox” → Configuració.
* “.iso” → Instal·lador.
* “.png” → No té relació.

