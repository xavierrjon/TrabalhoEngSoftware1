# Casos de Testes com Classes de Equivalências

Os casos de teste foram definidos com base na técnica de partição em classes de equivalência, aplicada às funcionalidades do sistema. O objetivo é garantir uma cobertura eficiente dos testes, validando comportamentos esperados tanto para entradas válidas quanto inválidas. Cada caso de teste foi elaborado considerando critérios de aceitação e regras de negócio específicas, buscando assegurar a qualidade e a robustez do produto.

---
### H4 - Como usuário, quero cadastrar os alimentos com suas datas de validade, para que eu possa acompanhar o que está para vencer.

#### Critérios de Aceitação
- C1. O sistema deve permitir o cadastro manual de alimentos com nome, tipo, e data de validade.
- C2. O app deve exibir a lista de alimentos organizados por data de vencimento (do mais próximo para o mais distante).
- C3. O usuário deve ser notificado quando um alimento estiver próximo do vencimento.
- C4. Deve haver a opção de editar ou remover alimentos cadastrados.

#### Regras de Negócio
- R1. O sistema deve aceitar apenas datas de validade futuras ou iguais à data atual — datas anteriores devem ser rejeitadas.
- R2. Cada alimento deve ter obrigatoriamente um nome e uma data de validade associada para ser salvo.
- R3. Os dados de alimentos cadastrados devem ser armazenados de forma segura, respeitando a LGPD.
- R4. Alimentos com data de vencimento próxima (ex: até 3 dias) devem ser destacados para o usuário.
- R5. O histórico de alimentos vencidos será visível apenas para o usuário que realizou o cadastro.

### Classes de Equivalência

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

###  H7 - Como usuário, gostaria de receber dicas de como armazenar diferentes tipos de alimentos para armazenar da melhor forma possível.

#### Critérios de Aceitação
- C1. As dicas devem estar organizadas por categorias de alimentos (ex: carnes, vegetais, laticínios,
grãos, congelados, etc.).
- C2. O conteúdo das dicas deve estar disponível mesmo sem conexão com a internet (modo offline).
- C3. Deverão ser incluídos exemplos práticos sempre que o conteúdo permitir.
- C4. A interface deve permitir ajuste de tamanho de fonte para tornar o conteúdo mais legível,
especialmente para pessoas com TEA.
- C5. O app deve permitir favoritar dicas, para que o usuário possa consultá-las mais rapidamente depois.
- C6. Todas as dicas devem ser curtas (O texto deve conter até 300 caracteres) para garantir leitura rápida e clareza.

#### Regras de Negócio
- R1. As dicas devem ser validadas por fontes confiáveis de saúde e segurança alimentar antes de serem
inseridas no sistema.
- R2. O conteúdo das dicas será fixo e não poderá ser editado pelo usuário, para garantir a integridade
das informações.

### Classes de equivalência
| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Texto da dica          | Até 300 caracteres (1)                    | Mais de 300 caracteres (2)|
| Fonte da dica          | Fonte confiável e registrada (3)            | Fonte ausente ou não verificada (4)          |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                       | Resultado Esperado |
| ------------- | ----------------------- | ---------------------------------------------- | ------------------ |
| Caso 1        | 1, 3                    | Texto: Beba água<br>Fonte: Ministério da Saúde | Válido             |
| Caso 2        | 2, 3                    | Texto com 301 caracteres<br>Fonte: Fiocruz     | Inválido           |
| Caso 3        | 1, 4                    | Texto: Coma frutas<br>Fonte: ""                | Inválido           |

Classe Vàlida: 1, 3

Classe Inválida:
- 2, 3
- 1, 4 

---

###  H8 - Como usuário PcD, gostaria que o app fizesse a leitura do nome dos alimentos e data de validade em voz alta, para que seja mais acessível.

#### Critérios de Aceitação
- C1. O botão de ativar a leitura deve ser visível e de fácil acesso próximo a cada alimento
cadastrado.
- C2. A voz que fará a leitura poderá ser personalizada de acordo com as preferências do usuário.
- C3. O sistema deve permitir ajuste da velocidade de leitura (lenta, normal, rápida).
- C4. Caso o volume do dispositivo do usuário esteja desativado, o sistema deve exibir uma
mensagem instruindo-o a ativar o volume.
- C5. Os conteúdos de voz deverão conter legendas sincronizadas ou versão em texto alternativo para acessibilidade auditiva.

#### Regras de Negócio
- R1. Toda atualização do app deve manter a compatibilidade com tecnologias assistivas (ex: TalkBack no
Android e VoiceOver no iOS).
- R2. A leitura em voz alta não pode incluir nenhum conteúdo promocional ou publicidade, em respeito às
normas de acessibilidade e experiência do usuário.
- R3. Todo conteúdo será revisado pela equipe de moderação antes da publicação para garantir ausência de promoções.

### Classes de equivalência

| Condição de Entrada     | Classes Válidas                          | Classes Inválidas                          |
|------------------------|------------------------------------------|--------------------------------------------|
| Volume do dispositivo  | Ativo  (1)                                 | Desativado sem mensagem de aviso (2)          |
| Voz utilizada          | Personalizável pelo usuário (3)          | Fixa e sem opção de ajuste (4)              |
| Legenda alternativa    | Presente e sincronizada (5)               | Ausente ou não funcional (6)                  |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                                       | Resultado Esperado |
| ------------- | ----------------------- | -------------------------------------------------------------- | ------------------ |
| Caso 1        | 1, 3, 5                 | Volume: Ativo<br>Voz: Personalizável<br>Legenda: Presente      | Válido             |
| Caso 2        | 2, 3, 5                 | Volume: Desativado<br>Voz: Personalizável<br>Legenda: Presente | Inválido           |
| Caso 3        | 1, 4, 6                 | Volume: Ativo<br>Voz: Fixa<br>Legenda: Presente                | Inválido           |
| Caso 4        | 1, 3, 6                 | Volume: Ativo<br>Voz: Personalizável<br>Legenda: Ausente       | Inválido           |

Classe Vàlida: 1, 3, 5

Classe Inválida:
- 2, 3, 5
- 1, 4, 6
- 1, 3, 6

---


### H9 - Como suporte técnico, gostaria de criar um menu com respostas de perguntas frequentes, para que os usuários tirem suas dúvidas de forma rápida.

#### Critérios de Aceitação
- C1. As perguntas devem estar organizadas por categorias temáticas (ex: Cadastro,
Backup, Alertas, Acessibilidade).
- C2. Deve haver um botão “Ainda com dúvida?” com link direto para o contato com o
suporte.
- C3. Ao clicar em ‘Ainda com dúvida?’, o usuário será redirecionado para um formulário de contato por e-mail (ou outro canal definido).
- C4. Deve existir suporte à leitura por voz, será feita via voz sintética do sistema.
- C5. A leitura por voz poderá ser ativada por um botão visível no canto superior da tela.
- C6. O sistema deve permitir que o usuário avalie a utilidade da resposta com um botão
“Essa resposta foi útil?”.

#### Regras de Negócio
- R1. O conteúdo do FAQ deve ser revisado e aprovado por profissionais de suporte ou
UX writing antes da publicação.
- R2. Todos os registros de feedbacks dos usuários sobre as respostas (útil/não útil)
devem ser anônimos.
- R3. O conteúdo será revisado a cada 60 dias conforme política interna de atualização e
controle de qualidade.

### Classes de equivalência

| Condição de Entrada          | Classes Válidas                            | Classes Inválidas                              |
|-----------------------------|--------------------------------------------|------------------------------------------------|
| Categoria de pergunta       | Cadastro, Backup, Alertas, Acessibilidade (1)  | Categoria inexistente ou vazia (2)                |
| Feedback do usuário         | "Essa resposta foi útil?" → Sim, Não  (3)   | Qualquer outro valor ou campo vazio (4)            |
| Identificação do feedback   | Feedback anônimo (5)                         | Feedback com nome, ID, e-mail do usuário (6)      |
| Leitura por voz ativada     | Botão visível no canto superior (7)          | Botão ausente, escondido ou fora da área visível (8) |

### Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas                                                                                              | Resultado Esperado |
| ------------- | ----------------------- | ----------------------------------------------------------------------------------------------------- | ------------------ |
| Caso 1        | 1, 3, 5, 7              | Categoria: Acessibilidade<br>Feedback: Sim<br>ID: Anônimo<br>Botão: Visível                           | Válido             |
| Caso 2        | 5, 3, 5, 7              | Categoria: ""<br>Feedback: Sim<br>ID: Anônimo<br>Botão: Visível                                       | Inválido           |
| Caso 3        | 1, 4, 5, 7              | Categoria: Backup<br>Feedback: Talvez<br>ID: Anônimo<br>Botão: Visível                                | Inválido           |
| Caso 4        | 1, 3, 6, 7              | Categoria: Cadastro<br>Feedback: Sim<br>ID: [joao@email.com](mailto:joao@email.com)<br>Botão: Visível | Inválido           |
| Caso 5        | 1, 2, 3, 8              | Categoria: Cadastro<br>Feedback: Sim<br>ID: Anônimo<br>Botão: Ausente                                 | Inválido           |

Classe Vàlida: 1, 3, 5, 7

Classe Inválida:
- 2, 3, 5, 7
- 1, 4, 5, 7
- 1, 3, 6, 7
- 1, 3, 5, 8

---


### H12 - Como usuário, eu quero receber alertas de vencimento com antecedência, para que eu possa consumir os alimentos antes de estragarem.

#### Critérios de Aceitação:

- C1. O sistema deve verificar diariamente os alimentos cadastrados com datas de validade próximas.
- C2. O usuário pode configurar alertas entre 1 e 30 dias de antecedência.
- C3. O alerta deve ser enviado por notificação push e exibido na tela inicial do app.
- C4. O sistema deve registrar no histórico a ação tomada para cada alimento vencido ou próximo do vencimento.

#### Regras de Negócio:

- R1. Alimentos com status "inativo", "expirado" ou sob recall não devem gerar alertas.
- R2. Alertas não serão enviados para alimentos com status inativo, mesmo que o usuário tenha configurado previamente.
- R3. As notificações devem ser armazenadas de forma segura, respeitando a LGPD e a ISO 27001.
- R4. O app não deve compartilhar alertas de vencimento com terceiros sem o consentimento explícito do usuário.

### Classes de equivalência

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


###  H14 - Como suporte técnico, eu quero receber notificações automáticas quando um usuário relatar um erro crítico, para que eu possa responder rapidamente e evitar maiores impactos.

#### Critérios de Aceitação:

- C1. O sistema deve classificar automaticamente os relatos de erro por gravidade (crítico, alto, médio, baixo).
- C2. Relatos marcados como “críticos” devem gerar uma notificação imediata para o suporte técnico.
- C3. A notificação deve incluir o ID do usuário, horário, versão do app e descrição do erro.
- C4. O sistema deve registrar o tempo de resposta da equipe técnica ao alerta.
- C5. Todos os erros críticos devem ser registrados em log para análise posterior.

#### Regras de Negócio:

- R1. Relatos que contenham dados sensíveis devem ser criptografados antes do envio à equipe técnica.
- R2. A criptografia dos dados será realizada com padrão mínimo AES-256
- R3. O sistema não deve enviar logs de erro para terceiros sem autorização da empresa ou do usuário.
- R4. A política de resposta a erros críticos deve seguir o SLA (Service Level Agreement) definido pela organização.
- R5. O SLA mínimo deverá ser de 24 horas úteis para respostas a solicitações.

### Classes de equivalência

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

###  H18 - Como usuário, eu quero acessar os alimentos já cadastrados, para que eu ver os alimentos cadastrados.

#### Critérios de Aceitação
- C1. O app deve apresentar um botão ou aba de "Meus Alimentos" acessível pela tela
principal.
- C2. Deve ser possível filtrar por categorias: vencidos, próximos do vencimento, etc.
- C3. O usuário deve poder ordenar a lista manualmente ou por critérios (nome, local,
vencimento).

#### Regras de Negócio
- R1. A lista de alimentos cadastrados deve ser privada.
- R2. Alterações nos dados dos alimentos (edição ou exclusão) exigem confirmação
explícita do usuário.

### Classes de equivalência

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


### H19 - Como usuário, eu gostaria de compartilhar as dicas de armazenamento de alimentos para outras pessoas via WhatsApp, para que todos possam armazenar da melhor forma.

#### Critérios de Aceitação
- C1. O app deve exibir um botão de compartilhamento visível em cada dica de armazenamento.
- C2. O app deve mostrar uma mensagem de confirmação visual ou sonora após o compartilhamento ser realizado.
- C3. O usuário deve conseguir compartilhar quantas dicas quiser, sem limite por sessão.
- C4. Deve poder compartilhar uma dica de cada vez.

#### Regras de Negócio
- R1. O compartilhamento não deve incluir nenhuma informação pessoal do usuário.
- R2. O sistema deve bloquear compartilhamento com links falsos ou potencialmente maliciosos, mesmo que inseridos por erro na dica.

### Classes de equivalência

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

###  H20 - Como usuário, gostaria de editar os alimentos da lista, para que eu possa adicionar ou remover os alimentos.

#### Critérios de Aceitação
- C1. O sistema deve validar campos obrigatórios (ex: nome e validade) antes de salvar.
- C2. O sistema deve exibir uma mensagem de confirmação ao salvar uma edição.
- C3. O sistema deve impedir alimentos duplicados na lista.
- C4. Nomes de alimentos podem conter letras, espaços, acentos e hífens.
- C5. O campo de nome deve ter no máximo 20 caracteres.

#### Regras de Negócio
- R1. Todo alimento adicionado deve estar em conformidade com a base de dados nutricional aprovada pela empresa.
- R2. Alimentos com validade vencida ou proibidos por órgãos reguladores não podem ser adicionados.

### Classes de equivalência

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

###  H21 - Como usuário, gostaria de classificar os alimentos cadastrados como consumidos, descartados ou próximos do vencimentos, para uma melhor organização.

#### Critérios de Aceitação
- C1. Alimentos só podem ser marcados como ‘Descartado’ se estiverem vencidos ou com data de validade ausente.
- C2. O usuário deve poder criar etiquetas personalizadas para classificação.
- C3. Cada etiqueta pode ter até 20 caracteres, máximo de 10 etiquetas por usuário, e pode ser reutilizada.
- C4. Alimentos podem ser classificados individualmente ou em lote (seleção múltipla).
- C5. O app exibe relatório de alimentos etiquetados e não etiquetados.
- C6. Um alimento só pode ter uma classificação ativa por vez. Alterações sobrescrevem o status anterior.

#### Regras de Negócio
- R1. O sistema deve impedir que alimentos com validade futura sejam marcados como vencidos manualmente, por integridade de dados.
- R2. A classificação deve respeitar as boas práticas de segurança alimentar e as diretrizes da OMS.

### Classes de equivalência

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

Classe Vàlida: 1, 3, 5, 7, 9, 11

Classe Inválida:
- 1, 3, 5, 7, 9, 11
- 2, 3, 5, 7, 9, 11
- 1, 4, 5, 7, 9, 11
- 1, 3, 6, 7, 9, 11
- 1, 3, 5, 8, 9, 11
- 1, 3, 5, 7, 10, 11
- 1, 3, 5, 7, 9, 12

---

###  H22 - Como usuário, gostaria que o app criasse uma lista de compras com base dos alimentos que estão acabando, para facilitar no momento das compras.

#### Critérios de Aceitação
- C1. O sistema deve identificar automaticamente alimentos com quantidade abaixo do limite mínimo definido. O limite mínimo será definido pelo sistema, mas o usuário poderá ajustá-lo dentro de uma faixa de 1 a 10 unidades.
- C2. O usuário pode revisar e editar a lista de compras antes de salvá-la.
- C3. O usuário pode marcar itens como “comprados” diretamente na lista.
- C4. O app deve salvar o histórico das últimas listas de compras.
- C5. O app deve permitir múltiplas listas (ex: compras semanais, compras especiais).

#### Regras de Negócio
- R1. A lista de compras não pode incluir alimentos inativos, expirados ou suspensos por recall, conforme política de segurança alimentar (ANVISA).
- R2. Todas as listas devem ser armazenadas de forma segura e criptografada, conforme política de proteção de dados (LGPD e ISO 27001).
- R3. O app deve impedir que listas de compras sejam compartilhadas com terceiros sem o consentimento do usuário.
- R4. Antes de compartilhar, o app solicitará confirmação explícita do usuário.

### Classes de equivalência

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
