# MongoDB
Este projeto consiste em uma demonstração prática das minhas habilidades em MongoDB, focando práticas e operações comuns no banco de dados NoSQL.

Resumo do projeto:

- Instalação e criação de bancos de dados, coleções e documentos no MongoDB;
- Realização de consultas, filtros e operações de atualização e exclusão em diferentes coleções;
- Modelagem de relacionamentos 1-N e N-N entre coleções;
- Criação de índices para otimização de consultas em coleções com atributos variados, incluindo índices únicos, compostos, esparsos e textuais;
- Configuração de um replica set para alta disponibilidade e replicação de dados;
- Implementação de um shard para distribuição horizontal de dados em múltiplos servidores;
- Utilização de diferentes storage engines, como mmapv1 e wiredTiger, e configuração de autenticação e autorização de usuários;
- Realização de operações de depuração, backup e restore em instâncias do MongoDB, demonstrando o uso de ferramentas como mongostat e mongotop.

## Instalações e criações

Criado o banco de dados "RB_rh" (sendo "RB" as iniciais para comprovação de autenticidade no projeto), juntamente com as coleções "RB_DEPARTAMENTO", "RB_FUNCIONARIO" e "RB_DEPENDENTE", seguido pela inserção de três documentos em cada coleção. A seguir, foi exibido o conteúdo de cada coleção. Obs: Todos os comandos estão disponíveis no topo da página no bloco de notas chamado "Scrip".

<p align="center">
    <img src="https://imgur.com/L9nTGeE.png" alt="codigo1">
</p>

Realização de filtro baseado numa descrição do departamento (igualdade) para a coleção "RB_DEPARTAMENTO".

<p align="center">
    <img src="https://imgur.com/Lx1wxeP.png" alt="codigo2">
</p>

Exibição dos ofuncionários que recebem salário acima de R $2000,00 para a coleção "RB_FUNCIONARIO".

<p align="center">
    <img src="https://imgur.com/rbTQyoc.png" alt="codigo3">
</p>

Execução do método distinct para o atributo nome para a coleção "RB_DEPENDENTE".

<p align="center">
    <img src="https://imgur.com/9OaXTQL.png" alt="codigo4">
</p>

Execução de um update para uma das coleções.

<p align="center">
    <img src="https://imgur.com/Yp4xTSj.png" alt="codigo5">
</p>

<p align="center">
    <img src="https://imgur.com/VY5W7Si.png" alt="codigo6">
</p>

Execução de um delete (remove) para uma das coleções.

<p align="center">
    <img src="https://imgur.com/3xeoqqQ.png" alt="codigo7">
</p>

<p align="center">
    <img src="https://imgur.com/1QjnCKg.png" alt="codigo8">
</p>

## Modelagem

Criado o banco de dados "RB_modelo" e posteriormente desenvolvido um pequeno modelo que envolve duas coleções com cardinalidades 1-N. As coleções foram nomeadas como "&&_col1a" e "&&_col2a". Nesse contexto, utilizou-se o conceito de referenciar o ID de uma coleção para a outra, enviando para o lado N como se fosse a chave primária do lado 1.

<p align="center">
    <img src="https://imgur.com/f6XcYkS.png" alt="codigo9">
</p>

Inserção de 2 documentos na coleção (lado 1).

<p align="center">
    <img src="https://imgur.com/oxOJyEE.png" alt="codigo10">
</p>

Inserção de 4 documentos na coleção (lado N).
Obs.: O lado 1 (é como se fosse a coleção mãe) e o lado N (é como se fosse a coleção filha). No item (B2) cada documento da coleção mãe deverá referenciar 2 documentos da coleção filha.

<p align="center">
    <img src="https://imgur.com/DSqd71p.png" alt="codigo11">
</p>

<p align="center">
    <img src="https://imgur.com/Xvlcg4G.png" alt="codigo12">
</p>

Criação de um pequeno modelo que envolve duas coleções com cardinalidades N-N, denominadas "RB_col1b" e "RB_col2b". Além disso, foram criadas três coleções e inseridos dois documentos em cada uma delas.

<p align="center">
    <img src="https://imgur.com/uUjRw6o.png" alt="codigo13">
</p>

<p align="center">
    <img src="https://imgur.com/SuqFQDM.png" alt="codigo14">
</p>

## Índices

Criação do banco de dados "RB_indeagreg" juntamente com uma coleção denominada "RB_indexar1", a qual apresenta pelo menos sete atributos, incluindo pelo menos um atributo do tipo array.

<p align="center">
    <img src="https://imgur.com/lkdOzsH.png" alt="codigo15">
</p>

Criação de um índice (não único e com ordenação ascendente).

<p align="center">
    <img src="https://imgur.com/7AE6kuj.png" alt="codigo16">
</p>
