# Rastreabilidade 

No aplicativo *EcoMida*, a rastreabilidade desempenha um papel essencial ao permitir acompanhar como as histórias de usuário, que refletem as necessidades e expectativas dos usuários, foram traduzidas em soluções técnicas dentro da arquitetura do sistema. A seguir, é apresentada uma tabela que conecta cada história do usuário aos componentes do sistema que a viabilizam, incluindo as tecnologias aplicadas e aos diagramas que ilustram essas decisões. Esse vínculo direto entre requisitos e arquitetura facilita a análise da consistência entre o que foi solicitado pelos usuários e o que foi efetivamente projetado e implementado.

## Tabela de Rastreabilidade com Histórias do Usuário:

| **História do Usuário**                                                    | **Componentes Envolvidos**                                                                 | **Diagramas de Referência**       |
| -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------- |
| **H1:** Registrar consumo ou descarte para controle da despensa.               | App Mobile Usuário (Flutter), Banco de Dados, Sistema de Gerenciamento de Alimentos        | Contexto, Containers, Componentes |
| **H2:** Organização por rotina ou horário (Usuário PcD).                       | App Mobile Usuário (Flutter), Banco de Dados, Sistema de Gerenciamento de Alimentos        | Contexto, Containers, Componentes |
| **H3:** Avaliação do suporte técnico (até 5 estrelas).                                 | App Mobile Suporte Técnico (Web), Módulo de Avaliação de Suporte, Banco de Dados                           | Contexto, Containers, Componentes |
| **H4:** Cadastrar alimentos com datas de validade.                             | App Mobile Usuário (Flutter), Sistema de Cadastro de Alimentos, Banco de Dados             | Contexto, Containers, Componentes |
| **H5:** Feedback claro após cada ação para evitar erros.                               | App Mobile Usuário (Flutter), Sistema de Mensagens de Feedback, Banco de Dados                             | Contexto, Containers, Componentes |
| **H6:** Interface acessível com poucos elementos e cores suaves (Usuário PcD).         | App Mobile Usuário (Flutter), Módulo de Interface Acessível, Banco de Dados                                | Contexto, Containers, Componentes |
| **H7:** Receber dicas de armazenamento de alimentos.                                   | App Mobile Usuário (Flutter), Sistema de Dicas e Conteúdos, Banco de Dados                                 | Contexto, Containers, Componentes
| **H8:** Leitura em voz alta dos alimentos e data de validade (Acessibilidade). | App Mobile Usuário (Flutter), Módulo de Acessibilidade por Voz, Banco de Dados             | Contexto, Containers, Componentes |
| **H9:** Criar menu com perguntas frequentes para suporte.                      | App Mobile Suporte Técnico (Web), Sistema de FAQ (Perguntas Frequentes), Banco de Dados    | Contexto, Containers, Componentes |
| **H10:** Corrigir erros técnicos para garantir a boa experiência.                      | App Mobile Suporte Técnico (Web), Serviço de Monitoramento e Correção de Erros, Banco de Dados             | Contexto, Containers, Componentes |
| **H11:** App para ajudar a reduzir desperdícios.                                       | App Mobile Usuário (Flutter), Sistema de Gerenciamento de Alimentos, Serviço de Alertas, Banco de Dados    | Contexto, Containers, Componentes |
| **H12:** Receber alertas de vencimento com antecedência.                       | App Mobile Usuário (Flutter), Serviço de Notificações, Banco de Dados                      | Contexto, Containers, Componentes |
| **H14:** Suporte técnico recebe notificação de erro crítico.                   | App Mobile Suporte Técnico (Web), Serviço de Notificações, Banco de Dados                  | Contexto, Containers, Componentes |
| **H18** – Como usuário, quero acessar os alimentos já cadastrados, para que eu possa visualizar minha lista atualizada.                          | App Mobile Usuário (Flutter), Sistema de Gerenciamento de Alimentos, Banco de Dados        | Contexto, Containers    |
| **H19:** Compartilhar dicas de armazenamento via WhatsApp.                     | App Mobile Usuário (Flutter), Módulo de Compartilhamento, Banco de Dados                   | Contexto, Containers, Componentes |
| **H20:** Editar alimentos na lista.                                          | App Mobile Usuário (Flutter), Sistema de Gerenciamento de Alimentos, Banco de Dados                        | Contexto, Containers, Componentes |
| **H21:** Classificar alimentos como consumidos, descartados ou próximos do vencimento. | App Mobile Usuário (Flutter), Sistema de Gerenciamento de Alimentos, Sistema de Relatórios, Banco de Dados | Contexto, Containers, Componentes |
| **H22:** Criar lista de compras com base nos alimentos que estão acabando.     | App Mobile Usuário (Flutter), Sistema de Gerenciamento de Lista de Compras, Banco de Dados | Contexto, Containers, Componentes |
