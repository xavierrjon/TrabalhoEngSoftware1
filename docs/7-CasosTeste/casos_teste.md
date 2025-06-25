# Casos de Testes com Classes de Equivalências

Os casos de teste foram definidos com base na técnica de partição em classes de equivalência, aplicada às funcionalidades do sistema. O objetivo é garantir uma cobertura eficiente dos testes, validando comportamentos esperados tanto para entradas válidas quanto inválidas. Cada caso de teste foi elaborado considerando critérios de aceitação e regras de negócio específicas, buscando assegurar a qualidade e a robustez do produto.

## Tabelas de Classes de Equivalência

---

### H4 - Cadastro de alimento com validade

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Nome do alimento       | Texto com letras, acentos, hífen (1)         | Vazio, apenas números ou símbolos  (2)       |
| Tipo de alimento       | Categoria existente (3)                     | Valor vazio ou inválido  (4)              |
| Data de validade       | Data igual ou posterior à atual (5)         | Data anterior à data atual    (6)             |

---

###  H7 - Cadastro de dica

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Texto da dica          | Até 300 caracteres (1)                    | Mais de 300 caracteres (2)|
| Fonte da dica          | Fonte confiável e registrada (3)            | Fonte ausente ou não verificada (4)          |

---

###  H8 - Acessibilidade sonora

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Volume do dispositivo  | Ativo  (1)                                 | Desativado sem mensagem de aviso (2)          |
| Voz utilizada          | Personalizável pelo usuário (3)          | Fixa e sem opção de ajuste (4)              |
| Legenda alternativa    | Presente e sincronizada (5)               | Ausente ou não funcional (6)                  |

---

### H9 - FAQ e feedback

| Condição de Entrada          | Classes Válidas                            | Classes Inválidas                              |
|-----------------------------|--------------------------------------------|------------------------------------------------|
| Categoria de pergunta       | Cadastro, Backup, Alertas, Acessibilidade (1)  | Categoria inexistente ou vazia (2)                |
| Feedback do usuário         | "Essa resposta foi útil?" → Sim, Não  (3)   | Qualquer outro valor ou campo vazio (4)            |
| Identificação do feedback   | Feedback anônimo (5)                         | Feedback com nome, ID, e-mail do usuário (6)      |
| Leitura por voz ativada     | Botão visível no canto superior (7)          | Botão ausente, escondido ou fora da área visível (8) |

---

### H12 - Configurar alertas

| Condição de Entrada         | Classes Válidas                          | Classes Inválidas                              |
|----------------------------|------------------------------------------|------------------------------------------------|
| Dias de antecedência       | Entre 1 e 30 dias  (1)                    | 0 dias, negativo ou acima de 30 (2)              |
| Status do alimento         | Ativo (3)                                    | Inativo, vencido, em recall  (4)                  |

---

###  H14 - Segurança e privacidade

| Condição de Entrada     | Classes Válidas                    | Classes Inválidas                             |
|------------------------|------------------------------------|-----------------------------------------------|
| Nível de gravidade     | Crítico, Alto, Médio, Baixo(1)        | Fora do escopo (ex: "muito crítico")(2)          |
| Dados sensíveis        | Criptografados com AES-256(3)         | Não criptografados ou com algoritmo inseguro(4)  |

---

###  H18 - Filtragem e ordenação de alimentos

| Condição de Entrada           | Classes Válidas                                       | Classes Inválidas                              |
|------------------------------|-------------------------------------------------------|------------------------------------------------|
| Filtro aplicado              | Vencidos, Próximos do vencimento, Todos (1)             | Filtro inexistente, inválido ou vazio(2)          |
| Ordenação da lista           | Nome, Local, Vencimento, Manual(3)                      | Ordenações não suportadas (ex: tipo, ID)(4)       |
| Botão "Meus Alimentos"       | Visível e funcional(5)                                  | Ausente ou com erro de navegação(6)               |
| Confirmação de edição/exclusão | Clique em "Confirmar" ou "Sim"(7)                     | Nenhuma resposta ou clique em "Cancelar"(8)      |

---

### H19 - Compartilhamento de dicas

| Condição de Entrada            | Classes Válidas                      | Classes Inválidas                                |
|-------------------------------|--------------------------------------|--------------------------------------------------|
| Texto da dica                 | Verificado e sem links perigosos(1)   | Contém links falsos ou maliciosos (2)             |
| Quantidade por compartilhamento | Uma dica por vez(3)                   | Múltiplas dicas no mesmo envio  (4)                |

---

###  H20 - Cadastro rápido de alimento

| Condição de Entrada   | Classes Válidas                                       | Classes Inválidas                                     |
|----------------------|-------------------------------------------------------|-------------------------------------------------------|
| Nome do alimento     | Até 20 caracteres, com letras, acentos, espaços, hífens(1) | Acima de 20 caracteres ou com símbolos inválidos(2)     |
| Data de validade     | Igual ou posterior à data atual(3)                       | Vencida(4)                                               |
| Duplicidade          | Alimento único(5)                                        | Já existente na lista(6)                                 |

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

---

###  H22 - Controle de quantidade de alimento

| Condição de Entrada         | Classes Válidas                  | Classes Inválidas                               |
|----------------------------|----------------------------------|-------------------------------------------------|
| Quantidade de alimento     | Abaixo do limite (1–10) (1)          | Negativa, 0 ou acima do limite sem configuração(2) |
| Status do alimento         | Ativo(3)                            | Inativo, expirado ou em recall(4)                  |
