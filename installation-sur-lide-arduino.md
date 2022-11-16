# Installation sur l'IDE Arduino

Ouvrez l’Arduino IDE, dans le menu : **Outils** à **Type de carte : "ESP32 Dev Module"**

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

Quand vous redémarrez, remettez la vitesse de téléversement à 115200.

Vous devez avoir un port série ouvert.

**Installation d’un port série virtuel**

Sous Windows 10, afin de communiquer par liaison série avec votre ESP32, téléchargez et installez le driver CP210x USB suivant :

[https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers)

Ensuite, dans votre gestionnaire de périphériques, vérifiez le numéro de port à utiliser pour votre communication avec l’Arduino IDE (COM4 dans l’exemple ci-dessous) **:**

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Vérifiez que vous utilisez bien un câble USB-miniUSB permettant la communication avec le port USB du PC et non un « simple » câble USB-miniUSB d’alimentation provenant d’un chargeur, sinon le port COM restera grisé dans l’IDE Arduino malgré l’installation du driver.
