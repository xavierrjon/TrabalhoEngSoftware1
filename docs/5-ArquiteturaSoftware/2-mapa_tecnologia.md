# Tecnologias e Ferramentas Utilizadas

## Introdução

Aqui mostramos o Mapa de Tecnologias (Tech Stack) do aplicativo *EcoMida*, detalhando as principais ferramentas, linguagens e bibliotecas utilizadas no desenvolvimento do sistema.

O *EcoMida* foi pensado para funcionar tanto online quanto offline, oferecendo aos usuários uma experiência fluida, segura e eficiente. A escolha das tecnologias prioriza usabilidade, desempenho, armazenamento local, notificações eficientes e monitoramento dos erros quando conectado à internet.

---

## Mapa de Tecnologias

![image](https://github.com/xavierrjon/TrabalhoEngSoftware1/blob/main/docs/Imagens/ArquiteturaSoftware/techstackmap.png)


> O mapa acima resume as principais tecnologias utilizadas no desenvolvimento do EcoMida, organizadas nas seguintes categorias:
- *Frontend:* Interface do usuário desenvolvida com Flutter, garantindo compatibilidade multiplataforma e suporte offline.
- *Backend:* Funções em nuvem opcionais (Firebase Cloud Functions), usadas apenas quando houver conexão.
- *Banco de Dados:* Utilização de banco local como Hive ou Objectbox para garantir desempenho offline.
- *Notificações:* Notificações locais, funcionando sem dependência de internet.
- *Autenticação:* Firebase Auth combinado com armazenamento local para sessões offline.
- *Monitoramento:* Firebase Crashlytics para análise e rastreio de erros quando conectado.
- *Implantação:* Distribuição oficial nas lojas Google Play e App Store.

---

## Tabela de Tecnologias e Justificativa

A tabela abaixo foi elaborada com o objetivo de documentar de forma clara e organizada todas as tecnologias, ferramentas e arquiteturas utilizadas no desenvolvimento do projeto **EcoMida**.

Esta estrutura tem como propósito:

- Facilitar a visualização rápida da stack tecnológica do projeto;
- Ajudar novos desenvolvedores a entenderem o ecossistema da aplicação;
- Justificar as escolhas técnicas, destacando o papel de cada tecnologia dentro do sistema.

Cada item listado está categorizado de acordo com sua função no sistema (como *Frontend*, *Backend*, *Banco de Dados*, entre outros), acompanhado de uma breve descrição sobre seu uso no contexto da aplicação.



| Camada          | Tecnologia                               | Justificativa                                                                                  |
|-----------------|------------------------------------------|------------------------------------------------------------------------------------------------|
| *Front-end*   | Flutter                                  | Permite desenvolvimento mobile multiplataforma com suporte a recursos offline                 |
| *Back-end*    | Firebase Cloud Functions (opcional)   | Usado apenas quando online; lógica principal pode estar embutida no app                       |
| *Banco de Dados* | Hive ou Objectbox                     | Banco de dados local, rápido e eficiente para uso offline em Flutter                          |
| *Autenticação* | Firebase Auth + armazenamento local     | Login com cache local para manter sessão offline                                              |
| *Notificações* | Flutter Local Notifications             | Permite notificações sem internet (baseadas no tempo e dados do dispositivo)                  |
| *Deploy*       | Google Play / App Store                 | Distribuição oficial                                                                           |
| *Monitoramento*| Firebase Crashlytics (quando online)  | Coleta erros ao reconectar, garantindo acompanhamento da saúde do app                         |

---
