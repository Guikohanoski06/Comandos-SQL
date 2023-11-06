## Comandos de banco de dados

### Criar database
* Local para a gente criar as tabelas do sistema
* Nome do app é workbench
```
create database NOME_DATABASE;
```
### Executar o comando

```
Ctrl + enter
```

### Selecionar database
```
use NOME_DATABASE;
```
<hr>

## Projeto site Ecommerce
* Tabela de usuarios
* Tabela de produtos 
* Tabela de carrinho de compras

### Criar tabela de usuários 

* Sempre colocar virgula no final, menos na última linha
```
create table usuarios(
    id int nto null auto_increment,
    nome varchar(120) not null,
    email varchar(120) not null,
    senha varchar(120) not null,
    primary key(id)
);
```

* id = identificador de cada registro
* not null = campo obrigatório, não pode ser nulo
* auto_increment = soma +1 no último registro de id 
* varchar(120) = campo de texto com 120 caracteres

### Criar tabela de produtos 
```
create yable produtos(
    id int not null auto_increment
    modelo varchar(120)
    nome varchar(120)not null,
    valor float not null,
    primary key(id)
);
```

###Criar tabela de carrinho 

```
create table carrinho (
    id int not null auto_increment,
    id_usuario int not null,
    id_produto int not null,
    primary key(id),
    foreign key(id_usuario) references usuarios(id),
    foreign key(id_produtos) references produtos(id)
)
```
* foreign key = Chave estrangeiro que recebe a referencia de oputra tabela
* references = indica qual chave estrangeira vai se conectar

### Inserir dados 
```
insert into usuarios(nome, email, senha) values('Renato Gaúcho', 'teste@teste.com', 'secret')
```

### Inserir produti 
```
insert into produtos(modelo, nome, valor) values('nike', 'camisa', '129.90')
```

### inserir carrinho
```
insert into carrinho(id_usuario, id_produto) values(43, 234);
insert into carrinho(id_usuario, id_produto) values(43, 120);
insert into carrinho(id_usuario, id_produto) values(43, 6);
insert into carrinho(id_usuario, id_produto) values(43, 234);
insert into carrinho(id_usuario, id_produto) values(43, 234);
```

### Listar todos os usuarios

```
select * from usuarios;
```
### Listar nome dos usuarios

```
select nome from usuarios;
```

### Listar nomes e emails dos usuarios

```
select nome, email from usuarios;
```

### Listar usuarios pelo id

```
select * from usuario where id = 23; 
```