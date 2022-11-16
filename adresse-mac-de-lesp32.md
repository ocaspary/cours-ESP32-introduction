# Adresse MAC de l'ESP32

Tout objet connecté doit pouvoir être identifié. En l'occurrence, l'ESP32 dispose d'une adresse MAC qui lui est propre (appelée parfois adresse physique ou adresse Ethernet). Pour la récupérer, car celle-ci peut-être utile, vous pouvez utiliser le code suivant qui utilise la fonction ESP.getEfuseMac() et des déclages de registres d'un octet. Rappel : l'adresse MAC est sur 6 octets en hexadécimal.

_**Fichier GetChipID.ino pour récupérer l’adresse MAC du composant ESP32 (NodeMCU) :**_

```arduino
uint64_t chipid;

void setup() {
  Serial.begin(115200);
}

void loop() {
  chipid=ESP.getEfuseMac();//The chip ID is essentially its MAC address(length: 6 bytes).
  Serial.printf("ESP32 Chip ID = ");
  for(int i=0 ; i<5;i++)
  {
      Serial.printf("%02X:",(uint8_t)(chipid>>(i*8)));
  }
  Serial.printf("%02X\n",(uint8_t)(chipid>>40));
  delay(3000);
}
```

Dans le menu de l’Arduino IDE, Aller dans **Outils--> Moniteur Série** pour visualiser l’adresse MAC de votre ESP32 appelé Chip ID. Par exemple, dans le moniteur série, le programme retourne :

16:37:29.157 -> ESP32 Chip ID = 48:0C:8E:27:A5:50

(donne l’heure si la case « Afficher l’horodatage » est cochée)

**Autre possibilité avec un fichier utilisant une bibliothèque, appelé Get\_MAC\_Adress.ino**

```arduino
#include "WiFi.h"

void setup(){
  Serial.begin(115200);
 
  WiFi.mode(WIFI_MODE_STA);
 
  Serial.println(WiFi.macAddress());
}
 
void loop(){ }
```
