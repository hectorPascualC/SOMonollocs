# RA03 — Respostes de la part pràctica

## 1. Creació d’una tasca automatitzada amb `crontab`

Per programar una tasca automàtica perquè un script de còpia de seguretat s’executi **cada dia a les 17:00**, primer cal editar el `crontab` de l’usuari amb aquesta comanda:

```bash
crontab -e
```

A dins del `crontab`, la línia que s’ha d’escriure és aquesta:

```bash
0 17 * * * /home/alumne/backup_docs.sh >> /home/alumne/logs/backup.log 2>&1
```

Aquesta línia vol dir:
- `0` = minut 0
- `17` = hora 17
- `* * *` = qualsevol dia del mes, qualsevol mes i qualsevol dia de la setmana

Per tant, l’script s’executarà **cada dia a les 17:00**.

És important fer servir una **ruta absoluta** perquè `cron` no treballa igual que quan l’usuari està dins d’una carpeta concreta. Per això s’ha de posar la ruta completa de l’script.

Per comprovar que la tasca ha quedat registrada, cal executar:

```bash
crontab -l
```

Per comprovar si la tasca s’ha executat correctament, es poden fer aquestes comprovacions:
- provar manualment l’script:
```bash
/home/alumne/backup_docs.sh
```
- revisar el fitxer log:
```bash
cat /home/alumne/logs/backup.log
```

---

## 2. Explicació línia per línia de l’script

### Script

```bash
#!/bin/bash

LOG="/home/alumne/backup/cron.log"

echo "[$(date '+%Y-%m-%d %H:%M:%S')] Inici de la tasca" >> "$LOG"

cp -r "/home/alumne/Documents" "/home/alumne/backup/Documents" >> "$LOG" 2>&1

if [ $? -eq 0 ]; then
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] Còpia feta correctament" >> "$LOG"
else
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] ERROR: la còpia ha fallat" >> "$LOG"
fi
```

### Explicació

```bash
#!/bin/bash
```

Indica que aquest script s’ha d’executar amb l’intèrpret **Bash**.

```bash
LOG="/home/alumne/backup/cron.log"
```

Defineix una variable anomenada `LOG` que guarda la ruta del fitxer de registre on s’escriurà la informació.

```bash
echo "[$(date '+%Y-%m-%d %H:%M:%S')] Inici de la tasca" >> "$LOG"
```

Escriu una línia inicial al log amb la data i hora actual.
- `echo` escriu text
- `date` genera la data i hora
- `>>` afegeix el text al final del fitxer log

```bash
cp -r "/home/alumne/Documents" "/home/alumne/backup/Documents" >> "$LOG" 2>&1
```

Fa la còpia de la carpeta `Documents` cap a `backup/Documents`.
- `cp` és la comanda de còpia
- `-r` vol dir **recursive**, és a dir, copia carpetes i tot el seu contingut intern
- `>> "$LOG"` envia la sortida normal al log
- `2>&1` envia també la sortida d’error al mateix log

```bash
if [ $? -eq 0 ]; then
```

Comença una estructura condicional.
- `$?` és el codi de retorn de l’última comanda executada
- `-eq` vol dir **igual a**
- `0` vol dir que la comanda anterior ha acabat correctament
- `then` indica que s’executarà el bloc següent si la condició es compleix

```bash
echo "[$(date '+%Y-%m-%d %H:%M:%S')] Còpia feta correctament" >> "$LOG"
```

Si la còpia ha anat bé, escriu un missatge final al log indicant que s’ha completat correctament.

```bash
else
```

Si la condició anterior no es compleix, entra al cas d’error.

```bash
echo "[$(date '+%Y-%m-%d %H:%M:%S')] ERROR: la còpia ha fallat" >> "$LOG"
```

Si la còpia falla, escriu al log un missatge d’error.

```bash
fi
```

Tanca l’estructura condicional `if`.
