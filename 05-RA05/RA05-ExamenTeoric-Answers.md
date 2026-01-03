# 1. Quina afirmació defineix millor la virtualització segons el temari?

A) Executar aplicacions sense sistema operatiu
B) Simular maquinari físic mitjançant programari
C) Compartir fitxers entre ordinadors
D) Substituir el maquinari per programari

**Resposta correcta: B**

* **A)** Incorrecta. El temari no defineix la virtualització com l’execució d’aplicacions sense sistema operatiu, sinó com la simulació d’un equip complet.
* **B)** Correcta. El temari indica que la virtualització consisteix a **simular el funcionament del maquinari físic mitjançant programari**, permetent executar sistemes operatius com si fossin equips reals.
* **C)** Incorrecta. Compartir fitxers és una funció de xarxa o de sistemes, no una definició de virtualització.
* **D)** Incorrecta. La virtualització no substitueix el maquinari, sinó que el simula i l’aprofita.

---

## 2. Quin element és imprescindible per crear i executar màquines virtuals?

A) Sistema de fitxers
B) Hipervisor
C) Gestor d’arrencada
D) Controlador de xarxa

**Resposta correcta: B**

* **A)** Incorrecta. Tot i que el sistema de fitxers és necessari en un sistema, no és l’element clau per executar màquines virtuals.
* **B)** Correcta. El temari estableix que **l’hipervisor és el component imprescindible** que permet crear, gestionar i executar màquines virtuals.
* **C)** Incorrecta. El gestor d’arrencada s’utilitza en sistemes operatius, però no és l’element que permet la virtualització.
* **D)** Incorrecta. El controlador de xarxa no és essencial per crear una màquina virtual.

---

## 3. Quin tipus d’hipervisor s’executa directament sobre el maquinari físic?

A) Allotjat
B) De procés
C) Tipus 1
D) Emulat

**Resposta correcta: C**

* **A)** Incorrecta. Un hipervisor allotjat necessita un sistema operatiu amfitrió.
* **B)** Incorrecta. El temari no defineix “de procés” com una categoria d’hipervisor que s’executi directament sobre el maquinari.
* **C)** Correcta. El temari indica que l’**hipervisor de tipus 1** s’executa directament sobre el maquinari físic, sense sistema operatiu intermedi.
* **D)** Incorrecta. L’emulació no correspon a aquesta definició.

---

## 4. Quin enunciat descriu correctament un hipervisor de tipus 2?

A) Funciona sense sistema operatiu amfitrió
B) Ofereix el màxim rendiment possible
C) S’executa com una aplicació sobre un SO
D) Només s’utilitza en CPD

**Resposta correcta: C**

* **A)** Incorrecta. L’hipervisor de tipus 2 necessita un sistema operatiu amfitrió.
* **B)** Incorrecta. El màxim rendiment correspon habitualment als hipervisors de tipus 1.
* **C)** Correcta. El temari explica que un **hipervisor de tipus 2 s’executa com una aplicació sobre un sistema operatiu** existent.
* **D)** Incorrecta. No està limitat només a centres de processament de dades.

---

## 5. Quina és una característica general de les màquines virtuals de sistema?

A) Executen només una aplicació
B) Simulen un equip complet
C) Comparteixen sempre el nucli
D) No utilitzen disc virtual

**Resposta correcta: B**

* **A)** Incorrecta. Executar una sola aplicació correspon a una VM de procés.
* **B)** Correcta. El temari indica que les **màquines virtuals de sistema simulen un equip complet**, amb maquinari virtual propi.
* **C)** Incorrecta. Compartir el nucli és propi d’altres tecnologies, no de les VM de sistema.
* **D)** Incorrecta. Les VM de sistema utilitzen disc virtual.

---

## 6. Quina diferència conceptual separa una VM de sistema d’una VM de procés?

A) El tipus de disc utilitzat
B) El nombre de nuclis assignats
C) L’abast del que s’executa
D) La connexió de xarxa

**Resposta correcta: C**

* **A)** Incorrecta. El tipus de disc no defineix aquesta diferència.
* **B)** Incorrecta. El nombre de nuclis és una configuració, no una diferència conceptual.
* **C)** Correcta. El temari explica que la diferència està en **l’abast del que s’executa**: un sistema complet o només un procés.
* **D)** Incorrecta. La xarxa no defineix el tipus de VM.

---

## 7. Quin format de disc virtual és propi de VirtualBox segons el temari?

A) VMDK
B) VHD
C) VDI
D) ISO

**Resposta correcta: C**

* **A)** Incorrecta. VMDK és propi d’altres plataformes.
* **B)** Incorrecta. VHD està associat a altres solucions de virtualització.
* **C)** Correcta. El temari indica que **VDI és el format propi de VirtualBox**.
* **D)** Incorrecta. ISO és una imatge òptica, no un disc virtual de VM.

---

## 8. Quina característica defineix un disc virtual de mida fixa?

A) Creix segons l’ús
B) Assigna l’espai total des del principi
C) Depèn de la RAM
D) No ocupa espai al disc

**Resposta correcta: B**

* **A)** Incorrecta. Això descriu un disc de mida dinàmica.
* **B)** Correcta. El temari explica que un **disc de mida fixa assigna tot l’espai des del principi**.
* **C)** Incorrecta. El disc no depèn de la RAM.
* **D)** Incorrecta. Un disc virtual sempre ocupa espai al disc.

---

## 9. Quina funció general tenen les Guest Additions?

A) Crear snapshots automàtics
B) Millorar la integració host–guest
C) Substituir el controlador gràfic
D) Gestionar usuaris

**Resposta correcta: B**

* **A)** Incorrecta. Els snapshots no formen part de les Guest Additions.
* **B)** Correcta. El temari indica que les **Guest Additions milloren la integració entre l’amfitrió i la màquina virtual**.
* **C)** Incorrecta. No substitueixen el controlador gràfic del sistema.
* **D)** Incorrecta. No gestionen usuaris.

---

## 10. Quina funcionalitat forma part de les Guest Additions?

A) Xifratge del disc
B) Carpetes compartides
C) Reenviament de ports
D) Creació de xarxes

**Resposta correcta: B**

* **A)** Incorrecta. El xifratge no és una funció de les Guest Additions.
* **B)** Correcta. El temari inclou les **carpetes compartides** com una funcionalitat de les Guest Additions.
* **C)** Incorrecta. El reenviament de ports és una funció de xarxa.
* **D)** Incorrecta. La creació de xarxes no correspon a les Guest Additions.

---

## 11. Què és un snapshot en una màquina virtual?

A) Una còpia del disc físic
B) Un punt de l’estat de la VM
C) Un sistema de còpia externa
D) Un tipus de disc virtual

**Resposta correcta: B**

* **A)** Incorrecta. No és una còpia del disc físic.
* **B)** Correcta. El temari defineix un **snapshot com un punt de l’estat de la màquina virtual** en un moment determinat.
* **C)** Incorrecta. No és un sistema de còpia externa.
* **D)** Incorrecta. No és un tipus de disc.

---

## 12. Quin element pot quedar inclòs en un snapshot?

A) Només fitxers personals
B) Estat del sistema
C) Només la configuració de xarxa
D) Només la RAM

**Resposta correcta: B**

* **A)** Incorrecta. No inclou només fitxers personals.
* **B)** Correcta. El temari indica que un snapshot pot incloure **l’estat del sistema** de la màquina virtual.
* **C)** Incorrecta. No es limita només a la xarxa.
* **D)** Incorrecta. No inclou només la RAM.

---

## 13. Quina definició correspon a la xarxa NAT?

A) Xarxa sense cap connexió
B) Connexió a Internet mitjançant l’amfitrió
C) Xarxa exclusiva entre VMs sense sortida
D) Connexió directa amb IP pròpia

**Resposta correcta: B**

* **A)** Incorrecta. NAT permet connexió.
* **B)** Correcta. El temari explica que la **xarxa NAT permet connexió a Internet mitjançant l’amfitrió**.
* **C)** Incorrecta. Això correspon a xarxa interna.
* **D)** Incorrecta. L’IP pròpia correspon a adaptador pont.

---

## 14. Quin enunciat descriu l’adaptador pont?

A) No permet connexió externa
B) Assigna IP de la xarxa física
C) Només connecta VMs entre elles
D) Depèn del DHCP intern

**Resposta correcta: B**

* **A)** Incorrecta. L’adaptador pont permet connexió externa.
* **B)** Correcta. El temari indica que l’**adaptador pont assigna una IP de la xarxa física**.
* **C)** Incorrecta. Això descriu xarxa interna.
* **D)** Incorrecta. No depèn d’un DHCP intern.

---

## 15. Què permet una xarxa interna a VirtualBox?

A) Accés directe a Internet
B) Comunicació amb l’amfitrió
C) Comunicació entre VMs seleccionades
D) Connexió a xarxes externes

**Resposta correcta: C**

* **A)** Incorrecta. No té accés a Internet.
* **B)** Incorrecta. No comunica amb l’amfitrió.
* **C)** Correcta. El temari indica que la **xarxa interna permet comunicació entre VMs seleccionades**.
* **D)** Incorrecta. No connecta amb xarxes externes.

---

## 16. Quin component configura el nombre de nuclis d’una VM?

A) Emmagatzematge
B) Pantalla
C) Processador
D) Xarxa

**Resposta correcta: C**

* **A)** Incorrecta. L’emmagatzematge no defineix nuclis.
* **B)** Incorrecta. La pantalla no afecta el nombre de nuclis.
* **C)** Correcta. El temari indica que el **processador configura el nombre de nuclis assignats a la VM**.
* **D)** Incorrecta. La xarxa no intervé.

---

## 17. Què és un benchmark segons el temari?

A) Un sistema operatiu virtual
B) Una tècnica de mesura de rendiment
C) Un controlador de dispositiu
D) Un format de disc

**Resposta correcta: B**

* **A)** Incorrecta. No és un sistema operatiu.
* **B)** Correcta. El temari defineix un **benchmark com una tècnica de mesura del rendiment**.
* **C)** Incorrecta. No és un controlador.
* **D)** Incorrecta. No és un format de disc.

---

## 18. Quin és l’objectiu principal d’un benchmark?

A) Instal·lar programari
B) Comparar rendiments
C) Crear VMs
D) Optimitzar la xarxa

**Resposta correcta: B**

* **A)** Incorrecta. No instal·la programari.
* **B)** Correcta. El temari indica que l’objectiu és **comparar rendiments**.
* **C)** Incorrecta. No serveix per crear màquines virtuals.
* **D)** Incorrecta. No optimitza xarxes.

---

## 19. Quina és la primera fase d’una prova de rendiment?

A) Captura de dades
B) Anàlisi
C) Planificació
D) Pla d’acció

**Resposta correcta: C**

* **A)** Incorrecta. La captura ve després.
* **B)** Incorrecta. L’anàlisi no és la primera fase.
* **C)** Correcta. El temari indica que la **planificació és la primera fase** d’una prova de rendiment.
* **D)** Incorrecta. El pla d’acció és posterior.

---

## 20. Quina eina està pensada per a entorns virtualitzats massius segons el temari?

A) Novabench
B) Geekbench
C) PassMark
D) VMMark

**Resposta correcta: D**

* **A)** Incorrecta. Novabench és genèrica.
* **B)** Incorrecta. Geekbench és generalista.
* **C)** Incorrecta. PassMark no està pensat específicament per entorns massius virtualitzats.
* **D)** Correcta. El temari indica que **VMMark està pensada per a entorns virtualitzats massius**.
