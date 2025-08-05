# Banco-de-Dados1
### Banco de Dados-Relacional
É um sistema de organização de um banco ,onde, ele oraganiza uma tabela em colunas e linhas e faz um relacionamento entre as mesmas. E isso facilita na recuperaçao de dados 
#### Exemplos de Uso
1. **Gerenciamento de pedidos**: Rastrear pedidos, produtos e clientes.
2. **Sistemas financeiros**: Controlar transações, contas e saldos.
3. **Sistemas de gestão de estoque**: Monitorar produtos, quantidades e movimentações.
4. **Sistemas de gerenciamento de relacionamento com clientes (CRM)**: Armazenar informações sobre clientes e interações.

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTLN-MhXT7kbN-csJzfC67OlQaA1MLH66M9cQ&s">

---

### Banco de Dados- Não Relacional
 É um tipo de sistema de gerenciamento de banco de dados que não usa o modelo tradicional de tabelas com linhas e colunas (como em bancos de dados relacionais). Em vez disso, ele oferece flexibilidade para armazenar e gerenciar dados de diversas formas, como documentos, grafos, ou pares chave-valor. Essa abordagem permite lidar com grandes volumes de dados não estruturados ou semiestruturados, como os encontrados em redes sociais, dados de sensores ou análise de texto. 
#### Exemplos de Uso
1. **Armazenamento de perfis de usuários em redes sociais**:
Bancos de dados não relacionais podem armazenar perfis de usuários com informações variadas, como fotos, vídeos, e interações, de forma flexível, sem a necessidade de definir esquemas rígidos como em bancos de dados relacionais. 
3.  **Análise de dados de sensores**:
Em aplicações de Internet das Coisas (IoT), onde dispositivos enviam dados constantemente, os bancos de dados não relacionais podem armazenar esses dados de forma eficiente e escalável, permitindo análises em tempo real. 
5. **Recomendação de conteúdo**:
Plataformas de streaming podem utilizar bancos de dados não relacionais para armazenar histórico de visualizações e preferências dos usuários, permitindo recomendações personalizadas de conteúdo. 
6. **Big Data e análises complexas**:
Bancos de dados não relacionais são ideais para lidar com grandes volumes de dados não estruturados, facilitando análises complexas e descobertas de padrões. 
7. **Aplicações de jogos**:
Bancos de dados não relacionais podem ser usados para armazenar dados de jogos, como pontuações, personagens, e inventários, de forma flexível e escalável.
---

### Normalização
Normalização é o processo de organização de dados em um banco de dados. Isso inclui a criação de tabelas e o estabelecimento de relações entre essas tabelas de acordo com as regras projetadas para proteger os dados e tornar o banco de dados mais flexível, eliminando a redundância e a dependência inconsistente. E como descrito o objetivo da Normalizaçaõ é a maior proteção de dados e ter dados mais flexíveis.

---

### Tabela Não Normalizada

| Id da pescaria  | Nome do pescador | Peixe  | Peso | Valor do Equipamento |
|-----------------|------------------|--------|------|----------------------|
|       101       | Cauã José        |Tucunaré| 9kg  |     R$1000,00        |
|       102       | Rubens Cestari   | Pintado| 20kg |     R$800,00         |
|       103       | Dolores Duarte   |Tucunaré| 5kg  |     R$200,00         |
|       104       | Juliano Rocha    | Piau   | 2kg  |     R$200,00         |
|       105       | Amanda Cestari   | Mandi  | 40kg |     R$700,00         |
|       106       | Victor Hugo      | Traíra | 1kg  |     R$100,00         |
|       107       | Paula Duarte     |Pirarara| 30kg |     R$900,00         |
|       108       | Cauã José        |Tucunaré| 9kg  |     R$900,00         |

---
### Primeira Forma(1FN)
A tabela ja está em 1FN pois cada célula contém seu próprio valor, e cada linha tem sua chave primária

**Tabela 1**

| Id da pescaria  | Nome do pescador | Peixe  | Peso | Valor do Equipamento |
|-----------------|------------------|--------|------|----------------------|
|       101       | Cauã José        |Tucunaré| 9kg  |     R$1000,00        |
|       102       | Rubens Cestari   | Pintado| 20kg |     R$800,00         |
|       103       | Dolores Duarte   |Tucunaré| 5kg  |     R$200,00         |
|       104       | Juliano Rocha    | Piau   | 2kg  |     R$200,00         |
|       105       | Amanda Cestari   | Mandi  | 40kg |     R$700,00         |
|       106       | Victor Hugo      | Traíra | 1kg  |     R$100,00         |
|       107       | Paula Duarte     |Pirarara| 30kg |     R$900,00         |
|       108       | Cauã José        |Tucunaré| 9kg  |     R$900,00         |

---
### Segunda Forma(2FN)
Para estar na 2FN, todas as colunas que não são a chave primária devem depender da chave primária completa 

#### Vamos analizar as colunas:
1. **Nome do pescador**: Não depende de nenhuma das informações, somente de si mesmo
2. **Peixe**: Mesma coisa, essa informação é sobre o tipo do peixe
3. **Peso**: Isso sim depende de outra informação, pois o peso vai de cada peixe!!
4. **Valor do equipamento**: Este valor esta associado ao pescador, pois quem irá comprar será ele.
#### Para resolver isso, vamos criar novas tabelas para agrupar as informações que não dependem diretamente do Id da pescaria.

#### Tabela de Pescadores:
1. ID_Pescador (Chave Primária)
2. Nome_Pescador
3. Valor_do_Equipamento

**Observação**: Perceba que criamos um ID para cada pescador. Isso evita problemas, por exemplo, se dois pescadores diferentes se chamarem "Cauã José".

#### Tabela de Peixes:
1. ID_Peixe (Chave Primária)
2. Nome_Peixe

**Observação**: O nome do peixe é o que o identifica, mas é melhor usar um ID para evitar erros de digitação e facilitar as referências.

#### Tabela de Pescarias:
1. ID_Pescaria (Chave Primária)
2. ID_Pescador (Chave Estrangeira)
3. ID_Peixe (Chave Estrangeira)

**Observação**: Agora, o Id da pescaria se relaciona com o pescador e o peixe usando as chaves estrangeiras.

#### Chave Primária
A chave primária é um campo (ou um conjunto de campos) que identifica de forma única cada registro (linha) em uma tabela. Ela é essencial para garantir a integridade dos dados e evitar duplicatas. Pense nela como o CPF de uma pessoa: cada CPF é único e identifica uma única pessoa.

#### Chave Estrangeira
A chave estrangeira é um campo (ou um conjunto de campos) em uma tabela que faz referência à chave primária de outra tabela. Sua principal função é estabelecer um relacionamento entre as tabelas. Ela garante a "integridade referencial", ou seja, que você não insira dados em uma tabela que não tenham um correspondente na tabela original.

**Tabela 2**:
| Id Peixe  | Peixe  | 
|-----------|--------|
|    101    |Tucunaré|
|    102    | Pintado|
|    103    | Piau   |
|    104    | Mandi  |
|    105    | Traíra |
|    106    |Pirarara|

---
### Terceira Forma(3FN)
Para estar na 3FN, não pode haver dependências transitivas. Ou seja, nenhuma coluna que não seja a chave primária pode depender de outra coluna que também não seja a chave primária.

**Tabela 3**
| Id da pescaria  | Id do Pescador | ID Peixe  | Peso    | 
|-----------------|----------------|-----------|---------|
|       101       |        1       |      1    |   9kg   | 
|       102       |        2       |      2    |   20kg  |
|       103       |        3       |      1    |   5kg   | 
|       104       |        4       |      3    |   2kg   | 
|       105       |        5       |      4    |   40kg  |   
|       106       |        6       |      5    |   1kg   | 
|       107       |        7       |      6    |   30kg  | 
|       108       |        1       |      1    |   9kg   |

---
### Json 
```
{
  "pescarias": [
    {
      "id_pescaria": 101,
      "pescador": {
        "nome": "Cauã José"
      },
      "peixe": {
        "nome": "Tucunaré",
        "peso_kg": 9
      },
      "equipamento": {
        "valor_reais": 1000.00
      }
    },
    {
      "id_pescaria": 102,
      "pescador": {
        "nome": "Rubens Cestari"
      },
      "peixe": {
        "nome": "Pintado",
        "peso_kg": 20
      },
      "equipamento": {
        "valor_reais": 800.00
      }
    },
    {
      "id_pescaria": 103,
      "pescador": {
        "nome": "Dolores Duarte"
      },
      "peixe": {
        "nome": "Tucunaré",
        "peso_kg": 5
      },
      "equipamento": {
        "valor_reais": 200.00
      }
    },
    {
      "id_pescaria": 104,
      "pescador": {
        "nome": "Juliano Rocha"
      },
      "peixe": {
        "nome": "Piau",
        "peso_kg": 2
      },
      "equipamento": {
        "valor_reais": 200.00
      }
    },
    {
      "id_pescaria": 105,
      "pescador": {
        "nome": "Amanda Cestari"
      },
      "peixe": {
        "nome": "Mandi",
        "peso_kg": 40
      },
      "equipamento": {
        "valor_reais": 700.00
      }
    },
    {
      "id_pescaria": 106,
      "pescador": {
        "nome": "Victor Hugo"
      },
      "peixe": {
        "nome": "Traíra",
        "peso_kg": 1
      },
      "equipamento": {
        "valor_reais": 100.00
      }
    },
    {
      "id_pescaria": 107,
      "pescador": {
        "nome": "Paula Duarte"
      },
      "peixe": {
        "nome": "Pirarara",
        "peso_kg": 30
      },
      "equipamento": {
        "valor_reais": 900.00
      }
    },
    {
      "id_pescaria": 108,
      "pescador": {
        "nome": "Cauã José"
      },
      "peixe": {
        "nome": "Tucunaré",
        "peso_kg": 9
      },
      "equipamento": {
        "valor_reais": 900.00
      }
    }
  ]
}
```
### Por que a normalização não é necessária aqui?
Nessa estrutura, não precisa de normalização porque ela foi pensada para ser um documento completo e autossuficiente.
