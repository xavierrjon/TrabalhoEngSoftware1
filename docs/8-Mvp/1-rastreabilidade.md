# **História do Usuário**

# **Funcionalidade 3 – Tela de Cadastro de Alimentos**

- **História de Usuário:**

  História de Usuário: H4 – “Como usuário, quero cadastrar os alimentos com suas datas de validade, para que eu possa acompanhar o que está para vencer.”  

- **Implementação no MVP:**

   Tela de cadastro que permite inserir nome, categoria, data de validade, data de fabricação, quantidade e observações, com botões “Salvar” e “Cancelar”. Os dados são armazenados no banco.

# **Funcionalidade 4 – Tela de Lista de Alimentos**

- **Histórias de Usuário:**

  H18 – “Como usuário, eu quero acessar os alimentos já cadastrados, para que eu veja os alimentos cadastrados.”  
  H12 – “Como usuário, eu quero receber alertas de vencimento com antecedência, para que eu possa consumir os alimentos antes de estragarem.”  
  H20 – “Como usuário, gostaria de editar os alimentos da lista, para que eu possa adicionar ou remover os alimentos.”  
  H21 – “Como usuário, gostaria de classificar os alimentos cadastrados como consumidos, descartados ou próximos do vencimento, para uma melhor organização.”
  
- **Implementação no MVP:**

  A lista exibe os alimentos cadastrados, ordenados por validade. Alerta visual para itens próximos do vencimento (ex: cores verde, amarelo e vermelho). Botões para editar, excluir e marcar como consumido.

# **Funcionalidade 5 – Tela de Dicas de Armazenamento**

- **Histórias de Usuário:**

  H7 – “Como usuário, gostaria de receber dicas de como armazenar diferentes tipos de alimentos para armazenar da melhor forma possível.”  
  H19 – “Como usuário, eu gostaria de compartilhar as dicas de armazenamento de alimentos para outras pessoas via WhatsApp, para que  
todos possam armazenar da melhor forma.”

- **Implementação no MVP:**  

  Tela com exibição de dicas categorizadas por tipo de alimento (frutas, verduras, carnes etc). Inclui filtros por categoria. Recursos futuros: favoritar dicas, salvar offline e compartilhar via WhatsApp.  

# **Rastreabilidade**  

# **1. Tela de Cadastro de Alimentos**  

- **Diagrama de Classes:**  
Utiliza as classes:  
  - Alimento
  - Usuario
  - GerenciadorAlimento
  - Enum StatusAlimento  

- **Diagrama C4 (Container):**

  A funcionalidade faz parte do container “App Mobile EcoMida”, que armazena as informações localmente no container “Banco de Dados” (Hive ou ObjectBox).


# **2. Tela de Lista de Alimentos**  

- **Diagrama de Classes:**
**Utiliza as classes:**
  - Alimento
  - Usuario
  - GerenciadorAlimento
  - Notificacao
  - Enum StatusAlimento
  
- **Diagrama C4 (Container):**

  A funcionalidade pertence ao container “App Mobile EcoMida”, que consulta os dados no “Banco de Dados”. Alertas visuais são programados via a classe Notificacao, que se conecta com o container “Flutter Local Notifications System” para envio de lembretes ao usuário.  

# **3. Tela de Dicas de Armazenamento**  

- **Diagrama de Classes:**
**Utiliza as classes:**

  - DicasArmazenamento
  - Usuario
  
- **Diagrama C4 (Container):**

  A funcionalidade está no container “App Mobile EcoMida”, que armazena ou consulta as dicas no “Banco de Dados”.  
  Recursos como marcar como favorita e salvar offline são realizados localmente no app, sem necessidade de comunicação externa.
  
# **4. Tela de Cadastro de Usuário**

- **Função: Permitir que novos usuários se registrem no sistema com nome, e-mail e senha.**
- **Diagrama de Classes:**
**Utiliza as classes:**  

  - Usuario
  - Autenticação
- **Diagrama C4 (Container):**

  A funcionalidade pertence ao container “App Mobile EcoMida”, que realiza a autenticação via o container “Firebase Auth System”, salvando os dados localmente no “Banco de Dados” após validação.
  
# **5. Tela de Login**  

- **Função: Permitir que usuários existentes entrem no sistema com e-mail e senha.**
- **Diagrama de Classes:**
**Utiliza a classe:**  

  - Autenticação (com os métodos login(), logout() e usuarioLogado())
- **Diagrama C4 (Container):**
- Essa funcionalidade também faz parte do container “App Mobile EcoMida”, que usa o “Firebase Auth System” para autenticar o usuário localmente antes de liberar o acesso ao app.
