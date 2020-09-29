[![NPM](https://nodei.co/npm/easybot.png)](https://nodei.co/npm/easybot/)

# 🧰 EasyBot

## 📥 Installation
```
npm i easybot
```

## 💻 Exemple
```js
const Discord = require('discord.js'); // Require discord.js
const client = new Discord.Client(); // Create the bot client.
const { EasyMusic, EasyEconomy } = require('easybot');

const musicBot = new EasyMusic({
    clientPrefix: ">>", // Préfix du bot musique
    youtubeApiKey: "AIzaSyBNlvN2na4_rfKA2tPqeG71i6KPNZdIXmM", // Clé d'API Youtube
    discordClient: client, // Ne pas toucher,
    config: {
        helpCommand: true
    }
});
const economyBot = new EasyEconomy({
    clientPrefix: "$", // Préfix du bot économique
    discordClient: client, // Ne pas toucher
    config: { // Configurez votre bot Discord en répondant aux indications !
        helpCommand: true, // true: le bot enverra la liste des commandes | false: Le bot ne répondra pas à la commande "help"
        managerRoles: [], // ID des rôles qui peuvent gérer l'économie, utiliser les commandes pour ajouter/retirer de l'argent.
        startsWith: 1000, // Montant d'argent avec lequel le membre commence.
        cashParMessage: 3, // Nombre maximum d'argent / message (minimum préparamétré à 1)
        moneySymbole: "", // Votre symbole de monnaie ("💵" par défaut)
        custom: {} // Bientôt
    }
});

 
client.on('message', message => { // Ne pas toucher
    musicBot.onMessage(message);
    economyBot.onMessage(message);
});

client.login('NzU5ODE4MjM5NjI1Nzg5NDY5.X3DB4Q.RsLA5UErXu71WPeugezFGGfIgLM'); // Mettez ici le token de votre bot (https://discord.com/developers/applications/)
```

## 🤖 Commandes

### 🎶  [color=#735BC1]Musique[/color]
* **PLAY**
    * `play`,
    * `add`,
    * `p`,
    * **+ `<recherche par chaine de caractère | URL de la vidéo>`**

* **STOP**
    * `stop`,
    * `kill`,
    * `destroy`,
* **PAUSE**
    * `pause`,
* **RESUME**
    * `resume`,
    * `res`,
    * `play`,
    * `p`
* **SKIP**
    * `skip`,
    * `s`
* **NOW-PLAY**
    * `now-play`,
    * `np`
* **CLEAR**
    * `clear`,
    * `delete-queue`
* **REPEAT**
    * `repeat`,
    * `loop`
* **LEAVE**
    * `leave`,
    * `disconnect`
* **JOIN**
    * `join`,
    * `connect`
* **LYRICS**
    * `lyrics`,
    * `paroles`,
    * `text`
    * **+ `<recherche par chaine de caractère>`**
* **VOLUME**
    * `volume`,
    * `vol`,
    * `setVolume`
* **QUEUE**
    * `queue`,
    * `q`

### 💰 [color=#FFB900]Economie[/color]

