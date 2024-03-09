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

# Instalações e criações

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

# Modelagem

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

# Índices

Criação do banco de dados "RB_indeagreg" juntamente com uma coleção denominada "RB_indexar1", a qual apresenta pelo menos sete atributos, incluindo pelo menos um atributo do tipo array.

<p align="center">
    <img src="https://imgur.com/lkdOzsH.png" alt="codigo15">
</p>

Criação de um índice (não único e com ordenação ascendente).

<p align="center">
    <img src="https://imgur.com/7AE6kuj.png" alt="codigo16">
</p>

Criação de um índice (único e com ordenação descendente).

<p align="center">
    <img src="https://imgur.com/w49oLKu.png" alt="codigo17">
</p>

Criação de um índice (com dois atributos).

<p align="center">
    <img src="https://imgur.com/TKM7ph6.png" alt="codigo18">
</p>

Crialção de um índice para um atributo array.

<p align="center">
    <img src="https://imgur.com/8vpayXB.png" alt="codigo19">
</p>

Criação de um índice esparso (com um atributo).

<p align="center">
    <img src="https://imgur.com/i7lE98P.png" alt="codigo20">
</p>

Criação de um índice com tempo de vida - TTL (com um atributo e com expiração de 20 segundos).

<p align="center">
    <img src="https://imgur.com/Onrmpij.png" alt="codigo21">
</p>

Inserção de 4 documentos na coleção.

<p align="center">
    <img src="https://imgur.com/7p97Sim.png" alt="codigo22">
</p>

Criação de uma segunda coleção de nome "RB_indexar2" (ela apresenta 4 atributos string).

<p align="center">
    <img src="https://imgur.com/jNR4NxE.png" alt="codigo22">
</p>

Criação de um índice textual para essa segunda coleção.

<p align="center">
    <img src="https://imgur.com/Jba5q0N.png" alt="codigo23">
</p>

Inserção de 4 documentos nessa segunda coleção.

<p align="center">
    <img src="https://imgur.com/b993dhc.png" alt="codigo24">
</p>

Criação de uma terceira coleção de nome "RB_Venda" (na qual tem os atributos: Cod_Venda, UF_Venda, Desc_Prod_Vendido, Valor_Venda).

<p align="center">
    <img src="https://imgur.com/4R0BAT9.png" alt="codigo25">
</p>

Inserção de 16 documentos (sendo 4 documentos para cada uma das UFs - são 4 UFs diferentes). 

<p align="center">
    <img src="https://imgur.com/sEvVWTl.png" alt="codigo26">
</p>

Criação de uma consulta que mostra o número de documentos por UF.

<p align="center">
    <img src="https://imgur.com/dbFw8iz.png" alt="codigo27">
</p>

Criação de uma consulta que mostre o valor total das vendas por UF.

<p align="center">
    <img src="https://imgur.com/uu8SgcV.png" alt="codigo28">
</p>

Criação uma consulta que mostre o valor de médias das vendas por UF.

<p align="center">
    <img src="https://imgur.com/gDzAGau.png" alt="codigo29">
</p>

Criação de uma consulta que mostre o maior valor de venda por UF.

<p align="center">
    <img src="https://imgur.com/keZXNei.png" alt="codigo30">
</p>

Criação de uma consulta que mostre o menor valor de venda por UF.

<p align="center">
    <img src="https://imgur.com/G4mCGTv.png" alt="codigo31">
</p>

# Replicação

Criação do replica set "RB_rsposmit" e criação a coleção "RB_col_filmes" no nó primário.

<p align="center">
    <img src="https://imgur.com/PVALcKy.png" alt="codigo32">
</p>

Inserção de 5 documentos na coleção "RB_col_filmes".

<p align="center">
    <img src="https://imgur.com/t3trEiz.png" alt="codigo33">
</p>

Acesso a um dos nós secundários.

<p align="center">
    <img src="https://imgur.com/xXGAfQ6.png" alt="codigo34">
</p>

# Particionamento

Criado um shard com quatro servidores shard (sem Replica Set) e configurado um servidor mongos.

<p align="center">
    <img src="https://imgur.com/kxZq5uJ.png" alt="codigo35">
</p>

<p align="center">
    <img src="https://imgur.com/tNyKxPd.png" alt="codigo36">
</p>

Conexão ao mongos e particionada uma coleção.

</p>
<p align="center">
    <img src="https://imgur.com/03Gr3sl.png" alt="codigo37">
</p>

Inserção, para essa coleção, de 1.000 documentos através do comando [for].

</p>
<p align="center">
    <img src="https://imgur.com/hZRRsHA.png" alt="codigo38">
</p>

Distribuição da coleção criada.

</p>
<p align="center">
    <img src="https://imgur.com/VuzMJXI.png" alt="codigo39">
</p>

# Storage Engines

Criação e conexão de uma instância do MongoDB que use o storage engine mmapv1.

</p>
<p align="center">
    <img src="https://imgur.com/PiazgYF.png" alt="codigo40">
</p>

</p>
<p align="center">
    <img src="https://imgur.com/4fVDiiX.png" alt="codigo41">
</p>


Criação de uma coleção “RB_produtos” e inserção de 4 documentos.

</p>
<p align="center">
    <img src="https://imgur.com/oy5HRNJ.png" alt="codigo43">
</p>

Criação e conexão de uma instância do MongoDB que usa o storage engine wiredTiger.

</p>
<p align="center">
    <img src="https://imgur.com/YOzMrGu.png" alt="codigo44">
</p>

Criação de uma coleção “RB_lugares” e inserção de 4 documentos.

</p>
<p align="center">
    <img src="https://imgur.com/XM2WP4a.png" alt="codigo45">
</p>

Criação e conexão de uma instância do MongoDB que use segurança (autenticação e autorização).

</p>
<p align="center">
    <img src="https://imgur.com/qOMhpql.png" alt="codigo46">
</p>

</p>
<p align="center">
    <img src="https://imgur.com/HUff7oQ.png" alt="codigo47">
</p>

Criarção de um usuário dba com a role root.

</p>
<p align="center">
    <img src="https://imgur.com/uXzNdOD.png" alt="codigo48">
</p>

Criação de um usuário “RB_desenv” com a role readWrite no database “RB_rh”.

</p>
<p align="center">
    <img src="https://imgur.com/75xnc4e.png" alt="codigo49">
</p>

#  Depuração, Backup/Restore
