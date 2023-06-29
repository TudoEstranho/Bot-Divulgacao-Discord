# Bot-Divulgacao-Discord

by: tudoestranho

O código acima é um script em Python que realiza o envio de mensagens diretas em massa no Discord. Aqui está uma explicação passo a passo do que ele faz:

Importa as bibliotecas necessárias: ctypes, threading, requests, time e json.

Define uma variável token vazia. Essa variável deve ser preenchida com um token de autenticação válido para o bot do Discord que será usado para enviar as mensagens diretas.

Define um cabeçalho de requisição headers contendo a autorização com o token do bot.

Cria duas listas vazias: dmed e not_dmed. Essas listas serão usadas para armazenar os IDs dos usuários que foram enviados com sucesso e os IDs dos usuários que não puderam ser enviados, respectivamente.

Define uma variável content que contém o conteúdo da mensagem que será enviada para os usuários.

Cria um dicionário msg que contém o conteúdo da mensagem.

Define a função title(text) que atualiza o título da janela do console.

Define a função date_send(text) que imprime uma mensagem no console.

Define a função massdm(total, user, msg) que realiza o envio da mensagem direta para um usuário específico.

a. Faz uma requisição POST para criar um canal de mensagem direta com o usuário.

b. Se a requisição for bem-sucedida, envia a mensagem para o canal criado.

c. Se a requisição retornar um código 200 (OK), adiciona o ID do usuário à lista dmed e imprime uma mensagem de sucesso.

d. Se a requisição retornar um código 429 (taxa limite excedida), espera um determinado período de tempo e tenta novamente.

e. Se a requisição retornar um código diferente de 200 ou 429, adiciona o ID do usuário à lista not_dmed e imprime uma mensagem de falha.

Abre o arquivo "ids.txt" que contém uma lista de IDs de usuários a serem enviados.

Abre o arquivo "blacklisted.txt" que contém uma lista de IDs de usuários que estão na lista de bloqueados e não devem receber a mensagem.

Percorre cada usuário na lista de IDs.

a. Verifica se o usuário está na lista de bloqueados. Se estiver, passa para o próximo usuário.

b. Inicia uma nova thread que executa a função massdm para enviar a mensagem direta para o usuário.

c. Espera um pequeno intervalo de tempo (0.1 segundo) antes de enviar a próxima mensagem, para evitar sobrecarregar o servidor do Discord.

Esse código é projetado para enviar mensagens diretas em massa para os usuários listados no arquivo "ids.txt", excluindo aqueles que estão na lista de bloqueados.
