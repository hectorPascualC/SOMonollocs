# Exercici 1 — Interpretar una línia de `crontab` amb log

## Enunciat

Explica amb paraules què fa aquesta línia:

```bash
0 17 * * * /home/alumne/backup_docs.sh >> /home/alumne/logs/backup.log 2>&1
```

Han d’indicar:

* quan s’executa
* quin script executa
* què fa `>>`
* què fa `2>&1`
* per a què serveix el fitxer `backup.log`

---

## Resultat / solució

Aquesta línia vol dir:

* `0` → minut 0
* `17` → hora 17
* `* * *` → qualsevol dia del mes, qualsevol mes i qualsevol dia de la setmana

Per tant:

> **s’executa cada dia a les 17:00**

Després:

* executa l’script:

```bash
/home/alumne/backup_docs.sh
```

I després:

* `>> /home/alumne/logs/backup.log`
  afegeix la **sortida normal** al fitxer log

* `2>&1`
  envia també la **sortida d’error** al mateix fitxer log

  En Linux, una comanda pot tenir diferents “sortides”.
  - 1 és la sortida estàndard, el que surt normalment quan tot va bé
  - 2 és la sortida d’error, els missatges d’error  
  - El símbol > serveix per redirigir una sortida cap a un fitxer  
  - 2>: treballa amb la sortida d’error
  - &1: envia-la al mateix lloc que la sortida 1

Per tant, el resultat complet és:

> Cada dia a les 17:00 s’executa l’script `backup_docs.sh`, i tant la sortida normal com els errors es guarden al fitxer `backup.log`.

---

## Explicació 

### El temps

Els cinc primers camps indiquen **quan** s’executa la tasca.

```bash
0 17 * * *
```

Això es llegeix així:

* a les 17 hores
* al minut 0
* qualsevol dia

És a dir:

> cada dia a les 17:00

### Què fa amb la informació

El sistema executa l’script, però després pot passar una cosa important:

* pot sortir bé
* pot donar error
* o pot escriure missatges

Si no fem res, aquesta informació es perd.

Per això es posa:

```bash
>> /home/alumne/logs/backup.log 2>&1
```

Això serveix per guardar en un fitxer:

* el que surt bé
* i també els errors

### Idea simple 

> El `crontab` no només serveix per programar una tasca. També ens interessa saber què ha passat quan s’ha executat. Per això guardem la sortida i els errors en un log.

---

# Exercici 2 — Escriure una línia de `crontab` amb log

## Enunciat

Escriu la línia correcta de `crontab` per a aquest cas:

L’alumne té aquest script:

```bash
/home/alumne/scripts/copia.sh
```

Vol que:

* s’executi **cada dia a les 18:30**
* la sortida es guardi a:

```bash
/home/alumne/logs/copia.log
```

* i també s’hi guardin els errors

---

## Resultat / solució

```bash
30 18 * * * /home/alumne/scripts/copia.sh >> /home/alumne/logs/copia.log 2>&1
```

---

## Explicació didàctica per SMX1

### El temps

Volem que s’executi a les **18:30**.

A `crontab`, l’ordre dels camps és:

```text
minut hora dia_del_mes mes dia_de_la_setmana
```

Per tant:

* `30` = minut 30
* `18` = hora 18

Això dona:

```bash
30 18 * * *
```

### L’script

Després posem la ruta completa:

```bash
/home/alumne/scripts/copia.sh
```

És important que sigui **ruta absoluta**, perquè `cron` no treballa igual que quan l’usuari està dins d’una carpeta concreta.

### Log

Després afegim:

```bash
>> /home/alumne/logs/copia.log 2>&1
```

Això fa que:

* `>>` afegeixi informació al final del log
* `2>&1` guardi també els errors

### Idea simple 

> La línia de `crontab` té dues parts grans: quan s’executa i què fa. En aquest cas el que fa és executar l’script i guardar-ne el resultat en un fitxer log.

---

# Exercici 3 — Detectar i corregir errors

## Enunciat

Observa aquesta línia i indica què està malament. Després reescriu-la correctament.

```bash
30 18 * * * /home/alumne/scripts/copia.sh > /home/alumne/logs/copia.log
```

L’objectiu real és aquest:

* executar-se cada dia a les 18:30
* guardar sortida i errors en un fitxer log
* no esborrar el contingut anterior del log

---

## Resultat / solució

La part del temps està bé:

```bash
30 18 * * *
```

La ruta de l’script també està bé.

L’error està en aquesta part:

```bash
> /home/alumne/logs/copia.log
```

Perquè:

* `>` **sobreescriu** el fitxer log cada vegada
* no està guardant els errors
* només guarda la sortida normal

La línia correcta seria:

```bash
30 18 * * * /home/alumne/scripts/copia.sh >> /home/alumne/logs/copia.log 2>&1
```

---

## Explicació 

Aquest exercici és molt bo perquè els alumnes vegin que **una línia pot semblar correcta però no estar del tot ben feta**.

### Què fa `>`

El símbol `>` envia la sortida a un fitxer, però:

* si el fitxer ja existeix
* el contingut anterior es reemplaça

Per tant, si la tasca s’executa cada dia, només quedaria l’última execució.

### Què fa `>>`

Amb `>>` en canvi:

* no esborres el que hi havia
* afegeixes nova informació al final

Això és molt millor per a un log.

### Què falta si només posem `>`

Encara falta guardar els errors.

Per això s’afegeix:

```bash
2>&1
```

Això envia també la sortida d’error al mateix fitxer.

### Idea simple 

> Un log serveix per guardar historial. Si fem servir `>`, anem esborrant l’historial. Si fem servir `>>`, l’anem conservant. I amb `2>&1` també guardem els errors.

---

# Exercici 4 — Cas pràctic complet

## Enunciat

Un alumne té aquest script:

```bash
#!/bin/bash
cp -r /home/alumne/Documents /home/alumne/backup/
```

Vol que:

* s’executi cada dia a les **17:00**
* quedi registrat en un fitxer log cada vegada
* si hi ha un error, també quedi escrit al log

Respon:

### a)

Quina línia posaries al `crontab`?

### b)

Quina comanda faria servir per veure si la tasca està registrada?

### c)

Quina comanda faria servir per provar manualment l’script?

### d)

Quina comanda faria servir per veure el contingut del log, si el log és aquest?

```bash
/home/alumne/logs/backup.log
```

---

## Resultat / solució

### a) Línia de `crontab`

```bash
0 17 * * * /home/alumne/backup_docs.sh >> /home/alumne/logs/backup.log 2>&1
```

### b) Veure si la tasca està registrada

```bash
crontab -l
```

### c) Provar manualment l’script

```bash
/home/alumne/backup_docs.sh
```

### d) Veure el contingut del log

```bash
cat /home/alumne/logs/backup.log
```

També es podria fer amb:

```bash
less /home/alumne/logs/backup.log
```

---

## Explicació 

### a) Programar la tasca

La línia:

```bash
0 17 * * *
```

vol dir:

> cada dia a les 17:00

Després posem el script i el log.

### b) Comprovar si està registrada

Molts alumnes confonen:

* veure si està **registrada**
* veure si s’ha **executat**

Per veure si està registrada, fem:

```bash
crontab -l
```

Això mostra la configuració guardada.

### c) Provar l’script manualment

Abans d’esperar a les 17:00, convé provar-lo a mà:

```bash
/home/alumne/backup_docs.sh
```

Així sabem si:

* la ruta és correcta
* la còpia funciona
* no hi ha errors bàsics

### d) Mirar el log

Si hem programat la tasca perquè escrigui al log, després podem llegir-lo.

Això és molt útil perquè ens diu:

* si s’ha executat
* si hi ha hagut sortida
* si hi ha hagut errors

### Idea simple p

> Una automatització completa no és només fer que una cosa s’executi sola. També hem de poder comprovar què ha passat. Per això és tan important el log.

---

# Resum 

* **`cron`** és el servei que executa tasques programades
* **`crontab`** és el fitxer o eina on definim aquestes tasques
* una línia de `crontab` té:

  * una part de **temps**
  * una part de **comanda**
* si volem controlar què ha passat, hem de fer servir:

  * **redirecció de sortida**
  * **redirecció d’errors**
  * **fitxers log**

