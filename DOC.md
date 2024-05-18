# AZ Launcher (aka Pactify Launcher)

## Informations sur le Client

Concernant l'anticheat côté client vous êtes directement détecté à la modification d'une valeur détectée et un message sera envoyé directement
sur le serveur aux administrateurs même si vous trichez ailleurs, mais en revanche vous ne serez pas banni.

Il faut également savoir que si vous vous connectez à Pactify après avoir triché ou même avant sans avoir redémarrer votre launcher vous serez
banni car sa enverra quand même un message sur le serveur comme si vous y étiez connecté.

## Informations sur le Serveur

Concernant le serveur, le plugin utilisé comme anticheat est `OldNCP` (Ancien NoCheatPlus).

Nathan818 et le staff n'ont pas souhaiter mettre un plugin d'anticheat plus avancé pour plusieurs raisons, premièrement pour ne pas faire énormement de
logs, de falses positives et aussi pour ne pas être surcharger en protection sachant qu'une protection launcher est beaucoup plus fiable est avancée.

## Types d'alertes

- `MemoryHacking` Quand un joueur modifie une ou plusieurs constances détectées dans la mémoire de son jeu.
- `Injections` Quand un joueur injecte un fichier `dll` dans son jeu.

## Types de Protections

- `MemoryCorruption` Un code permettant de simuler un crash côté client une fois des valeurs modifiées.
- `MemoryFields` Ré-attribut des valeurs sous d'autres fields pour diminuer la facilité à avoir ces valeurs.
- `ThreadSleep` Un code ou le nom du processus a été référencé afin de le faire crash si il est lancé en même tant que `AZ-Launcher`.
- `Loop` Utilisation d'une boucle pour réinitialiser la valeur par défaut, code utilisé pour le `timer`.
