# Carte d'acquisition permettant de récupérer le signal électrique

On a besoin d'une carte d'acquisition pour récupérer les tensions et les courants des 3 phases et du neutre de notre réseau triphasé. Pour se faire, nous allons faire un premier PCB qui sera appelé "Carte d'acquisition".
Nous avons listé ci-dessous l'ensemble des composants avec les caractéristiques techniques et les raisons du choix de ces derniers.

## Capteurs de tensions 
Référence : LEM LV 25-P 
Repères U1-U2-U3 
Rôle : Récupérer la tension de notre réseau électrique 
Composants choisis : Capteur de tension LEM LV 25-P
Raisons du choix : Le capteur LV25P est très précis et fiable, ce qui signifie qu'il mesure avec exactitude différentes tensions. Il est également facile à utiliser dans différents systèmes, ce qui le rend utile pour de nombreuses tâches. Ce dernier est donc très adapté avec notre projet d'analyseur de réseau électrique.


Caractèristiques techniques : 

![image](https://github.com/jsain78480/2324_Projet3DN_AnalyseurQualiteReseauElectrique/assets/144773577/42ebae67-2afa-42fd-a535-9975a1017a0a)

Schéma technique : 

![image](https://github.com/jsain78480/2324_Projet3DN_AnalyseurQualiteReseauElectrique/assets/144773577/8e5cee4c-4cc5-4115-b8be-255dfef610d6)

Dimensions du composants : 

![image](https://github.com/jsain78480/2324_Projet3DN_AnalyseurQualiteReseauElectrique/assets/144773577/c5bfaf82-d1ab-4d2a-9cc7-1e17e006b54c)

Lien vers la datasheet : 

https://www.lem.com/sites/default/files/products_datasheets/lv_25-p.pdf 

Selon le datasheet "Voltage Transducer LV 25-P", on sait que :
 - Taux de conversion = 2500 : 1000
 - Courant Is = 25 mA
 - Donc conrant Iin = 10 mA

Tension d'entrée est 230 V au maximum et -230 V au minmum, donc on choisit Vin comme 500V, R1 = Vin  / Iin = 500/10mA = 50 Kohm, la puissance de l'entrée est Iin*Vin = 10*230 = 2.3 kW.

On a Vout = 3.3 V au maximum, donc Rm = Vout (au maximum) / Is = 3.3/25mA = 132 ohm.

En conclusion, le taux de la tension est : Vout/Vin = 3.3/230 = 0.0143.  

## OP1 à OP7 : AOP
Tension d'entrée : V1(Vout de U1)
Tension de sortie : V2
Resistance variable : pour calibrer V2 à 3,3V  


Tension d'entrée : Provient du traco avec +15v
Tension de sortie : 3,3v pour alimenter le STM, l'écran, les LEDS, etc

## Contrôleur LCD I2C PCF8574 

## Ecran LCD LM016L

https://controllerstech.com/i2c-lcd-in-stm32/

# Carte de traitement permettant d'effectuer des calculs et d'afficher ces derniers à l'utilisateur 

## U3 : Régulateur linéaire et transfo XXXX pour alimenter le STM32
Tension d'entrée : +15 V
Tension de sortie : 3.3 V


