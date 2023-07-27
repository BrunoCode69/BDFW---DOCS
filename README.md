# BDFW---DOCUMENTAÇÃO
Documentação da linguagem basica de criação de bots na plataforma whatsapp (bdfw).

# Variaveis padrões do sistema:
```js
// USUARIO:
$username // Equivale ao nome do individuo que usou o comando.
$user_contact // Equivale ao numero do individuo que usou o comando.
$user_profile_description // Equivale a descrição do individuo que usou o comando.
$user_profile_message // Equivale ao recado do individuo que usou o comando.
$user_profile_status // Equive ao status do do individuo que usou o comando ["online", ["offline"]].
$user_profile_avatar // Equivale ao buffer da foto de perfil do individuo que usou o comando.
$user_profile_avatar_url // Equivale a uma URL PNG do perfil do individuo que usou o comando.
```
* BOT (APLICAÇÃO):
```js
$bot_name // Equivale ao nome do bot.
$bot_contact // Equivale ao numero do bot.
$bot_profile_description // Equivale a descrição do bot.
$bot_profile_message // Equivale ao recado do bot.
$bot_profile_status // Equivale ao status do bot.
$bot_profile_avatar // Equivale ao buffer da foto de perfil do bot.
$bot_profile_avatar_url // Equivale a uma URL PNG do perfil do bot.
```
* AVANÇADO (HOSPEDAGEM):
```js
$bot_host_time_month // Equivale aos meses de hospedagem restantes ao bot.
$bot_host_time_days // Equivale aos dias de hospedagem restantes ao bot.
$bot_host_time_hours // Equivale as horas de hospedagem restantes ao bot.
$bot_host_time_minutes // Equivale aos minutos de hospedagem restantes ao bot.
```

# Envio de mensagens:
```js
$send(); // Envia uma mensagem a quem executou o comando.
$reply(); // Responde a quem executou o comando.
```

* Exemplo de uso:
```js
$send("Hello World !");
$reply("I replied to your message!");
```

# Envio de reações:
```js
$react(""); // Reaje a mensagem recebida.
$remove_reaction(""); // Remove a reação da mensagem.
```
* Exemplo de uso:
```js
$react("✅"); // Reaje a mensagem recebida pelo BOT.
$remove_reaction("✅"); // Remove a reação da mensagem recebida.
```

* Definindo a mensagem em variaveis:
```js
$send("msg", "Hello World"); // Envia e ativa a variavel "msg" associada a mensagem enviada.
$react($msg, "👍"); // Reaje a mensagem equivalente a variavel "msg".

// Removendo a reação da mensagem enviada:
$remove_reaction($msg, "👍");
```
# Envio de arquivos:
* Obtendo o buffer da imagem pelo URL:

```js
$get_file_buffer("img", "https://imagem.png");
```

* Enviando o arquivo:
```js
$send_file($img, "Aqui está sua imagem !");
// ou
$reply_file($img, "Aqui está sua imagem !");
```

# Condições:
```js
$if // Condicional, feito para fazer comparações.
$else // Chamado quando a condição não se cumpre.
```

* Exemplo de uso:
```js
$if(10 + 10 == 20) {
    $send("O resultado do calculo 10+10 = 20 é verdadeiro.");
} $else {
    $send("O resultado do calculo 10+10 = 20 é falso.");
};
```

# Manipulação de strings JSON:
```js
$def_json("", ""); // Requer 2 parametros, a variavel e o conteudo em string JSON.
$find_json("", "") // Busca a key na variavel definida no $def_json.
```

* Exemplo de uso:
```js
$def_json("my_json", "{"message": "Hello World"}") // Define a variavel e o JSON que deseja ativar as funções.
$send("O conteudo da key message é: $find_json("message")");
```

# Requisições HTTP (Função premium):
```js
new $request("meu_request"); // Cria uma instancia chamada "meu_request".
$meu_request.setUrl("https://api.com.br"); // Define o URL do servidor que receberá o request
$meu_request.setMethod("POST"); // Define o tipo de request ["POST", "GET", "DELETE", "OPTIONS"] etc..
$meu_request.setType("JSON"); // Define o tipo de conteudo a ser recebido. ["JSON", "UTF-8"].
$meu_request.addHeaders("headers"); // Define o cabeçalho da requisição. (opcional, o tipo "JSON" já define o content-type).
$meu_request.send(); // Envia a requisição.
```

* Exemplo de uso:
```js
new $request("meu_request");
$meu_request.setUrl("https://api.com.br");
$meu_request.setMethod("POST");
$meu_request.setType("JSON");
$meu_request.addHeaders("headers");
$meu_request.send();

$send("Mensagem recebida da requisição: $def_json($meu_request)");
```
