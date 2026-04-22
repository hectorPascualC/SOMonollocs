# Exercici 1 — Interpretar una línia de `crontab` amb log

## Enunciat

Explica amb paraules què fa aquesta línia:

```bash
0 17 * * * /home/alumne/backup_docs.sh >> /home/alumne/logs/backup.log 2>&1
```

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
