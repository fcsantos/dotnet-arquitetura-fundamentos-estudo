## RESUMO

## Classe x Objeto

- Classe: Definição de Classe: é uma estrutura de código ou dados que tem a função de mapear o objeto do mundo real;
- Objeto: Definição de Objeto: é quando tem uma classe sendo instanciada e alocada na memória;

## Pilares OOP

- O **estado** é representado através de PROPRIEDADES de uma classe;
- O **comportamento** é quando gera ou processa uma informação, através de um MÉTODO da classe ou altera o estado da classe (modifica o valor da propriedade);
- A **herança** permite que você crie novas classes que reutilizam, estendem e modificam o comportamento definido em outras classes;
  - Sempre pense no É UM exemplo: um funcionário É UMA pessoa, se não fizer sentido é porque não deva fazer herança ou é realmente necessário;
- **Classe abstrata**: Sempre tem que ser herdada e não pode ser instanciada, oferecem um cojunto de estado(propriedade) e comportamento(método) que abstraem uma certa especialização;
  - OBS: o conceito de abstração é a base para o polimorfismo e o encapsulamento;
  - **Métodos abstratos** não são obrigados a implementar o comprotamento na classe base, só a classe derivada (classe que estiver herdando, que são obrigatórios);
  - **Métodos virtual** podem ter a implementação do comportamento na classe base e ao herdar a classe, posso alterar seu comportamento na classe derivada (override não é obrigatório);
- **Poli-morfismo**: a classe derivada pode assumir diversos comportamentos;
- **Encapsulamento**: é a arte de encapsular comportamentos(métodos) através da exposição de métodos PUBLIC e esconder certos comportamentos a escrita de métodos PRIVATE (preservando certas implementações);

## Interface

- **Interface**: é uma espécie de contrato simples, então toda classe que implementa uma interface ela é obrigada a implementar seus métodos;
    
    **OBS**: não pode ser comparada com a Classe Abstrata, porque uma classe abstrata forca a implementacao de metodos tambem
      implementa alguns comportamentos que podem ser derivados

## Modificadores
- **classe selada** só pode ser instanciada e não herdada;
- **Classe e Método PUBLIC**: Access is not restricted;
- **Classe e Método PROTECTED**: Access is limited to the containing class or types derived from the containing class;
- **Classe e Método INTERNAL**: Access is limited to the current assembly;
- **Método PROTECTED INTERNAL**: Access is limited to the current assembly or types derived from the containing class;
- **Classe e Método PRIVATE**: Access is limited to the containing type;
- **Método PRIVATE PROTECTED**: Access is limited to the containing class or types derived from the containing class within the current assembly.Available since C# 7.2;

## Princípios SOLID

SOLID é um acrônimo dos cinco primeiros princípios da OOP e design de codigo identificados por Roberc C. Martin (Uncle Bob).

Os princípios do SOLID devem ser aplicados para se obter os benefícios da OO, tais como:
- Seja fácil de se manter, adaptar e se ajustar às alterações de escopo;
- Seja testável e de fácil entendimento;
- Seja extensível para alterações com o menor esforço necessário;
- Que forneça o máximo de reaproveitamento;
- Que permaneça o máximo de tempo possível em utilização;

Utilizando os princípios SOLID é possível evitar problemas muito comuns:
- Dificuldade na testabilidade / criação de testes de unidade;
- Código macarrônico, sem estrutura ou padrão;
- Dificuldades de isolar funcionalidades;
- Duplicação de código, uma alteração precisa ser feita em N pontos;
- Fragilidade, o código quebra facilmente em vários pontos após uma mudança;

### SRP - Single Responsability Principle
- Uma classe deve ter **um, e apenas um** motivo para ser modificada;
Exemplo: Classe que envia o email.

### OCP - Open Closed Principle
- Entidades de software (classes, módulos, funções, etc) devem estar abertas para extensão, mas fechadas para modificação;
Exemplo: Utilizar herança ou extension method.

### LSP- Liskov Substitution Principle
- Subclasse devem ser substituíveis por suas Superclasses.
Exemplo: usando abstração de classe (classe base Parelelogramo -> Quadrado).

### ISP - Interface Segregation Principle
- Classes não devem ser forçados a depender de métodos que não usam ou muitas interfaces específicas são melhores do que uma interface única.
Exemplo: ICadastroCliente e ICadastroProduto herdam de ICadastro

### DIP - Dependency Inversion Principle
- Dependa de uma abstração e não de uma implementação.

:link: Algumas referencias:

https://github.com/ardalis/SolidSample

## Dependency Injection

- **Transient**: Modelo padrão (quando não se sabe como usar, seria a melhor escolha), vai ser criada toda vez que for injetada em alguma classe, funciona melhor em objetos leves ou serviços sem estado (ocupa mais memória, porque toda vez que é requisitado cria uma instancia);
- **Scoped**: Os objetos são criados uma vez por client request (por conexão), muito utilizado em aplicações Web;
- **Singleton**: Cria uma unica instancia para toda a aplicação (todo o tempo de execução da aplicação);

:link: Algumas referencias:

https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-3.1

https://www.palmmedia.de/blog/2011/8/30/ioc-container-benchmark-performance-comparison

https://simpleinjector.readthedocs.io/en/latest/index.html

## Clean Code
- **O que é um código limpo?**
  * Simples;
  * Direto;
  * Eficiente;
  * Sem duplicidade;
  * Elegante;
  * Feito com cuidado;
  * Fácil de ler.

- **Desculpas?**
  * Mas o cronograma está apertado!
  * Meu chefe me pressiona a entregar logo!
  * Quero mostrar produtividade.
  * Não ganho o suficiente para escrever o melhor código do mundo!
  * A empresa não valoriza bom código e sim a entrega!
  
- **Verdades que não lhe dizem...**
  * Sua carreira é sua responsabilidade!
  * Leia, Estude e Pratique;
  * Vá a conferências;
  * Faça cursos;
  
**OBS1**: Não é a responsabilidade do seu empregador lhe oferecer cursos, oportunidades ou até mesmo um projeto com a tecnologia que pretende se especializar.   
**OBS2**: "Você recebe para trabalhar 40 horas por semana e resolver os problemas da sua empresa, não os seus..." (Uncle Bob)

- **Quanto custa um código ruim?**
  * Alta rotatividade;
  * Demora na entrega de nova funcionalidades;
  * Dificuldade na manutenção;
  * Alta incidência de bugs;
  * Perda de confiança do cliente;
  * Desmotivação profissional;
  * Mais tempo depurando o código do que escrevendo.

- **Como medir um bom código?**
  * Linhas de código (depende do contexto);
  * Número de métodos (depende do contexto);
  * Número de classes
  * Linhas de código por método (Excemplo: quebrar um método em 3);
  * Complexidade ciclomática (pode ser evitada utilizando a separação de responsabilidade);
  * Número de estruturas de decisão;
 
- **Nomes significativos!**
  * Escolha os nomes que revelem intenção!
  * Por que existe;
  * O que faz;
  * Como é usado;
  * Use nomes fáceis de se encontrar;
  * Use nomes pronunciáveis;
  * Evite siglas ou acrônimos;
  * Não economize palavras;
  * Revele a intenção do código;
  * Evite palavras que podem ser variáveis ou palavras reservadas em outras plataformas;
  * Evite dar nomes como "doubleValorPromocional" ou "clienteEmail", o tipo não precisa estar no nome;
  * Evite trocadilhos, não misture idioma, não mescle nomes.
  
  **OBS**:. O SOLID ajuda muito nesses sentidos.

- **Boas práticas!**
  * Nome de **classes** devem ser **substantivos** e não devem conter verbos.
    Exemplo: ClienteRepository
    
  * Nome de **métodos** devem conter **verbos** de preferência no infinitivo.
    Exemplo: AdicionarCliente
   
  * Não seja genérico
    (Errado)
    // processa folha de pagamento
    Processa();
    // calcula imposto de renda
    Calcula();
    
    **OU**
    (Certo)
    ProcessarFolhaPagamento();
    CalcularImpostoRenda();
    
 - **Menos é mais!**
   * "A primeira regra dos métodos é que eles devem ser pequenos. A segunda regra é que eles devem ser menores ainda." (Uncle Bob)
   * Método <= 20 linhas;
   * Linha <= 100 caracteres;
   * Classe <= 500 linhas;

 - **Métodos**
   * Extraia trechos em métodos privados;
   * Métodos devem fazer apenas uma coisa, fazê-la certa e somente faze-la;
   * Evite muitos parâmetros(ex. criar DTO);
   * Não deixe o método mentir dizendo que faz uma coisa e faz outras "escondidas";
   * Se o método tiver mais de uma responsabilidade extraia em dois ou mais (cada um com sua responsabilidade);
   * Leia seu método de cima para baixo como uma narrativa, ele deve fazer sentido;
   * Aplique uma boa indentação;

 - **Comentários**
   * Comentários não vão ajudar um código ruim ser melhor interpretado;
   * Um código que requer comentário, precisa ser reescrito;
   * Não deixe trechos de código comentado;
   * Quando comentar?
    * Alertar consequências que pode vir a causar;
    * Licença, direitos autorais, etc;
    * Necessidade de explicar uma regra de negócio interna;
    * Decisões de design de código (ex.: ToDo);

 - **Tratamento de erros**
   * Tratar e prever possíveis exceções é de responsabilidade do desenvolvedor (try e catch só se for muito expecífico), logar;
   * Retorne exceptions e não código de erro;
   * Informe o máximo que puder em sua exception, por meio de log;
   * Se necessário crie exceptions personalizadas para um problema eespecífico;
   * Não retorne null;
   * Regra dos escoteiros: "Deixe a área de acampamento mais limpa de como você a encontrou" (melhorar(refatorar) o maximo possivel o codigo que você esta alterando);
    

## Design Patterns
- São padrões de código para solução de problemas conhecidos;
- O objetivo é não reinventar a roda e aplicar uma solução com um bom design de código;
- O conceito de padrões foi introduzido por 4 desenvolvedores intitulados "Gang of Four" (GoF) e hoje conta com 23 padrões fundamentais;
- Atualmente existem mais de 80 padrões conhecidos que são em geral variações dos 23 patterns do GoF;
- Os padrões do GoF estão divididos em 3 famílias:
  1. **Creational Patterns**: Fornece meios de criação de um objeto e de como ele será instanciado;
      * **Abstract Factory**: Cria uma instância de diversas famílias de classes (Mais importante e utilizado);
      * **Factory Method**: Cria uma instância de diversas derivações de classes (Mais importante e utilizado);
      * **Singleton**: Cria uma única instância que será utilizada por os recursos ou uma única alocação na memória (N processor simultaneos);
  2. **Structural Patterns**: Tratam de composição de objetos por herança e interfaces para diferentes funcionalidades;
      * **Adapter**: Compatibiliza objetos de interfaces diferentes;
      * **Facade**: Uma única classe que representa um subsistema (muito utilizado em modelagem de dominio);
      * **Composite**: Compartilha um objeto em estruturas de árvores que representam hierarquias;
  3. **Behavioral Patterns**: Tratam das interações e comunicação entre objetos além da divisão de responsabilidaes;
      * **Command**: Encapsula um command request em um objeto;
      * **Strategy**: Encapsula um algoritmo dentro de uma classe (muito utilizado em modelagem de dominio, RNs, Seviços externos);
        * Excemplo: Strategy + Facade trabalham muito bem juntos na implementação de meios de pagamento;
      * **Observer**: Uma forma de notificar mudanças a uma série de classes (Observações e notificações);

**OBS: Evite Patternite** 
  - Patternite é o mal que o desenvolvedor sofre quando deseja aplicar todos os patterns conhecidos apenas para praticar ou por entender que quanto mais patterns melhor;
  - Não utilize sem conhecer;
  - Apesar de conhecer só utilize se necessário.

:link: Algumas referencias:

https://www.dofactory.com/net/design-patterns

https://refactoring.guru/pt-br/design-patterns/catalog

https://github.com/KevinDockx/CSharp10DesignPatterns

## Arquitetura de Software

- **Estilos Arquiteturais**

  * Um estilo arquitetural é uma abordagem de como projetar e entregar uma aplicação;
  * Trata-se de como organizar os componentes responsáveis de uma arquitetura, como eles irão interagir entre si
  e quais aspectos tecnológicos irão atender.

- **Arquitetura Monolítica**: é quando você tem toda a solução em um unico bloco ou projeto ou aplicação. (ja esta um pouco defasada, mas para resolver um problema mais simples, ja e o suficiente).

:link: Algumas referencias:

https://marquesfernandes.com/tecnologia/o-que-e-um-sistema-aplicacao-monolito-monolitica/

- **Arquitetura em camadas**: é um estilo de gerenciar uma arquitetura que divide as responsabilidades em camadas especificas (ex:. Apresentação, Service, Business e Data)

:link: Algumas referencias:

https://imasters.com.br/arquitetura-da-informacao/arquitetura-em-camadas

https://learn.microsoft.com/pt-pt/azure/architecture/guide/architecture-styles/n-tier

- **Arquitetura Rest**: é um padrão onde visa separar a forma que escreve a aplicação em APIs, bem utilizado em aplicações distribuidas (foi o primeiro passo para a ida aos microserviços)

:link: Algumas referencias:

https://arquiteturadesoftware.online/fundamentos-para-sistemas-com-arquiteturas-rest/

https://rockcontent.com/br/blog/rest/

- **Arquitetura de Microserviços**: em uma arquitetura de micro serviços, múltiplos serviços fracamente acoplados (ou seja, com poucas ou nenhuma dependência entre si) trabalham juntos

:link: Algumas referencias:

https://learn.microsoft.com/pt-pt/azure/architecture/guide/architecture-styles/microservices

https://www.ibm.com/br-pt/cloud/learn/microservices

- **SOA vs Microserviços**:

:link: Algumas referencias:

https://www.ibm.com/cloud/blog/soa-vs-microservices
	
https://www.guru99.com/microservices-vs-soa.html



## Padrões arquiteturais

- Os Padrões arquiteturais são semelhantes aos "Desing Patterns", mas possuem um escopo diferente.
- Padrões arquiteturais são estratégias de alto nível que dizem respeito a componentes de grande escala, as propriedades e mecanismos globais de um sistema.
- Um projeto de arquitetura pode conter diversos estilos arquiteturais, e cada estilo arquitetural pode utilizar diversos padrões arquiteturais. 
- Um padrão arquitetural pode ser um subconjunto de um estilo arquitetural visando um escopo especifico.
- Um padrão arquitetural é uma solução geral e reutilizavel para um problema em um contexto particular. É uma solução recorrente para um problema recorrente.


**Padrão arquitetura "3 camadas"** (clássica)

- Clássica maneira de distribuir responsabilidades (apresentação, aplicação [negócio], acesso a dado).
- Não deve ser menosprezada, pois nem sempre a complexidade é uma solução para problemas simples.
- Pode ser aplicada em diversos cenários, porém geralmente é mais encontrada em aplicações com foco comercial(cadastros, regras e etc).


**Padrão arquitetura "cebola" - Clean Architecture** (famosa)

- Essa arquitetura fornece uma alternativa robusta para criar aplicativos para uma melhor testabilidade, manutenção e 
confiabilidade nas infraestruturas como bancos de dados e serviços.


:link: Algumas referencias:

https://www.youtube.com/watch?v=sZPBvlmuvw4

https://www.macoratti.net/20/05/net_onion1.htm

https://medium.com/xp-inc/apreendendo-a-arquitetura-cebola-em-net-5-d2e06dcc9e8

https://learn.microsoft.com/en-us/dotnet/architecture/

:books: Livro: 

https://www.amazon.com/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164


**Padrão arquitetura Hexagonal "Ports & Adapters"**

- É um padrão apoiado sobre o uso de camadas, e que busca uma outra forma de representar e aplicar na prática as questões de organização, 
isolamento e dependência entre as camadas. Quando criado, teve como motivação os problemas citados no tema Camadas com relação a desorganização 
no uso de camadas e a infiltração de lógica de negócio em outras camadas.

:link: Algumas referencias:

https://learning.eximia.co/videos/descomplicando-arquitetura-hexagonal/

https://guia.dev/pt/pillars/software-architecture/layers-and-architecture-patterns.html#hexagonal-architecture

https://pt.linkedin.com/pulse/arquitetura-hexagonal-introdu%C3%A7%C3%A3o-e-estrutura-douglas-santana

https://medium.com/tableless/desvendando-a-arquitetura-hexagonal-52c56f8824c



## CQRS - Command Query Reponsability Segregation

- Um padrão arquitetural onde o foco principal é separar os meios de leitura e escrita de dados. Alterações de dados são realizados via Commands 
e leitura de dados são realizados via Queries.
- O objetivo do CQRS é prover expressividade para aplicação, pois todos os Commands representam uma intenção de negócio.
- CQRS promove a consistência eventual, que é quando possuímos um banco de leitura e outro de escrita com os mesmos dados, porém os dados não são consistidos
exatamente no mesmo momento.
- Muito aplicado em arquiteturas hexagonais, microservices ou em aplicações que possuem uma alta demanda de consumo de dados.

**Conceitos**:

  - Commands: Representam uma intenção de mudança no estado de uma entidade. São expressivos e representam uma única intenção de negócio, 
ex: AumentarSlarioFuncionarioCommand

  - Queries: É a forma de obter dados de um banco o origem de dados para atender as necessidades da aplicação

**Solução**:

  - Separar em 2 bancos um de leitura e outro de escrita, utilizando comandos para atualizar dados e consultas para ler dados.

**OBS**: O principal desafio do CQRS é manter as bases atualizadas.

:link: Algumas referencias:

https://learn.microsoft.com/pt-pt/azure/architecture/patterns/cqrs

https://www.eduardopires.net.br/2016/07/cqrs-o-que-e-onde-aplicar/



## Event Sourcing

- "Nós podemos buscar o estao de uma aplicação para encontrar o estado atual do mundo, e isso responde muitas perguntas. Entretanto há momentos que nós
não só queremos ver onde nós estamos, mas também queremos saber como chegamos lá." - Martin Fowler
- "Event Sourcing assegura que todas as mudanças feitas no estado de uma aplicação são armazenadascomo uma sequência de eventos. Não só podemos buscar esses eventos, 
mas também podemos usar este log de eventos para reonstruir estados passados e ajustar automaticamenteo estado atual com mudanças retroativas" Martin Fowler
- A ideia central é persistir todos estados anteriores de uma entidade de negócio desde o momento de sua criação. Com este dados é possível realizar o "replay"
dos fatos passados para entender o comportamento do usuário, trabalhr com Big Data, Machine Learning, realizar testes de integração com cenários reais ou 
simplesmente recriar as entidades necessário.

:link: Algumas referencias:

https://martinfowler.com/eaaDev/EventSourcing.html

https://learn.microsoft.com/en-us/azure/architecture/patterns/event-sourcing

https://medium.com/design-microservices-architecture-with-patterns/event-sourcing-pattern-in-microservices-architectures-e72bf0fc9274

https://docs.aws.amazon.com/prescriptive-guidance/latest/modernization-data-persistence/service-per-team.html

https://www.upsolver.com/blog/cqrs-event-sourcing-build-database-architecture



## DDD

- Introduzido em 2003 por Eric Evans;
- Indicado para aplicações complexas, com muitas entidades e regras de negócio;
- Razoavelmente fácil de entender, difícil de aplicar;
- Um guia de como entender um negócio, organizá-lo em um conjunto de princípios, criar uma modelagem com base no negócio e implementar utilizando diversas
boas práticas.

**Processo de "implementação" do DDD**:

- Entender o Negócio;
- Extrair a Linguagem Obliqua:
	- Vocabulário de todos os termos específicos do domínio: Nomes, verbos, adjetivos, jargões, apelidos, expressoes idiomaticas e adverbios;
	- Compartilhado por todas as partes envolvidas no projeto: Primeiro passo para evitar desentendimento;
	- Usadas em todas formas faladas e escritas de comunicação: A linguagem universal de um negócio é feita dentro da empresa.
- Modelagem Estratégica:
	- Extrair a Linguagem Ubiqua vai colaborar na visao e entendimento do negocio e como segregar seu dominio em partes menores e responsaveis;
	- Para documentar estar segregações responsaveis utilizamos o Mapa de Contextos(Context Map) que pode ser representado atraves de imagens e 
	uma simples documentação do tipo de relacionamento entre os contextos;
	- Cada contexto delimitado possui sua propria Linguagem Ubiqua, pois em contextos diferentes, os termos podem ter significados diferentes.
- Definir a Arquitetura: ver imagem anexada ao projeto
- Modelagem Tática;
	- Aggregate Object: Uma entidade que é raiz agregadora de um processo de dominio que envolve mais de uma entidade.
	- Domain Model: Uma entidade do dominio, possui estados e comportamentos, logica de negocio, getters e setters AdHoc, etc.
	- Value Object: Um objeto que agrega valor as entidades, não possui identidade e é imutavel.
	- Factory: Classe responsavel por construir adequadamente um objeto/entidade.
	- Domain Service: Serviço do dominio que atende partes do negocio que nao se encaixam em entidades especificas, trabalha com diversas entiodades, realiza
	persistencia atraves de repositorio e etc.
	- Application Service: Serviço de aplicação que orquestra açoes disparadas pela camada de apresentação e fornece DTOs para comunicação entre as demais
	camadas e para o consumo da camada de apresentação.
	- Repository: Uma classe que realiza a persistencia das entidades se comunicando diretamente com o meio de acesso aos dados, é utilizado apenas um
	repositorio por agregação.
	- External Service: Serviço externo que realiza a consulta/persistencia de infomações por meios diversos.

:link: Algumas referencias:

https://www.google.com/search?rlz=1C1GCEA_enPT1016PT1016&biw=2133&bih=1076&q=Domain-Driven+Design:+Tackling+Complexity+in+the+Heart+of+Software&stick=H4sIAAAAAAAAAOOQUeLVT9c3NEwuyKowNTWsMuJMSUlRSMrPzy6O4gYxCxJLSlKL8k4x8oDUGSWZx1uYGqWcYkTVBuOnZRuaFFRVFsH46fF52QVFVZYw7UaG5mXmhcVw03Itsw0tTH8xcrq4uEBsbWBhXMTq5JKfm5iZp-tSlFmWmqfgklqcmZ5npRCSmJydk5mXruCcn1uQk1qRWVKpkJmnUJKRquCRmlhUopCfphCcn1ZSnliUeotNksH0YytT-If3iU9EP9VVCZzv23OodlqL3QV_AEQsfU_2AAAA&sa=X&ved=2ahUKEwj--tXRjJL7AhWWBhoKHSHWCdoQs9oBKAF6BAg5EAM

https://medium.com/beelabacademy/domain-driven-design-vs-arquitetura-em-camadas-d01455698ec5

https://fullcycle.com.br/domain-driven-design/

https://www.eduardopires.net.br/2016/03/ddd-bounded-context/

https://martinfowler.com/tags/domain%20driven%20design.html

https://www.eduardopires.net.br/2016/08/ddd-nao-e-arquitetura-em-camadas/

https://github.com/VaughnVernon/IDDD_Samples



## Arquiteturas Evolutivas

- "Um arquiteto permite que decisões importantes sejam adiadas e um bom arquiteto maximiza o número de decisões não tomadas." - Uncle Bob
- "Uma arquitetura evolutiva suporta mudanças continuas e incrementais como um primeiro principio por meio de varios aspectos." - Rebecca Parsons
- "Mudanças são inevitaveis. A evolução, no entanto, é opcional." - Tony Robbins



**Sempre considere a complexidade!**

- Acidental: Complexidade acidental é aquela que surge durante o processo de desenvolvimento, ou seja, ela é CAUSADA pela abordagem escolhida para
resolver o problema.
- Esencial: Já a essencial é basicamente a complexidade que nosso "software" se propoe resolver. SIM, infelizmente existem problemas complexos, 
e é neles que temos que focar

:link: Algumas referencias:

https://github.com/EduardoPires/EquinoxProject



## Conway's Law

- "Qualquer empresa que projeta um sistema, inevitavelmente produz um projeto cuja estrutura é uma cópia da estrutura 
de comunicaçao da organização." - Melvin Conway

:link: Algumas referencias:

http://scrumbook.org/product-organization-pattern-language/conway-s-law.html



## Agilidade e o manifesto agil

- Individuos e interações mais que processos e ferramentas;
- Software em funcionamento mais que documentação abrangente;
- Colaboração com o cliente mais que negociação de contratos;
- Responder a mudanças mais que seguir um plano.

:link: Algumas referencias:

https://agilemanifesto.org/



## DevOps

- O termo DevOps deriva da junção das palavras "desenvolvimento" (development) e "operações" (operations), sendo uma pratica de engenharia de software
que possui o intuito de unificar o desenvolvimento de software (Dev) e a operação de software (Ops);
- A caracteristica principal do movimento DevOps é defender fortemente a automação e monitoramento em todas as fases da construção do software, 
da integração, teste, liberação para implantação e gerenciamento de infraestrutura;
- DevOps pretende fornecer, em ciclos de desenvolvimento menores, frequencia de implantação aumentada, liberações mais seguras, em alinhamento proximo 
com os objetivos de negocios.



## Principios DRY, KISS e YAGNI

- **Principios DRY** - Dont Repeat Yourself: Cada parte do conhecimento deve ter uma representação unica, nao ambigua e definitiva dentro da aplicação

- **Principio KISS** - Keep it simple, stupid: O KISS valoriza a simplicidade do projeto e defende que toda a complexidade desnecessaria seja descartada.

- **Principio YAGNI** - You aint gonna need it: Uma orientação que sugere nao adicionar funcionalidades ao codigo fonte de uma aplicaçao ate que estas 
sejam realmente necessarias.

:link: Algumas referencias:

https://pt.linkedin.com/pulse/princ%C3%ADpios-yagni-kiss-e-dry-emerson-romano

https://dev.to/urielsouza29/kiss-yagni-dry-tres-principios-que-todo-desenvolvedor-deveria-conhecer-47gg

https://danielsmanioto.com/blog/2020/01/18/dry-yagni-kiss-principios-de-design-de-software-que-todo-desenvolvedor-deveria-seguir/



## Leituras recomendadas

:books: Livros:

- Clean Code (1º) - Robert C. martin
- The Clean Coder (2º) - Robert C. Martin
- Clean Architecture (3º) - Robert C. Martin
- Patterns of Enterprise Application Architecture - Martin Fowler
- Computer Science - Robert Sedgewick e Kevin Wayne
- Domain-Drive Design (1º) - Eric Evans
- Implementing Domain Driven Design (2º) - Vaughn Vernon
- Domain-Driven Design Distilled (3º) - Vaughn Vernon
- C# 10 - Mark J. Price
- Desing Pattern - gang of 4
- Desingning Data-Intensive Applications - Martin Kleppmann
- The Effective Enginner - Edmond Lau
- Code Complete - Steve McConnell
- Docker Deep Dive - Nigel Poulton
- Concurrency in C# Cookbook: Asynchronous, Parallel, and Multithreaded Programming 2nd Edition - Stephen Cleary
- Apps and Services with .NET 7: Build Practical Projects with Blazor, .NET MAUI, GRPC, GraphQL, and Other Enterprise Technologies - Mark J. Price
- C# 11 and . NET 7 - Modern Cross-Platform Development Fundamentals: Start Building Websites and Services with ASP. NET Core 7, Blazor, and EF Core 7, 7th Edition - Mark J. Price 

## Outros:

- **Alternativa ao Automapper**

	https://riptutorial.com/csharp/example/19238/using-extension-methods-to-create-beautiful-mapper-classes


- **EventstoreDB**: base de dados para Event Sourcing (banco de dados funcional com Complex Event Processing em JavaScript)

	https://www.eventstore.com/


- **Rebus**

	https://github.com/rebus-org/Rebus


- **Docker**: é um conjunto de produtos de plataforma como serviço que usam virtualização de nível de sistema operacional para entregar software em pacotes chamados contêineres. Os contêineres são isolados uns dos outros e agrupam seus próprios softwares, bibliotecas e arquivos de configuração.

	https://www.docker.com/


- **RabbitMQ**: é um software de mensagens com código aberto, que implementou o protocolo "Advanced Message Queuing Protocol", que foi estendido com uma arquitetura de plug-in para suportar o protocolo "Streaming Text Oriented Messaging Protocol", o MQTT entre outros protocolos

	https://www.rabbitmq.com/


- **Dapr**: é um sistema de tempo de execução gratuito e de código aberto projetado para suportar computação nativa em nuvem e sem servidor. Sua versão inicial suportava SDKs e APIs para Java, .NET, Python e Go e tinha como alvo o sistema de implantação de nuvem Kubernetes.

	https://dapr.io/

	https://github.com/renatogroffe/ASPNETCore7-REST_API-Dapr-StateManagement_ContagemAcessos

	https://learn.microsoft.com/en-us/dotnet/architecture/dapr-for-net-developers/


## Alguns ORMs

* **Dapper**: um micro ORM que pode ser usado em aplicações menos complexas.

	https://github.com/DapperLib/Dapper

	https://www.learndapper.com/

	https://www.macoratti.net/19/09/cshp_dapb1.htm


* **Entity Framework**: é uma ferramenta ORM (Object-relational mapping) que permite ao desenvolvedor trabalhar com dados relacionais na forma de objetos específicos do domínio.

	https://learn.microsoft.com/en-us/ef/

	https://www.entityframeworktutorial.net/efcore/entity-framework-core.aspx

	https://www.macoratti.net/17/05/efcore_ini1.htm

	https://www.simplilearn.com/tutorials/asp-dot-net-tutorial/entity-framework-in-c-sharp


* **NHibernate**: é um framework para realizar o mapeamento objeto/relacional de modo a transformar os dados da estrutura lógica de um banco de dados relacional em objetos definidos no domínio de uma aplicação. Ele também realiza a persistência de objetos em banco de dados relacionais.

	https://nhibernate.info/

	https://github.com/nhibernate/nhibernate-core

	https://www.macoratti.net/19/07/aspnc_nhib1.htm
