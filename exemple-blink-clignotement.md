# Exemple Blink (clignotement)

Le premier exemple à faire est celui du clignotement d'une LED. Comme l'ESP32 dispose d'une LED bleue par défaut sur le port GPIO2, nous allons l'utiliser.

L'objectif est de téléverser le programme et de le faire fonctionner sur l'ESP32 en vérifiant sur la sortie Terminal le bon déroulement lors du téléversement. Vérifier que vous avez bien un port COM actif.

```arduino
/*
  Blink
  Turns an LED on for one second, then off for one second, repeatedly.
*/

const int LED_BUILTIN = 2;  // Blue LED of the module ESP32-NodeMCU (see pinout)

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}
// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}

```

**Remarques pour mettre à jour votre programme sur l’ESP32 :**

\-  Appuyer sur le bouton BOOT lors du téléversement si le message suivant apparaît en rouge après la compilation : <mark style="color:red;">Failed to connect to ESP32 : Timed out … Connecting…</mark> &#x20;

Enlever votre doigt seulement quand le message <mark style="color:red;">Connecting</mark> s’affiche.

\- Appuyer sur le bouton RESET après le téléversement si vous n’avez pas le message :

<mark style="color:red;">Hard resetting via RTS pin …</mark>
