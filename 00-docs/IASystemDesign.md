## 1. Arquitectura

* És la **visió global** del software.
* Defineix **com està organitzat** tot el sistema a gran escala.
* Per exemple: **frontend + backend**, **MVC**, **monòlit** o **microserveis**.

**Idea clau per dir a classe:**
L’arquitectura és l’**esquelet general** de l’aplicació.

---

## 2. Disseny de sistemes

* És el procés de decidir **com construirem el sistema**.
* Baixa una mica més al detall que l’arquitectura.
* Defineix:

  * mòduls
  * base de dades
  * comunicació entre parts
  * seguretat
  * escalabilitat

**Idea clau per dir a classe:**
El disseny de sistemes és **pensar com encaixa tot** perquè el programa funcioni bé.

---

## 3. Patrons de disseny

* Són **solucions conegudes** a problemes habituals de programació.
* No defineixen tot el sistema, sinó **parts concretes**.
* Exemples:

  * **Singleton**
  * **Factory**
  * **Strategy**
  * **Observer**

**Idea clau per dir a classe:**
Els patrons de disseny són **maneres habituals i bones de resoldre problemes concrets** dins del software.

---

# Relació entre els tres

* **Arquitectura** → nivell més general
* **Disseny de sistemes** → nivell intermedi, organitza el sistema
* **Patrons de disseny** → nivell més concret, resol problemes puntuals

---

> L’arquitectura defineix l’estructura general del software, el disseny de sistemes defineix com es construeix i s’organitza, i els patrons de disseny aporten solucions concretes a problemes habituals de programació.

---

# Exemple botiga on-line

* **Arquitectura**: frontend, backend i base de dades
* **Disseny de sistemes**: mòdul d’usuaris, comandes, pagaments i notificacions
* **Patrons de disseny**: Strategy per diferents formes de pagament
