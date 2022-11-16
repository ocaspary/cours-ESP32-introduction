# Configuration

**Configuration**

Pour la partie Software, vous devez choisir votre langage de programmation ainsi que votre plateforme de développement. Plusieurs choix s’offrent à vous :

\-        Pour les langages : le langage assembleur dans des cas de contraintes sévères de temps réel, les langages C/C++ proches de la machine, Arduino, MicroPython, Java

\-        Pour les plateformes de développement (IDE) : Visual Studio, Eclipse, Visual Studio Code, Arduino IDE, PlatformIO, …

\-        Autres outils à ne pas négliger : le « flasher », l’ « uploader »

Pour de petits projets non-critiques ou personnels, MicroPython peut être intéressant car assez facile à apprendre et à comprendre. Cependant, il est préférable de rester près du niveau du microcontrôleur. Le langage C apparaît encore comme le langage à privilégier pour le développement ou, pourquoi pas du code Arduino avec des sketchs en .ino mais structurés pour basculer en .cpp. Pour plus d’explications, voir le lien ci-joint : [https://www.visualmicro.com/page/User-Guide.aspx?doc=INOs-and-CPPs.html](https://www.visualmicro.com/page/User-Guide.aspx?doc=INOs-and-CPPs.html)

A noter que le fabricant Espressif propose d’utiliser le langage C avec FreeRTOS pour pouvoir exploiter au mieux toutes les possibilités de l’ESP32. C’est la solution professionnelle à privilégier mais qui demande du temps pour s’approprier les connaissances du langage et son application à l’ESP32, même si des exemples sont fournis et peuvent être adaptés.

Aussi, pour s’intéresser à quelques montages et à l’échange des données, nous utiliserons l’IDE Arduino mais également l’extension VisualMicro dans Visual Studio 2017. Quant à PlateformIO, extension sous Visual Studio Code (donc possible également sous Linux), très complet, la partie Debug nécessite la création d’un compte pour fonctionner.

**IDE Arduino**

Pour l’IDE Arduino, la configuration associée au microcontrôleur NodeMCU est décrite ci-avant à la fin de l’introduction. Il suffit de relier la carte comprenant l’ESP32 à un ordinateur par un câble USB-miniUSB afin que le téléversement du programme se réalise par liaison série avec un port actif. Pour la programmation, afin d’accéder aux références du langage Arduino, créez un compte ou connectez-vous au site officiel avec vos identifiants Gmail :&#x20;

{% embed url="https://www.arduino.cc/reference/en/" %}

Nous allons cependant compléter cette installation et apporter quelques précisions concernant un élément important pour le développement qu’est le débogage.

Dans **Fichier --> Préférences**, mettez les paramètres suivants par défaut (voir capture d’écran ci-après) avec l’affichage des résultats détaillés et l’avertissement du compilateur, ainsi que l’URL de gestionnaire des cartes : [https://dl.espressif.com/dl/package\_esp32\_index.json](https://dl.espressif.com/dl/package\_esp32\_index.json) (liste non-officielle des cartes supportées).

**Activer le repli de code** : permet d’afficher un bouton à côté des numéros de lignez pour « replier » ou « déplier » des blocs de code (contenu d’une fonction, d’une boucle, …).

**Avertissement du compilateur** : cela n’empêche pas la compilation mais ce sont des sources de bugs potentiels que le compilateur détecte et qu’il est recommandé de modifier plutôt que de les masquer. Choisir l’option Tout.

**Changer le thème Arduino** : [https://github.com/jeffThompson/DarkArduinoTheme](https://github.com/jeffThompson/DarkArduinoTheme%20)

\- Télécharger en zip, puis décompressez DarkArduinoTheme-master.zip

\- Dans C:\Program Files (x86)\Arduino\lib, renommez le répertoire theme en theme\_old

\- Copiez le répertoire theme de DarkArduinoTheme-master et collez-le dans C:\Program Files (x86)\Arduino\lib, puis redémarrez l’IDE Arduino

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

_**Sous VS Code avec PlatformIO :**_

{% embed url="https://projetsdiy.fr/debuter-platformio-ide-visual-studio-code-vscode-windows-linux/" %}

_**Sous Visual Studio :**_

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

qui peut être complété par Visual Micro :

{% embed url="https://www.visualmicro.com/" %}

Exemple d'affichage :

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
