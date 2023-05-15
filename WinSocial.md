# Processo Seletivo WinSocial - Arquiteto(a) de Sistemas

## Recrutando candidatos

A empresa LeadScore tem uma equipe de agentes de venda e recebe milhares de leads por dia. A empresa precisa entender qual deles Ã© o mais indicado para recebÃª-los.

Seu papel aqui Ã© ajudar o gerente de vendas indicando qual o vendedor com maior score. Calculamos o score de um vendedor cruzando o nÃºmero de horas Ãºteis (seg-sex 9am-6pm) sem receber um lead com a sua senioridade.

**ConsideraÃ§Ãµes gerais:**


CÃ¡culo do score:

`SCORE = NH * MT` onde:

* **NH** Ã© o nÃºmero de horas Ãºteis desde o Ãºltimo recebimento de um lead
* **MT** Ã© o multiplicador associado Ã  senioridade do vendedor

NÃ­veis de senioridade:

* **1**: jÃºnior
* **2**: pleno
* **3**: sÃªnior

Para definir o nÃºmero mÃ¡ximo de leads recebidos usamos a tabela abaixo:

|NÃ­vel do Vendedor|Multiplicador|
|-|-|
|JÃºnior|1|
|Pleno|1.5|
|SÃªnior|2|

Exemplo: 

O `SCORE` de um vendedor `Pleno` que nÃ£o recebe um lead hÃ¡ `3 horas` serÃ¡ de `4.5`. Por outro lado, um sÃªnior que nÃ£o recebe um lead hÃ¡ `2.5 horas` terÃ¡ um `SCORE` de `5`. Ou seja, o vendedor sÃªnior receberia o lead por ter um `SCORE` mais alto.

### EspecificaÃ§Ãµes da API

#### Endpoints

##### 1. Criar um endpoint para cadastrar agentes com seus nomes e nÃ­veis de senioridade

Todo o desenho do endpoint (uri/verbo/request/response) para esta funÃ§Ã£o serÃ¡ definido por vocÃª e **faz parte da avaliaÃ§Ã£o**.

##### 2. Criar um endpoint para cadastrar leads com nome e telefone

Todo o desenho do endpoint para esta funÃ§Ã£o serÃ¡ definido por vocÃª e **faz parte da avaliaÃ§Ã£o**.

##### 3. Criar um endpoint para retornar os agentes mais qualificados para um lead especÃ­fico (ordenados pelo score de forma decrescente).

Todo o desenho do endpoint para esta funÃ§Ã£o serÃ¡ definido por vocÃª e **faz parte da avaliaÃ§Ã£o**.

**Response:**

```json
[
    {
        "nome": "Vendedor Mary Jane",
        "nivel": 3,
        "ultimo_lead_recebido": "2020-11-19 09:22:11",
        "score": 36
	},
    {
        "nome": "Vendedor John Doe",
        "nivel": 1,
        "ultimo_lead_recebido": "2020-11-20 11:23:22",
        "score": 18	
    },
    ...
]
```
