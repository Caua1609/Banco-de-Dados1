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
