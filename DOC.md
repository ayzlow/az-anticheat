# AZ Launcher (aka Pactify Launcher)

## Informations sur le Client

Concernant l'anticheat côté client


## Informations sur le Serveur

Concernant le serveur, le plugin utilisé comme anticheat est `OldNCP` (Ancien NoCheatPlus).

Nathan818 et le staff n'ont pas souhaiter mettre un plugin d'anticheat plus avancé pour plusieurs raisons, premièrement pour ne pas faire énormement de
logs, de falses positives et aussi pour ne pas être surcharger en protection sachant qu'une protection launcher est beaucoup plus fiable est avancée.

## Types d'alertes

- `MemoryHacking` Quand un joueur modifie une ou plusieurs valeurs détectés dans la mémoire de son jeu.
- `Injections` Quand un joueur injecte un fichier `dll` dans son jeu.

## Types de Protections

- `MemoryCorruption` Un code permettant de faire simuler un crash du launcher une fois des valeurs modifiées.
- `MemoryFields` Ré-attribut des valeurs sous d'autres fields pour diminuer la facilité à avoir ces valeurs.
- `ThreadSleep` Un code ou le nom du processus a été référencé afin de le faire crash si il est lancé en même tant que `AZ-Launcher`.
- `Loop` Utilisation d'une boucle pour réinitialiser la valeur par défaut, code utilisé pour le `timer`.


Quelques exemples des alertes en questions sur Pactify:

![PactifyAlert](https://i.ibb.co/fpTzFmM/image.png)
