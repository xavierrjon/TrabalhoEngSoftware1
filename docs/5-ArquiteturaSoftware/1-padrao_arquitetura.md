# Padrões Arquiteturais
## Visão Geral do EcoMida

O EcoMida é um aplicativo voltado para promover o consumo consciente de alimentos. Suas principais funcionalidades são:
* Cadastro de alimentos com data de validade e tipo;
* Notificações automáticas próximas à validade;
* Alertas de segurança alimentar;
* Redução do desperdício por meio de lembretes e organização.
  
## Arquitetura Recomendada
A arquitetura ideal para o *EcoMida* combina:

* Clean Architecture: para organizar e isolar a lógica de negócio;
* MVVM (Model-View-ViewModel): para estruturar a camada de apresentação;
* Pub/Sub (Publish-Subscribe): para eventos internos desacoplados, como agendamento de notificações.

## Exemplo Visual
<img src="https://raw.githubusercontent.com/xavierrjon/TrabalhoEngSoftware1/main/docs/Imagens/ArquiteturaSoftware/arquitetura.jpg" width="400" />

## Conclusão
A arquitetura proposta para o EcoMida é bem estruturada, moderna e robusta, adequada para aplicativos com lógica de negócio relevante e necessidade de manutenção a longo prazo. O uso combinado de Clean Architecture, MVVM e Pub/Sub traz organização, escalabilidade e flexibilidade, embora exija disciplina na implementação.<p>
