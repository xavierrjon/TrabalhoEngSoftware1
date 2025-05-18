# Análise SWOT

A Análise SWOT é uma metodologia amplamente utilizada no planejamento estratégico para identificar fatores que impactam o sucesso de um projeto, tanto interna quanto externamente. O termo deriva das iniciais em inglês: *Strengths (Forças), **Weaknesses (Fraquezas), **Opportunities (Oportunidades)* e *Threats (Ameaças)*. 

Essa técnica permite visualizar de forma clara os elementos que podem favorecer ou dificultar o desenvolvimento e a adoção de um sistema, auxiliando na definição de estratégias mais alinhadas ao contexto real de uso. 

No caso do aplicativo *EcoMida*, a análise SWOT foi aplicada com o objetivo de entender melhor os recursos disponíveis, os desafios enfrentados e as possibilidades de expansão e impacto social da solução, especialmente em ambientes como unidades públicas de saúde que lidam com limitações operacionais e alta demanda por segurança alimentar.


## Forças
- Proposta de valor clara e com foco social: promover o uso seguro e consciente de alimentos.
- Funciona **offline**, sendo acessível para regiões com pouca ou nenhuma conectividade.
- Aplicativo **gratuito** e educativo, com orientações sobre armazenamento e consumo seguro de alimentos.
- Possui sistema de **backup simples** via arquivos (.csv/.txt), facilitando o uso em diferentes dispositivos.

## Fraquezas
- **Não possui escaneamento automático** de rótulos de alimentos.
- Interface e usabilidade ainda podem ser aprimoradas para melhorar a experiência do usuário.
- Falta de uma **base de dados integrada** de produtos e alimentos.
- Adoção pode ser limitada pelo **baixo conhecimento da proposta** entre usuários e instituições.

## Oportunidades
- Crescente interesse social na **redução do desperdício de alimentos**.
- Possibilidade de **parcerias com ONGs, escolas e programas sociais**.
- Expansão para **áreas rurais ou com acesso limitado à tecnologia**.
- **Incentivos públicos** voltados à segurança alimentar podem apoiar o desenvolvimento da solução.

## Ameaças
- Concorrência com **apps mais tecnológicos** (ex: com leitura de rótulos via scanner).
- **Baixa adesão inicial** por falta de divulgação ou engajamento.
- Atualizações nos sistemas operacionais que possam **quebrar a compatibilidade**.
- **Desvalorização de aplicativos com foco não comercial**, dificultando financiamento e manutenção.

<p align="center"><img src="images_mercado/analise_swot.jpg" style="width:70%"/></p>

# Soluções Existentes
Antes do desenvolvimento do *EcoMida*, já existiam algumas soluções no mercado voltadas à segurança alimentar, controle de validade e combate ao desperdício de alimentos. A maioria desses aplicativos foca no escaneamento de rótulos, controle de estoque doméstico ou em ações de conscientização para consumo responsável. 
No entanto, grande parte dessas ferramentas apresenta limitações quando se trata de acessibilidade (por exigirem conexão constante com a internet), custo para o usuário ou pouca ênfase no aspecto educacional e social. Além disso, muitas soluções existentes não dialogam diretamente com contextos de vulnerabilidade alimentar ou com regiões que têm acesso restrito à tecnologia. 
O *EcoMida* surge como uma alternativa gratuita, funcional offline e com forte apelo educativo, buscando preencher essas lacunas e contribuir de forma significativa para a segurança alimentar em comunidades diversas.

## Concorrência
Alguns apps disponíveis no mercado que oferecem funcionalidades semelhantes, mas com focos diferentes:
- *Yuka* – Yuka é um aplicativo que analisa a composição de produtos alimentícios e cosméticos, avaliando seu impacto na saúde. Ele funciona através de um scanner que decifra rótulos e fornece uma avaliação do produto em um sistema de cores (excelente, bom, medíocre, ruim), além de oferecer informações detalhadas e sugestões de alternativas mais saudáveis.
  
<p align="center"><img src="images_mercado/yuka1.jpeg" style="width:50%"/></p>  
<p align="center"><img src="images_mercado/yuka2.jpeg" style="width:70%"/></p>


  
- *NoWaste* – O NoWaste é um aplicativo gratuito que permite aos usuários monitorar, organizar e gerenciar os alimentos em casa, com o objetivo de reduzir o desperdício e economizar dinheiro. O app oferece ferramentas para criar listas de inventário para a geladeira, freezer e despensa, facilitando o controle dos itens disponíveis e suas datas de validade.
  
<p align="center"><img src="images_mercado/nowaste.png" style="width:70%"/></p>
  
- *Fridge Pal AI* – O FridgePal AI é um aplicativo gratuito que utiliza inteligência artificial para sugerir receitas com base nos ingredientes disponíveis na sua geladeira. Com apenas um vídeo da sua geladeira, o app identifica os itens presentes e propõe receitas personalizadas, considerando preferências alimentares, ferramentas de cozinha e nível de habilidade culinária. 

<p align="center"><img src="images_mercado/fridgepal.png" style="width:70%"/></p> 





---

## Quadro Comparativo

| Critérios/Soluções       | **NoWaste**                | **Fridge Pal AI**          | **Yuka**                    | **EcoMida**                                              |
|--------------------------|----------------------------|----------------------------|-----------------------------|---------------------------------------------------------------|
| **Modelo de negócio**    | Freemium                   | Gratuito com anúncios      | Freemium                    | Gratuito com foco social                                      |
| **Tecnologia utilizada** | App móvel (iOS/Android)    | App móvel (iOS/Android)    | App móvel com scanner       | App móvel com banco local + backup               |
| **Pontos fortes**        | Notificações, categorização| Facilidade de uso          | Base de dados de produtos   | Offline, acessível, educativo, com guia de uso               |
| **Pontos fracos**        | Precisa de internet        | Interface antiga           | Não ajuda no armazenamento  | Sem escaneamento automático (por enquanto)                   |
| **Público-alvo**         | Pessoas organizadas        | Usuários domésticos        | Consumidores exigentes      | Famílias, comunidades locais, pessoas sem acesso a apps complexos |
