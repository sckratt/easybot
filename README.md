const Discord = require('discord.js'); // discord.js requis
const client = new Discord.Client(); // Création du client
const { EasyMusic, EasyEconomy } = require('easybot');

const musicBot = new EasyMusic({
    clientPrefix: ">>", // Préfix du bot musique
    youtubeApiKey: "YOUTUBE_API_KEY", // Clé d'API Youtube
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

client.login('BOT_TOKEN'); // Mettez ici le token de votre bot (à trouver sur: https://discord.com/developers/applications/)
