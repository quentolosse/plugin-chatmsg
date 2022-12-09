
# Plugin chatmsg Bungeecord

## Description

### Chat personnalisable

Les messages envoyés par les joueurs sont envoyés sur les serveurs du même groupe que le serveur du joueur, ou juste sur le serveur du joueur, tout est configurable dans le fichier `config.yml`.

### Commande `/msg`
- Utilisation : `/msg <palyer> <message>`
- Envoie un message privé au joueur `<player>`

### Commande `/r`
- Utilisation : `/msg <message>`
- Envoie un message privé au dernier joueur avec lequel l'utilisateur de la commande a interagi (envoi ou réception de messages privés)

### Message de join et de leave
- Envoie un message de join sur tous les serveurs quand un joueur plus de 2 secondes se connecte au proxy
- Si le joueur est resté moins de 2 secondes sur le serveur, envoie un message de silent join dans la console

## Exemple de fichier `config.yml`:
```yaml
# message de join
join-format: '   &a&l+&r &7[&r%{prefix}&7] %{player}'

#message de leave
leave-format: '   &c&l-&r &7[&r%{prefix}&7] %{player}'

#message de /msg et /r 
msg-send: '&a&oMoi &7--> &o%{player} &7>>> &o%{message}'

msg-receive: '&a&o%{player} &7--> &oMoi &7>>> &o%{message}'

#message de tchat
chat-format: '&7[&r%{prefix}&7] %{pseudo} &8>>> &f%{message}'

#Si un message de tachat contient le pseudo du joueur il est remplacé par ce texte.
pseudo-format: '&d%{pseudo}' 

groups: #liste des groupes
  lobby: #nom du groupe
    shared: true # Tchat de ces serveurs sont syncronisés entre tous ces serveurs
    servers: # Serveurs dans ce groupe
    - hub1
    - hub2
    - hub3
  game:
    shared: false #Tchats de ces serveurs sont UNIQUEMENT reçus sur ces serveurs.
    servers:
    - game1
    - game2
    - game3
```

