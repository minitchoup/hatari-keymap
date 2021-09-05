# hatari-keymap
Tags: hatari keyboard keymap mapping binding keymap.c

## Français

### Introduction

Quelles modifications ont été apportées à la prise en charge du "mapping" clavier réalisé par l'émulateur Hatari.

Il devient grace à ça possible de faire ce qu'on veut ! Toutes les limitations ont été je crois levées.

Il est dès lors possible d'associer à une combinaison de touches (clavier de la machine hote), une combinaison de touches de la machine Atari émulée.

Par combinaison de touche j'entends une séquence de codes : le code des touches pressées dans l'ordre chronologique.

Un exemple vaut mieux qu'un long discours... Cet exemple est repris du fichier de configuration **keymap-fr.txt**.

Je suis dans la configuration suivante : j'ai un clavier PC 105 touches Azerty Français et je souhaite émuler le clavier de l'Atari équipé d'une ROM pour la France (donc pour un Atari ayant un clavier Français).

### Exemple 1 : Le cas du caractère '#'

    # '#'
    @32-0x200,0x2B

Sous Linux (machine hôte), la séquence est *@32-0x200*. Deux touches : `[AltGr]+[3]`

Pour l'Atari, internet est plein de ressource : https://www.jchr.be/atari/tables.htm. Une seule touche : celle qui se trouve en bas à droite de la touche "Return".

### Exemple 2 : La cas du caractère '{'

    # '{'
    @33-0x200,0x2A-0x38-0x1A

Sous Linux, il me faut faire un `[AltGr]+[4]` => *@33-0x200*

Sous Atari, il me faut faire un `[SfG]+[Alt]+[^]` => *0x2A-0x38-0x1A*

### Utilisation

Le code a été compilé avec succès avec la version Hatari clonée de GitHub en date du 05/09/2021.

Il suffit de cloner le source de Hatari puis de "remplacer" le fichier source **src/keymap.c** par le nouveau.

Le fichier de configuration **keymap-fr.txt** peut être utilisé dans la configuration Hatari. Il sert pour mapper le clavier PC 105 Fr vers le clavier Atari ST(e) Français. 

Ce code a été proposé en merge, mais faute de temps de ma part, n'a pas pu être intégré à la branche officielle.

En effet, le code n'a pas été testé dans toutes les configurations possibles !

Si quelqu'un se sent motivé, qu'il n'hésite surtout pas à "s'approprier" ce code, à le modifier, pour le soumettre au projet Hatari.

En espérant que cela puisse vous aider...


## English

### Introduction

Some changes have been made to the keyboard mapping support made by the Hatari emulator.

It becomes thanks to this possible to do what we want! All the limitations have been lifted, I believe.

It is therefore possible to associate a combination of keys (keyboard of the host machine) with a combination of keys of the emulated Atari machine.

By key combination I mean a sequence of codes: the code of the keys pressed in chronological order.

An example is better than a long speech ... This example is taken from the configuration file **keymap-fr.txt**.

I have the following configuration: I have a 105-key French Azerty PC keyboard and I want to emulate the keyboard of the Atari equipped with a ROM for France (therefore for an Atari with a French keyboard).

### Example 1: The case of the '#' character

    # '#'
    @ 32-0x200,0x2B

On Linux (host machine), the sequence is *@32-0x200*. Two keys: `[AltGr]+[3]`

For the Atari, the internet is full of resources: https://www.jchr.be/atari/tables.htm. Only one key: the one at the bottom right of the "Return" key.

### Example 2: The case of the character '{'

    # '{'
    @ 33-0x200,0x2A-0x38-0x1A

Under Linux, I need to do a `[AltGr]+[4]` => *@33-0x200*

Under Atari, I need to do a `[SfG]+[Alt]+[^]` => *0x2A-0x38-0x1A*

### Use

The code has been successfully compiled with the cloned Hatari version of GitHub as of 09/05/2021.

It is enough to clone the source of Hatari then to "replace" the source file **src/keymap.c** by the new one.

The **keymap-fr.txt** configuration file can be used in the Hatari configuration. It is used to map the PC 105 Fr keyboard to the Atari ST (e) Français keyboard.

This code was proposed in merge, but due to lack of time on my part, could not be integrated into the official branch.

Indeed, the code has not been tested in all possible configurations!

If someone feels motivated, let him especially not hesitate to "appropriate" this code, to modify it, to submit it to the Hatari project.

Hope this can help you ...
