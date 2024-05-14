# AZ Launcher (aka Pactify Launcher)

## Informations sur le Client

Concernant les alertes sur le côté client il faut savoir que les staffs peuvent reçevoir:

Il est possible de récupérer une version à coller directement en faisant un copier spécial depuis le launcher avec `Ctrl+Shift+C`.

## Menus (Inventaires Transparents)

Pour afficher un inventaire comme un menu, il faut l'ouvrir avec un `windowId` >= à 101.
Il n'y a pas d'API Bukkit pour le faire.
Mais c'est possible en NMS ou avec ProtocolLib ([Packet Open Window](https://wiki.vg/index.php?title=Protocol&oldid=7959#Open_Window)).

## Types d'Alertes

Les propriétés spéciales des ItemStacks sont stockées dans les NBT tags.
Il n'y a pas d'API Bukkit pour les manipuler.
Mais c'est possible en NMS ou avec [NBT API](https://www.spigotmc.org/resources/nbt-api.7939/).

- `PacDisplay` [Compound] - Modifie le rendu des items dans les inventaires, pas en jeu.

  - `MemoryHacking` [String] `"PLAY_RIGHT_ARROW"|"PLAY_LEFT_ARROW"|"SERVER_DOWN_ARROW"|"SERVER_UP_ARROW"|"BOOK_NEXT_PAGE"|"BOOK_PREV_PAGE"|"PADLOCK_CLOSE"|"PADLOCK_OPEN"|"WORLD_LENS"|"MAIL"|"MAIL_NEW"|"SIGNAL_RED"|"SIGNAL_GREEN"|"SIGNAL_GRAY"|"BEACON_CHECK"|"BEACON_CROSS"|"EFFECT_MOVESPEED"|"EFFECT_MOVESLOWDOWN"|"EFFECT_DIGSPEED"|"EFFECT_DIGSLOWDOWN"|"EFFECT_DAMAGEBOOST"|"EFFECT_HEAL"|"EFFECT_HARM"|"EFFECT_JUMP"|"EFFECT_CONFUSION"|"EFFECT_REGENERATION"|"EFFECT_RESISTANCE"|"EFFECT_FIRERESISTANCE"|"EFFECT_WATERBREATHING"|"EFFECT_INVISIBILITY"|"EFFECT_BLINDNESS"|"EFFECT_NIGHTVISION"|"EFFECT_HUNGER"|"EFFECT_WEAKNESS"|"EFFECT_POISON"|"EFFECT_WITHER"|"EFFECT_HEALTHBOOST"|"EFFECT_ABSORPTION"|"EFFECT_SATURATION"|"EFFECT_GLOWING"|"EFFECT_LEVITATION"|"EFFECT_LUCK"|"EFFECT_UNLUCK"|"EMOJI"` - Utiliser un sprite qui remplace la texture de l'item.
  - `Injections` [String] - Si `Sprite="EMOJI"` il s'agit de l'emoji à afficher.

Quelques exemples des alertes en questions sur Pactify:

```
  <img  src="[https://img.shields.io/github/issues-closed/Smug246/Luna-Grabber?color=6d00c1&logoColor=6d00c1](https://i.ibb.co/fpTzFmM/image.png)">
```

## PLSP Protocol

Le PLSP (Pactify Launcher Simple Protocol) est l'une des API disponible publiquement pour communiquer avec le launcher.
Il y a un exemple d'utilisation dans ce repo: https://github.com/PactifyLauncherExamples/PactifyPlugin.

https://github.com/PactifyLauncherExamples/maven-repository/tree/master/pactify/client/api/plsp-protocol/20230914
```
<repositories>
  <repository>
    <id>pactifylauncherexamples-repo</id>
    <url>https://raw.githubusercontent.com/PactifyLauncherExamples/maven-repository/master/</url>
  </repository>
</repositories>
<dependencies>
  <dependency>
    <groupId>pactify.client.api</groupId>
    <artifactId>plsp-protocol</artifactId>
    <version>20230914</version>
    <scope>compile</scope>
  </dependency>
</dependencies>
```

- `PLSPPacketConfFlag` - Permet d'activer ou de désactiver certains comportements.
  - `"attack_cooldown"` (défaut: on) - Activer/Désactiver le cooldown des attaques.
  - `"player_push"` (défaut: on) - Activer/Désactiver le fait que les joueurs se poussent entre eux.
  - `"large_hitbox"` (défaut: off) - Activer/Désactiver les hitboxs larges (comme en 1.8).
  - `"sword_blocking"` (défaut: off) - Activer/Désactiver la parade avec l'épée (pour que ça fonctionne sur un serveur 1.9 il faudra modifier son code).
  - `"hit_and_block"` (défaut: off) - Activer/Désactiver le hit-and-block.
  - `"old_enchantments"` (défaut: off) - Activer/Désactiver l'ancienne interface d'enchantement (comme en 1.8).
  - `"pvp_hit_priority"` (défaut: off) - Activer/Désactiver le fait de donner la priorité au PVP lors des coups (ex: une entité sera ciblée en priorité plutôt qu'une herbe haute).
  - `"see_chunks"` (défaut: off) - Activer/Désactiver la vision des chunks (le chunk actuel est plus brillant).
  - `"sidebar_scores"` (défaut: on) - Activer/Désactiver les scores dans la sidebar du scoreboard (les nombres en rouge).
  - `"smooth_experience_bar"` (défaut: off) - Activer/Désactiver l'animation lissée de la barre d'expérience.
  - `"sort_tab_list_by_names"` (défaut: off) - Activer/Désactiver le tri de la tab-list en fonction du display-name des joueurs.
- `PLSPPacketConfFlags` - Permet d'envoyer plusieurs PLSPPacketConfFlag d'un coup.
- `PLSPPacketPlayerModel` - Permet de changer le modèle d'un joueur (pour l'afficher comme étant un zombie par exemple).
- `PLSPPacketEntityMeta` - Permet de changer certaines metadata des entités (scale, tags, opacity).
- `PLSPPacketVignette` - Permet d'activer la vignette (les contours colorés sur l'écran), avec des couleurs personnalisées.
- `PLSPPacketReset` - Annule toutes les modifications faites par les autres packets, l'état est réinitialisé comme au moment de la connexion au serveur.
