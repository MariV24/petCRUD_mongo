Banco de dados Mongo para cadastro de animais de estimação, passando: tipo do animal, nome e idade.

Funcionalidades:

***A função connect() é responsável por estabelecer a conexão com o banco de dados MongoDB.
    Ela é invocada no início de cada função que precisa interagir com o banco de dados para garantir que haja uma conexão ativa disponível.
    Dentro da função connect(), utilizamos o objeto MongoClient do pacote mongodb para criar uma instância do cliente MongoDB.
    Passamos a URL de conexão do MongoDB como parâmetro para o método MongoClient.connect().
    Ao estabelecer a conexão com o banco de dados, obtemos um objeto client que representa a conexão ativa com o MongoDB.
    Esse objeto é usado para interagir com o banco de dados, como inserir, consultar, atualizar ou excluir documentos.
    O método client.db(dbName) é usado para selecionar o banco de dados a ser utilizado.
    Aqui, passamos o nome do banco de dados como parâmetro, que no exemplo é "petshop".
    Em seguida, usamos o método db.collection(collectionName) para selecionar a coleção específica dentro do banco de dados. Neste caso, a coleção é "animais".
    O objeto collection retornado é usado para executar operações no banco de dados, como inserir, consultar, atualizar ou excluir documentos.
    Após concluir as operações necessárias, a função connect() é responsável por fechar a conexão com o banco de dados, chamando o método client.close().
    Isso garante que a conexão seja encerrada adequadamente.


***A função cadastrarAnimal(tipo, nome, idade) é usada para inserir um novo animal de estimação no banco de dados.
    Ela recebe três parâmetros: tipo (o tipo de animal), nome (o nome do animal) e idade (a idade do animal).
    A função se conecta ao banco de dados MongoDB, insere os dados do animal na coleção "animais" e exibe uma mensagem de sucesso.

***A função buscarAnimalPorTipo(tipo) é usada para buscar todos os animais de um determinado tipo no banco de dados.
    Ela recebe um parâmetro tipo (o tipo de animal) e retorna todos os animais correspondentes a esse tipo.
    A função se conecta ao banco de dados MongoDB, realiza a consulta na coleção "animais" e exibe os animais encontrados.

***A função buscarAnimais() é responsável por buscar todos os animais cadastrados no banco de dados MongoDB.
    Ela não recebe nenhum parâmetro.
    Utilizamos o método collection.find() para realizar a consulta na coleção "animais" e obter todos os documentos presentes nessa coleção.
    O método toArray() é chamado para converter o resultado da consulta em um array de documentos.
    Em seguida, utilizamos um loop for para percorrer o array de documentos e exibir as informações de cada animal (tipo, nome e idade) no console.

***A função buscarAnimalPorId(id) é usada para buscar um animal pelo seu ID no banco de dados.
    Ela recebe um parâmetro id (o ID do animal) e retorna o animal correspondente a esse ID.
    A função se conecta ao banco de dados MongoDB, realiza a consulta na coleção "animais" e exibe o animal encontrado.

***A função atualizarAnimal(id, tipo, nome, idade) é usada para atualizar os dados de um animal no banco de dados.
    Ela recebe quatro parâmetros: id (o ID do animal a ser atualizado), tipo (o novo tipo de animal), nome (o novo nome do animal) e idade (a nova idade do animal).
    A função se conecta ao banco de dados MongoDB, realiza a atualização na coleção "animais" com base no ID fornecido e exibe uma mensagem de sucesso ou falha.

***A função excluirAnimal(id) é usada para excluir um animal do banco de dados com base no seu ID.
    Ela recebe um parâmetro id (o ID do animal a ser excluído) e remove o animal correspondente do banco de dados.
    A função se conecta ao banco de dados MongoDB, realiza a exclusão na coleção "animais" com base no ID fornecido e exibe uma mensagem de sucesso ou falha.

Essas funções permitem realizar operações básicas de CRUD (criar, ler, atualizar e excluir) em relação aos animais de estimação no banco de dados MongoDB.

*******IMPORTANTE: Você deve iniciar seu servidor LocalHost para que o sistema funcione!!!!
* Lembre-se de chamar a função connect() antes de executar as funções. No caso desse CRUD, elas vem sempre após o "try{}".
* Esse projeto foi realizado em arquivos separados, então lembre de sempre exportar seus modulos (funções) ao final do código, e importá-los no começo do seu código, remetendo à função devida no arquivo raiz.
* Este projeto foi feito em uma máquina Windows 10, mas não deve haver problema algum em versões superiores. Se seu sistema é Linux, procure saber informações de como instalar o node diretamente do painel de controle.
* Antes de inicar o projeto, inicie os comandos em seu Prompt de Comando/Windows PowerShell os comandos: npm install node; npm install mongodb.

IDE: WebStorm
Linguagem: NodeJS
SGBD: MongoDB (Compass)