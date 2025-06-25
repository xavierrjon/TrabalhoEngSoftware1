# Casos de Testes com Classes de Equivalências

Os casos de teste foram definidos com base na técnica de partição em classes de equivalência, aplicada às funcionalidades do sistema. O objetivo é garantir uma cobertura eficiente dos testes, validando comportamentos esperados tanto para entradas válidas quanto inválidas. Cada caso de teste foi elaborado considerando critérios de aceitação e regras de negócio específicas, buscando assegurar a qualidade e a robustez do produto.

## Tabelas de Classes de Equivalência

---

### H4 - Cadastro de alimento com validade

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Nome do alimento       | Texto com letras, acentos, hífen         | Vazio, apenas números ou símbolos          |
| Tipo de alimento       | Categoria existente                      | Valor vazio ou inválido                    |
| Data de validade       | Data igual ou posterior à atual          | Data anterior à data atual                 |

---

###  H7 - Cadastro de dica

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Texto da dica          | Até 300 caracteres                       | Mais de 300 caracteres                     |
| Fonte da dica          | Fonte confiável e registrada             | Fonte ausente ou não verificada            |

---

###  H8 - Acessibilidade sonora

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Volume do dispositivo  | Ativo                                    | Desativado sem mensagem de aviso           |
| Voz utilizada          | Personalizável pelo usuário              | Fixa e sem opção de ajuste                 |
| Legenda alternativa    | Presente e sincronizada                  | Ausente ou não funcional                   |

---

### H9 - FAQ e feedback

| Condição de Entrada          | Classes Válidas                            | Classes Inválidas                              |
|-----------------------------|--------------------------------------------|------------------------------------------------|
| Categoria de pergunta       | Cadastro, Backup, Alertas, Acessibilidade  | Categoria inexistente ou vazia                 |
| Feedback do usuário         | "Essa resposta foi útil?" → Sim, Não       | Qualquer outro valor ou campo vazio            |
| Identificação do feedback   | Feedback anônimo                           | Feedback com nome, ID, e-mail do usuário       |
| Leitura por voz ativada     | Botão visível no canto superior            | Botão ausente, escondido ou fora da área visível |

---

### H12 - Configurar alertas

| Condição de Entrada         | Classes Válidas                          | Classes Inválidas                              |
|----------------------------|------------------------------------------|------------------------------------------------|
| Dias de antecedência       | Entre 1 e 30 dias                        | 0 dias, negativo ou acima de 30                |
| Status do alimento         | Ativo                                    | Inativo, vencido, em recall                    |

---

###  H14 - Segurança e privacidade

| Condição de Entrada     | Classes Válidas                    | Classes Inválidas                             |
|------------------------|------------------------------------|-----------------------------------------------|
| Nível de gravidade     | Crítico, Alto, Médio, Baixo        | Fora do escopo (ex: "muito crítico")          |
| Dados sensíveis        | Criptografados com AES-256         | Não criptografados ou com algoritmo inseguro  |

---

###  H18 - Filtragem e ordenação de alimentos

| Condição de Entrada           | Classes Válidas                                       | Classes Inválidas                              |
|------------------------------|-------------------------------------------------------|------------------------------------------------|
| Filtro aplicado              | Vencidos, Próximos do vencimento, Todos              | Filtro inexistente, inválido ou vazio          |
| Ordenação da lista           | Nome, Local, Vencimento, Manual                      | Ordenações não suportadas (ex: tipo, ID)       |
| Botão "Meus Alimentos"       | Visível e funcional                                  | Ausente ou com erro de navegação               |
| Confirmação de edição/exclusão | Clique em "Confirmar" ou "Sim"                     | Nenhuma resposta ou clique em "Cancelar"       |

---

### H19 - Compartilhamento de dicas

| Condição de Entrada            | Classes Válidas                      | Classes Inválidas                                |
|-------------------------------|--------------------------------------|--------------------------------------------------|
| Texto da dica                 | Verificado e sem links perigosos     | Contém links falsos ou maliciosos               |
| Quantidade por compartilhamento | Uma dica por vez                   | Múltiplas dicas no mesmo envio                  |

---

###  H20 - Cadastro rápido de alimento

| Condição de Entrada   | Classes Válidas                                       | Classes Inválidas                                     |
|----------------------|-------------------------------------------------------|-------------------------------------------------------|
| Nome do alimento     | Até 20 caracteres, com letras, acentos, espaços, hífens | Acima de 20 caracteres ou com símbolos inválidos     |
| Data de validade     | Igual ou posterior à data atual                       | Vencida                                               |
| Duplicidade          | Alimento único                                        | Já existente na lista                                 |

---

###  H21 - Etiquetas e classificações

| Condição de Entrada         | Classes Válidas                                | Classes Inválidas                                      |
|----------------------------|--------------------------------------------------|--------------------------------------------------------|
| Nome da etiqueta           | Até 20 caracteres, sem símbolos especiais       | Acima de 20 ou caracteres inválidos                    |
| Quantidade de etiquetas    | Até 10 por usuário                              | Mais de 10 etiquetas criadas                           |
| Status para "Descartado"   | Vencido ou sem data                             | Válido e com data futura                               |
| Classificação ativa        | Uma por alimento                                | Múltiplas ativas ao mesmo tempo                        |
| Quantidade de alimento     | Abaixo do limite (1–10)                         | Negativa, 0 ou acima do limite sem configuração        |
| Status do alimento         | Ativo                                            | Inativo, expirado ou em recall                         |

---

###  H22 - Controle de quantidade de alimento

| Condição de Entrada         | Classes Válidas                  | Classes Inválidas                               |
|----------------------------|----------------------------------|-------------------------------------------------|
| Quantidade de alimento     | Abaixo do limite (1–10)          | Negativa, 0 ou acima do limite sem configuração |
| Status do alimento         | Ativo                            | Inativo, expirado ou em recall                  |
