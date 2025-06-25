# Casos de Testes com Classes de Equivalências

Os casos de teste foram definidos com base na técnica de partição em classes de equivalência, aplicada às funcionalidades do sistema. O objetivo é garantir uma cobertura eficiente dos testes, validando comportamentos esperados tanto para entradas válidas quanto inválidas. Cada caso de teste foi elaborado considerando critérios de aceitação e regras de negócio específicas, buscando assegurar a qualidade e a robustez do produto.

---

### H4 - Cadastro de alimento com validade

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Nome do alimento       | Texto com letras, acentos, hífen (1)         | Vazio, apenas números ou símbolos  (2)       |
| Tipo de alimento       | Categoria existente (3)                     | Valor vazio ou inválido  (4)              |
| Data de validade       | Data igual ou posterior à atual (5)         | Data anterior à data atual    (6)             |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                              | Resultado Esperado |
| ------------- | ----------------------- | ----------------------------------------------------- | ------------------ |
| Caso 1        | 1, 3, 5                 | Nome: Arroz<br>Tipo: Grão<br>Validade: 2025-01-01     | Válido             |
| Caso 2        | 2, 3, 5                 | Nome: 12345<br>Tipo: Grão<br>Validade: 2025-01-01     | Inválido           |
| Caso 3        | 1, 4, 5                 | Nome: Feijão<br>Tipo: ""<br>Validade: 2025-01-01      | Inválido           |
| Caso 4        | 1, 3, 6                 | Nome: Carne<br>Tipo: Proteína<br>Validade: 2020-01-01 | Inválido           |

Classe Vàlida: 1, 3, 5

Classe Inválida:
- 2, 3, 5
- 1, 4, 6
- 1, 3, 6

---

###  H7 - Cadastro de dica

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Texto da dica          | Até 300 caracteres (1)                    | Mais de 300 caracteres (2)|
| Fonte da dica          | Fonte confiável e registrada (3)            | Fonte ausente ou não verificada (4)          |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                       | Resultado Esperado |
| ------------- | ----------------------- | ---------------------------------------------- | ------------------ |
| Caso 1        | 1, 2                    | Texto: Beba água<br>Fonte: Ministério da Saúde | Válido             |
| Caso 2        | 3, 2                    | Texto com 301 caracteres<br>Fonte: Fiocruz     | Inválido           |
| Caso 3        | 1, 4                    | Texto: Coma frutas<br>Fonte: ""                | Inválido           |

Classe Vàlida: 1, 2

Classe Inválida:
- 3, 2
- 1, 4

---

###  H8 - Acessibilidade sonora

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Volume do dispositivo  | Ativo  (1)                                 | Desativado sem mensagem de aviso (2)          |
| Voz utilizada          | Personalizável pelo usuário (3)          | Fixa e sem opção de ajuste (4)              |
| Legenda alternativa    | Presente e sincronizada (5)               | Ausente ou não funcional (6)                  |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                                       | Resultado Esperado |
| ------------- | ----------------------- | -------------------------------------------------------------- | ------------------ |
| Caso 1        | 1, 2, 3                 | Volume: Ativo<br>Voz: Personalizável<br>Legenda: Presente      | Válido             |
| Caso 2        | 4, 2, 3                 | Volume: Desativado<br>Voz: Personalizável<br>Legenda: Presente | Inválido           |
| Caso 3        | 1, 5, 3                 | Volume: Ativo<br>Voz: Fixa<br>Legenda: Presente                | Inválido           |
| Caso 4        | 1, 2, 6                 | Volume: Ativo<br>Voz: Personalizável<br>Legenda: Ausente       | Inválido           |

Classe Vàlida: 1, 2, 3

Classe Inválida:
- 4, 2, 3
- 1, 5, 3
- 1, 2, 6

---

### H9 - FAQ e feedback

| Condição de Entrada          | Classes Válidas                            | Classes Inválidas                              |
|-----------------------------|--------------------------------------------|------------------------------------------------|
| Categoria de pergunta       | Cadastro, Backup, Alertas, Acessibilidade (1)  | Categoria inexistente ou vazia (2)                |
| Feedback do usuário         | "Essa resposta foi útil?" → Sim, Não  (3)   | Qualquer outro valor ou campo vazio (4)            |
| Identificação do feedback   | Feedback anônimo (5)                         | Feedback com nome, ID, e-mail do usuário (6)      |
| Leitura por voz ativada     | Botão visível no canto superior (7)          | Botão ausente, escondido ou fora da área visível (8) |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                                                                              | Resultado Esperado |
| ------------- | ----------------------- | ----------------------------------------------------------------------------------------------------- | ------------------ |
| Caso 1        | 1, 2, 3, 4              | Categoria: Acessibilidade<br>Feedback: Sim<br>ID: Anônimo<br>Botão: Visível                           | Válido             |
| Caso 2        | 5, 2, 3, 4              | Categoria: ""<br>Feedback: Sim<br>ID: Anônimo<br>Botão: Visível                                       | Inválido           |
| Caso 3        | 1, 6, 3, 4              | Categoria: Backup<br>Feedback: Talvez<br>ID: Anônimo<br>Botão: Visível                                | Inválido           |
| Caso 4        | 1, 2, 7, 4              | Categoria: Cadastro<br>Feedback: Sim<br>ID: [joao@email.com](mailto:joao@email.com)<br>Botão: Visível | Inválido           |
| Caso 5        | 1, 2, 3, 8              | Categoria: Cadastro<br>Feedback: Sim<br>ID: Anônimo<br>Botão: Ausente                                 | Inválido           |

Classe Vàlida: 1, 2, 3, 4

Classe Inválida:
- 5, 2, 3, 4
- 1, 6, 3, 4
- 1, 2, 7, 4
- 1, 2, 3, 8

---

### H12 - Configurar alertas

| Condição de Entrada         | Classes Válidas                          | Classes Inválidas                              |
|----------------------------|------------------------------------------|------------------------------------------------|
| Dias de antecedência       | Entre 1 e 30 dias  (1)                    | 0 dias, negativo ou acima de 30 (2)              |
| Status do alimento         | Ativo (3)                                    | Inativo, vencido, em recall  (4)                  |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                    | Resultado Esperado |
| ------------- | ----------------------- | --------------------------- | ------------------ |
| Caso 1        | 1, 3                    | Dias: 10<br>Status: Ativo   | Válido             |
| Caso 2        | 2, 3                    | Dias: -1<br>Status: Ativo   | Inválido           |
| Caso 3        | 1, 4                    | Dias: 15<br>Status: Vencido | Inválido           |

Classe Vàlida: 1, 3

Classe Inválida:
- 2, 3
- 1, 4 

---

###  H14 - Segurança e privacidade

| Condição de Entrada     | Classes Válidas                    | Classes Inválidas                             |
|------------------------|------------------------------------|-----------------------------------------------|
| Nível de gravidade     | Crítico, Alto, Médio, Baixo(1)        | Fora do escopo (ex: "muito crítico")(2)          |
| Dados sensíveis        | Criptografados com AES-256(3)         | Não criptografados ou com algoritmo inseguro(4)  |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                          | Resultado Esperado |
| ------------- | ----------------------- | ------------------------------------------------- | ------------------ |
| Caso 1        | 1, 3                    | Gravidade: Alto<br>Criptografia: AES-256          | Válido             |
| Caso 2        | 2, 3                    | Gravidade: Muito crítico<br>Criptografia: AES-256 | Inválido           |
| Caso 3        | 1, 4                    | Gravidade: Médio<br>Criptografia: Base64          | Inválido           |

Classe Vàlida: 1, 3

Classe Inválida:
- 2, 3
- 1, 4 

---

###  H18 - Filtragem e ordenação de alimentos

| Condição de Entrada           | Classes Válidas                                       | Classes Inválidas                              |
|------------------------------|-------------------------------------------------------|------------------------------------------------|
| Filtro aplicado              | Vencidos, Próximos do vencimento, Todos (1)             | Filtro inexistente, inválido ou vazio(2)          |
| Ordenação da lista           | Nome, Local, Vencimento, Manual(3)                      | Ordenações não suportadas (ex: tipo, ID)(4)       |
| Botão "Meus Alimentos"       | Visível e funcional(5)                                  | Ausente ou com erro de navegação(6)               |
| Confirmação de edição/exclusão | Clique em "Confirmar" ou "Sim"(7)                     | Nenhuma resposta ou clique em "Cancelar"(8)      |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                                                         | Resultado Esperado |
| ------------- | ----------------------- | -------------------------------------------------------------------------------- | ------------------ |
| Caso 1        | 1, 3, 5, 7              | Filtro: Vencidos<br>Ordenação: Nome<br>Botão: Visível<br>Confirmação: Confirmar  | Válido             |
| Caso 2        | 2, 3, 5, 7              | Filtro: Tipo<br>Ordenação: Nome<br>Botão: Visível<br>Confirmação: Confirmar      | Inválido           |
| Caso 3        | 1, 4, 5, 7              | Filtro: Todos<br>Ordenação: ID<br>Botão: Visível<br>Confirmação: Confirmar       | Inválido           |
| Caso 4        | 1, 3, 6, 7              | Filtro: Próximos<br>Ordenação: Local<br>Botão: Ausente<br>Confirmação: Confirmar | Inválido           |
| Caso 5        | 1, 3, 5, 8              | Filtro: Todos<br>Ordenação: Manual<br>Botão: Visível<br>Confirmação: Cancelar    | Inválido           |

Classe Vàlida: 1, 3, 5, 7

Classe Inválida:
- 2, 3, 5, 7
- 1, 4, 5, 7
- 1, 3, 6, 7
- 1, 3, 5, 8

---


### H19 - Compartilhamento de dicas

| Condição de Entrada            | Classes Válidas                      | Classes Inválidas                                |
|-------------------------------|--------------------------------------|--------------------------------------------------|
| Texto da dica                 | Verificado e sem links perigosos(1)   | Contém links falsos ou maliciosos (2)             |
| Quantidade por compartilhamento | Uma dica por vez(3)                   | Múltiplas dicas no mesmo envio  (4)                |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                      | Resultado Esperado |
| ------------- | ----------------------- | --------------------------------------------- | ------------------ |
| Caso 1        | 1, 3                    | Texto: verificado<br>Quantidade: 1            | Válido             |
| Caso 2        | 2, 3                    | Texto: contém link malicioso<br>Quantidade: 1 | Inválido           |
| Caso 3        | 1, 4                    | Texto: verificado<br>Quantidade: 2            | Inválido           |

Classe Vàlida: 1, 3

Classe Inválida:
- 2, 3
- 1, 4 

---

###  H20 - Cadastro rápido de alimento

| Condição de Entrada   | Classes Válidas                                       | Classes Inválidas                                     |
|----------------------|-------------------------------------------------------|-------------------------------------------------------|
| Nome do alimento     | Até 20 caracteres, com letras, acentos, espaços, hífens(1) | Acima de 20 caracteres ou com símbolos inválidos(2)     |
| Data de validade     | Igual ou posterior à data atual(3)                       | Vencida(4)                                               |
| Duplicidade          | Alimento único(5)                                        | Já existente na lista(6)                                 |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                                                     | Resultado Esperado |
| ------------- | ----------------------- | ---------------------------------------------------------------------------- | ------------------ |
| Caso 1        | 1, 3, 5                 | Nome: Feijão<br>Validade: 2026-01-01<br>Duplicidade: Não existe              | Válido             |
| Caso 2        | 2, 3, 5                 | Nome: Farofa!!! com bacon<br>Validade: 2026-01-01<br>Duplicidade: Não existe | Inválido           |
| Caso 3        | 1, 4, 5                 | Nome: Arroz<br>Validade: 2020-01-01<br>Duplicidade: Não existe               | Inválido           |
| Caso 4        | 1, 3, 6                 | Nome: Arroz<br>Validade: 2026-01-01<br>Duplicidade: Já existe                | Inválido           |

Classe Vàlida: 1, 3, 5

Classe Inválida:
- 2, 3, 5
- 1, 4, 5
- 1, 3, 6

---

###  H21 - Etiquetas e classificações

| Condição de Entrada         | Classes Válidas                                | Classes Inválidas                                      |
|----------------------------|--------------------------------------------------|--------------------------------------------------------|
| Nome da etiqueta           | Até 20 caracteres, sem símbolos especiais(1)       | Acima de 20 ou caracteres inválidos(2)                    |
| Quantidade de etiquetas    | Até 10 por usuário(3)                              | Mais de 10 etiquetas criadas(4)                           |
| Status para "Descartado"   | Vencido ou sem data(5)                             | Válido e com data futura(6)                               |
| Classificação ativa        | Uma por alimento(7)                                | Múltiplas ativas ao mesmo tempo(8)                      |
| Quantidade de alimento     | Abaixo do limite (1–10) (9)                         | Negativa, 0 ou acima do limite sem configuração (10)        |
| Status do alimento         | Ativo (11)                                         | Inativo, expirado ou em recall(12)                         |

###Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                                                                                             | Resultado Esperado |
| ------------- | ----------------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------ |
| Caso 1        | 1, 3, 5, 7, 9, 11       | Nome: Promoção<br>Qtd etiquetas: 5<br>Status: Vencido<br>Classificação: Única<br>Qtd alimento: 5<br>Status: Ativo    | Válido             |
| Caso 2        | 2, 3, 5, 7, 9, 11       | Nome: Promoção!!!<br>Qtd etiquetas: 5<br>Status: Vencido<br>Classificação: Única<br>Qtd alimento: 5<br>Status: Ativo | Inválido           |
| Caso 3        | 1, 4, 5, 7, 9, 11       | Nome: Saudável<br>Qtd etiquetas: 15<br>Status: Vencido<br>Classificação: Única<br>Qtd alimento: 5<br>Status: Ativo   | Inválido           |
| Caso 4        | 1, 3, 6, 7, 9, 11       | Nome: Rápido<br>Qtd etiquetas: 3<br>Status: Válido<br>Classificação: Única<br>Qtd alimento: 5<br>Status: Ativo       | Inválido           |
| Caso 5        | 1, 3, 5, 8, 9, 11       | Nome: Café<br>Qtd etiquetas: 3<br>Status: Vencido<br>Classificação: Múltiplas<br>Qtd alimento: 5<br>Status: Ativo    | Inválido           |
| Caso 6        | 1, 3, 5, 7, 10, 11      | Nome: Café<br>Qtd etiquetas: 3<br>Status: Vencido<br>Classificação: Única<br>Qtd alimento: 0<br>Status: Ativo        | Inválido           |
| Caso 7        | 1, 3, 5, 7, 9, 12       | Nome: Café<br>Qtd etiquetas: 3<br>Status: Vencido<br>Classificação: Única<br>Qtd alimento: 3<br>Status: Expirado     | Inválido           |

Classe Vàlida: 1, 3, 5

Classe Inválida:
- 1, 3, 5, 7, 9, 11
- 2, 3, 5, 7, 9, 11
- 1, 4, 5, 7, 9, 11
- 1, 3, 6, 7, 9, 11
- 1, 3, 5, 8, 9, 11
- 1, 3, 5, 7, 10, 11
- 1, 3, 5, 7, 9, 12

---

###  H22 - Controle de quantidade de alimento

| Condição de Entrada         | Classes Válidas                  | Classes Inválidas                               |
|----------------------------|----------------------------------|-------------------------------------------------|
| Quantidade de alimento     | Abaixo do limite (1–10) (1)          | Negativa, 0 ou acima do limite sem configuração(2) |
| Status do alimento         | Ativo(3)                            | Inativo, expirado ou em recall(4)                  |

###Casos de teste

| Caso de Teste | Classes de Equivalência | Entradas                           | Resultado Esperado |
| ------------- | ----------------------- | ---------------------------------- | ------------------ |
| Caso 1        | 1, 3                    | Quantidade: 5<br>Status: Ativo     | Válido             |
| Caso 2        | 2, 3                    | Quantidade: -1<br>Status: Ativo    | Inválido           |
| Caso 3        | 2, 3                    | Quantidade: 0<br>Status: Ativo     | Inválido           |
| Caso 4        | 2, 3                    | Quantidade: 12<br>Status: Ativo    | Inválido           |
| Caso 5        | 1, 4                    | Quantidade: 4<br>Status: Inativo   | Inválido           |
| Caso 6        | 1, 4                    | Quantidade: 6<br>Status: Expirado  | Inválido           |
| Caso 7        | 1, 4                    | Quantidade: 7<br>Status: Em Recall | Inválido           |

Classe Vàlida: 1, 3

Classe Inválida:
- 2, 3
- 1, 4 

---
