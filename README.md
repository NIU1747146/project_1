Angel Moreno Renau NIU:1744714 <br>
Manel Palomares Burgada NIU:1747146

## 📌 Descripció del programa ##

Programa dissenyat per a l'empresa creadora de la web "Amor pel Setè Art". <br>
Aquest programa funciona com a gestor de bases de dades per a diverses entregues de premis amb varies funcions per llistar el seus continguts i realitzar cerques específiques. <br>

Les opcions actuals del programa són:

1. Llistats del catàleg:
    - Llistat d’actors i actrius per data del premi.
    - Llistat alfabètic de pel·lícules.
    - Llistat per edat d’actors i actrius.  
    - Tornar al menú anterior.    
2. Cerca al catàleg 
    - Qui va guanyar durant els anys ...?
    - Qui va guanyar amb la pel·lícula ...?
    - Pel·lícules guanyades per ...?
    - Tornar al menú anterior
3. Com ets d'Expert? 
    - 🚧  En desenvolupament...  🚧
4. Gestió del catàleg 
    - 🚧  En desenvolupament...  🚧
0. Sortir (Finalitzar el programa)

<br>

> [!IMPORTANT]  
> Abans de continuar, és important que tinguis un ordinador amb el sistema operatiu Linux, connexió a Internet i accés a un navegador web.


## ⚙ Execució ##

L'execució de l'script premis.sh haurà de ser realitzada amb dos paràmetres que correspondran a les bases de dades d'actors i actrius juntament amb la pel·lícula per la qual són nominats.

Dins d'aquest repositori es poden trobar dos arxius BestActors.csv i BestActress.csv per actors i actrius respectivament a mode de referència. Aquests contenen la informació dels nominats als premis Oscars al llarg del temps.

Així i tot, premis.sh implementa la seva funcionalitat de manera que es pot fer servir amb qualsevol base de dades sempre que aquesta contingui el mateix format de columnes i caràcters de separació que els arxius BestActors.csv i BestActress.csv.

A continuació indico el procediment de com executar el programa: 

```bash
# Clonar el projecte
$ git clone https://github.com/FonamentsEnginyeria/Part-A-equip-451-16.git

# Accedir a la carpeta del repositori
$ cd ./Part-A-equip-451-16

# Donar permisos d'execució
$ chmod +x premis.sh

# Executar el script amb els fitxers que contenen les dades 
$ ./premis.sh BestActor.csv BestAcress.csv
```

## ❗ Problemes sorgits durant la pràctica ##
En el que respecta a l'implementació del script premis.sh, vam haver de resoldre diverses qüestions pel seu correcte funcionament.

Primerament, a l'hora de llistar els continguts dels archius .csv necesitavem eliminar la primera fila amb el títol de cada columna, de manera que vam afegir un tail +2 dins la sèrie de pipes que serveixen per mostrar en pantalla el resultat d'algunes opcions del menu. Deixem un exemple a la següent línia:

```bash
cat $1 | cut -d,  -f2,3,4,5 | tail +2 | sort -t , -k 1
```

Posteriorment, a l'Opció 2 vam haver de trobar la manera de poder llegir nombres de pel·lícules senceres que continguin espais amb un read, pel qual vam haver d'afegir el flag -r. Deixem un exemple a la següent línia:.

```bash
read -r
```

També vam tindre alguns problemes a l'hora de realitzar el gràfic de GitHub que s'ens sol·licitava.

Dins de l'Opció 1 no ens vam adonar que havíem de crear branques per a cada tasca. Un cop finalitzada aquesta opció, es va fer el merge a main, però el resultat del gràfic no era el que es demanava. Per solucionar-ho, es va haver de fer un git reset fins a l'opció Menú i començar de nou. Aquesta vegada, es van crear totes les branques corresponents a cada tasca i es van anar realitzant els commits fins a completar-les totes. Des de l'Opció 1, es van anar fusionant les tasques una a una, i finalment es va fer el merge a main.

## 🎉 Conclusions ##

En conclusió, durant les sessions de pràctiques de la part A hem hagut d'aplicar tot el coneixement impartit a l'assignatura sobre scripts a bash i la utilització de repositoris locals i repositors remots per tal de finalitzar-la. A més, hem hagut de resoldre noves qüestions i problemes que ens han ajudat a practicar i entendre millor el funcionament d'aquestes eines ampliant així el nostre coneixement sobre la matèria.
