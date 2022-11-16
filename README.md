# Introduction

Avant de commencer à programmer un microcontrôleur, la première chose à faire consiste à regarder la documentation associée, dite « **Datashee**t », ainsi que les caractéristiques et performances de ce microcontrôleur. Autrement dit, nous ne pouvons pas dissocier la partie Hardware de la partie Software qui a pour objectif d’exploiter au mieux les possibilités offertes par le microcontrôleur. Pour cela, identifiez la carte et les composants intégrés principaux sur le site de référence : [http://esp32.net/#Hardware](http://esp32.net/#Hardware). Bien sûr, un passage par le site du constructeur de l’ESP32 (successeur de l’ESP8266) est incontournable, le site d’Espressif :

{% embed url="https://www.espressif.com/en" %}

<figure><img src=".gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

Définissez sur quelle carte vous travaillez en remplissant les champs suivants, par exemple :

| Maker             | Model        | Surface-Mount module | USB  UART     | Notes         |
| ----------------- | ------------ | -------------------- | ------------- | ------------- |
| Guoyun Technology | Goouuu-ESP32 | ESP-WROOM-32         | Silabs CP2102 | Carte hybride |

Ensuite, trouvez le schéma « pinout » de votre microcontrôleur afin de faire les branchements avec les bonnes pattes (voir ci-dessous). Faites attention aux valeurs de tensions et de courant à respecter : 3,3 V et 5V et environ 8 mA à 16 mA maximum par patte.

_**Exemple de schéma « pinout » pour l’ESP-WROOM-32 Module du NodeMCU :**_

<figure><img src=".gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

2 LED : une LED rouge pour l'alimentation et une LED bleue accessible via GPIO2.

**Attention :** Travailler avec le schéma correspondant à votre ESP32 car il en existe plusieurs modèles ! Bien regarder la documentation associée à votre composant !



**Description du NodeMCU ESP32**

Module basé sur un ESP32 cadencé à 240 MHz et exécutant le firmware open source NodeMCU. Cette carte se programme via l'IDE Arduino et est compatible avec les scripts LUA. Ce microcontrôleur dispose d'interfaces **WiFi et Bluetooth** idéales pour les objets connectés. L'interface sans fil Wifi permet la création de point d'accès sans fil, l'hébergement d'un serveur, la connexion à internet et le partage des données par exemple.\
Le module se programme directement à partir de l'IDE Arduino (installation d'une extension nécessaire) et nécessite un cordon microUSB (non inclus). Son implantation le rend compatible avec les plaques de connexions rapides.

**Caractéristiques du NodeMCU :**

* Alimentation : 5 Vcc via micro-USB, 3,3 Vcc via broches Vin
* Microcontrôleur : ESP32, Microprocesseur : Tensilica LX6 Dual-Core
* Fréquence : 240 MHz
* Mémoire SRAM : 512 kB, Mémoire Flash : 4 Mb
* 10 E/S digitales compatibles PWM
* Interfaces : I2C, SPI, UART, DAC, ADC
* Interface Wifi 802.11 b/g/n 2,4 GHz, Bluetooth : Classique / BLE, Antenne intégrée
* Température de service : -40 à 125 °C, Dimensions : 48 x 26 x 11,5 mm

**Les caractéristiques de l'ESP32**

L'ESP32 n'est pas une version améliorée de l'ESP8266, mais un tout nouveau circuit intégré Celui-ci embarque un SoC basé avec 2 cœurs Xtensa LX6 cadencé à 240 MHz remplaçant le cœur ARM de l'ESP8266, du Wi-Fi b/g/n/d/e/i/k/r jusqu'à 150 Mb/s pour le Wi-Fi n sur la bande 2412 - 2484 MHz, du Bluetooth 4.2 compatible avec le Bluetooth basse consommation, une horloge RTC intégrée, et de nombreuses entrées / sorties à savoir :

* 2 convertisseurs Analogique -> Numérique 8 canaux avec une précision sur 12 bits
* 2 convertisseurs Numérique -> Analogique avec une précision sur 8 bits
* 16 canaux PWM avec une précision sur 16 bits
* 3 canaux PWM pour le contrôle de moteurs avec une précision sur 16 bits
* 3 UART dont 2 avec contrôle du flux de données
* 2 interfaces I2C pouvant être utilisées en tant qu'hôte ou esclave
* 2 interfaces I2S
* 3 interfaces SPI supportant les modes hôte et esclaves
* 8 canaux pour des émetteurs et récepteurs IR
* 10 GPIO compatibles avec des touches tactiles capacitives
* 1 contrôleur hôte SD / SDIO / MMC compatible avec le standard SD 3.01
* 1 contrôleur SDIO esclave compatible avec le standard SD 2.0
* 1 interface JTAG
* 1 adresse MAC et 1 interface pour contrôleur Ethernet
* 21 GPIO fonctionnant à 3.3V, pas de compatibilité 5V officielle



_**ESP32 Pinout Reference du modèle NodeMCU utilisé (lien à conserver !!!) :**_

{% embed url="https://randomnerdtutorials.com/esp32-pinout-reference-gpios/" %}

&#x20;_ **Tableau des consommations par modes (datasheet ESP32) :**_

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

La consommation électrique est très réduite, en alimentant le circuit avec un pack de 2 piles AA 2500 mAh par exemple, on a environ un peu moins de 7h d'autonomie en émission continue à puissance maximale, 60 jours en veille avec les modules radio actifs, et environ 80 ans en hibernation ! Bien évidemment, à faible consommation électrique l'autonomie sera surtout définie par l'autodécharge des accumulateurs.

Dans le cadre de l’IoT, votre objet connecté doit pouvoir traiter des données, communiquer, être réactif, fiable et sécurisé. Enfin, sa consommation fait l’objet d’une attention toute particulière, notamment pour avoir une autonomie maximale. Pour cela, différents modes sont prévus pour l’ESP32 tels que : Active Mode, Modem Sleep Mode, Light Sleep Mode, Deep Sleep Mode, Hibernation Mode. Pour plus de détails, consultez le site web suivant :&#x20;

{% embed url="https://lastminuteengineers.com/esp32-sleep-modes-power-consumption/" %}

ou bien la documentation du fabricant de l’ESP32. La _"_consommation" mémoire est également à prendre en compte, et donc sa gestion, dans des projets qui prennent de l’ampleur.

_**Photo du microcontrôleur NodeMCU ESP32 (version 30 broches) :**_

<figure><img src=".gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
