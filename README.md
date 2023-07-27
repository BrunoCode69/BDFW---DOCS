# BDFW---DOCUMENTAÇÃO
Documentação da linguagem basica de criação de bots na plataforma whatsapp (bdfw).

# Envio de mensagens:
```js
$send(); // Envia uma mensagem a quem executou o comando.
$reply(); // Responde a quem executou o comando.
```

# Exemplo de uso:
```js
$send("Hello World !");
$reply("I replied to your message!");
```

# Retorno:
![](https://i.imgur.com/5vxq3bL.png)
![](https://i.imgur.com/HjW1pWC.png)

# Envio de reações:

```js
$react(""); // Reaje a mensagem recebida
$remove_reaction(""); // Remove a reação da mensagem
```
# Exemplo de uso:
```js
$react("✅");
$remove_reaction("✅");
```
