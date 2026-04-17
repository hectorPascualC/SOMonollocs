# Pràctica 4 part cron i crontab

- /home/hector/Documents
- /home/hector/backup/Documents

mkdir -p /home/hector/backup

nano backup_docs.sh

```bash
    #!/bin/bash
    # Indica que aquest script s'ha d'executar amb l'intèrpret Bash

    LOG="/home/hector/backup/cron.log"
    # Variable LOG:
    # guarda la ruta del fitxer de registre on anirem escrivint què passa

    # afegim al log primera linea d'inici de tasca
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] Inici de la tasca" >> "$LOG"
    # echo                  -> escriu text
    # $(date '...')         -> executa la comanda date i insereix la data i hora actual
    # %Y                    -> any
    # %m                    -> mes
    # %d                    -> dia
    # %H                    -> hora
    # %M                    -> minuts
    # %S                    -> segons
    # >> "$LOG"             -> afegeix aquest text al final del fitxer de log

    # afegim una segona linea indicant què s'ha copiat, a on i si ha sorgit un error
    cp -r "/home/hector/Documents" "/home/hector/backup/Documents" >> "$LOG" 2>&1
    # cp                    -> comanda de còpia
    # -r                    -> recursive, copia carpetes i tot el seu contingut intern
    # >> "$LOG"             -> afegeix la sortida normal al fitxer de log
    # 2>&1                  -> envia també la sortida d'error al mateix log

    if [ $? -eq 0 ]; then
    # if                    -> inicia una condició
    # $?                    -> codi de retorn de l'última comanda executada
    # -eq                   -> equal, igual a
    # 0                     -> vol dir que la comanda anterior ha acabat correctament
    # then                  -> si la condició es compleix, executa el bloc següent

        echo "[$(date '+%Y-%m-%d %H:%M:%S')] Còpia feta correctament" >> "$LOG"
        # Escriu missatge final al log que la còpia ha anat bé

    else
    # Si la condició anterior no es compleix, entra aquí

        echo "[$(date '+%Y-%m-%d %H:%M:%S')] ERROR: la còpia ha fallat" >> "$LOG"
        # Escriu missatge final al log que hi ha hagut un error

    fi
# Tanca l'estructura condicional if
```

