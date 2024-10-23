# Desafio 3 - Criando um Dashboard corporativo com integração com MySQL e Azure
   
## Consulta SQL

Código criado para junção dos colaboradores e respectivos nomes dos gerentes.

```SQL
select concat(b.fname, ' ', b.minit, ' ',b.lname) as Gerente, concat(a.fname, ' ', a.minit, ' ',a.lname) as Colaborador 
from Employee as a left join Employee as b 
on a.super_ssn = b.ssn;
```

## Telas 

![relacionamentos](https://github.com/user-attachments/assets/65244834-2ac5-4028-a835-6ac86b0ed345)


## Diferença entre Mesclar e Acrescentar

 Mesclar Consultas realiza a junção das tabelas, criando uma nova coluna com as informações desejadas da segunda tabela

Já se tratando do Acrescentar Consultas, ele realiza a união dados das duas tabelas, acrescentando linhas à tabela.

#### Exemplo 

![mesclar_consultas](https://github.com/user-attachments/assets/cb8082b9-1e09-426b-84e8-894bc1a8dd4f)

![acrescentar_consultas](https://github.com/user-attachments/assets/c14504fa-bc2f-48aa-90d9-78c02cbe1766)



