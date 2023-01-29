## RESUMO

### Classe x Objeto

- Classe: Definição de Classe: é uma estrutura de código ou dados que tem a função de mapear o objeto do mundo real;
- Objeto: Definição de Objeto: é quando tem uma classe sendo instanciada e alocada na memória;

### Pilares OOP

- O **estado** é representado através de PROPRIEDADES de uma classe;
- O **comportamento** é quando gera ou processa uma informação, através de um MÉTODO da classe ou altera o estado da classe (modifica o valor da propriedade);
- A **herança** permite que você crie novas classes que reutilizam, estendem e modificam o comportamento definido em outras classes;
  - Sempre pense no É UM exemplo: um funcionário É UMA pessoa, se não fizer sentido é porque não deva fazer herança ou é realmente necessário;
- **Classe abstrata**: Sempre tem que ser herdada e não pode ser instanciada, oferecem um cojunto de estado(propriedade) e comportamento(método) que abstraem uma certa especialização;
  - OBS: o conceito de abstração é a base para o polimorfismo e o encapsulamento;
  - **Métodos abstratos** não são obrigados a implementar o comprotamento na classe base, só a classe derivada (classe que estiver herdando, que são obrigatórios);
  - **Métodos virtual** podem ter a implementação do comportamento na classe base e ao herdar a classe, posso alterar seu comportamento na classe derivada (override não é obrigatório);
- **Poli-morfismo**: a classe derivada pode assumir diveros comportamentos;
- **Encapsulamento**: é a arte de encapsular comportamentos(métodos) através da exposição de métodos PUBLIC e esconder certos comportamentos a escrita de métodos PRIVATE (preservando certas implementações);

### Interface

- **Interface**: é uma espécie de contrato, então toda classe que implementa uma interface ela é obrigada a implementar seus métodos;

### Modificadores
- **classe selada** só pode ser instanciada e não herdada;
- **Classe e Método PUBLIC**: Access is not restricted;
- **Classe e Método PROTECTED**: Access is limited to the containing class or types derived from the containing class;
- **Classe e Método INTERNAL**: Access is limited to the current assembly;
- **Método PROTECTED INTERNAL**: Access is limited to the current assembly or types derived from the containing class;
- **Classe e Método PRIVATE**: Access is limited to the containing type;
- **Método PRIVATE PROTECTED**: Access is limited to the containing class or types derived from the containing class within the current assembly.Available since C# 7.2;

### Princípios SOLID

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

### Dependency Injection

- **Transient**: Modelo padrão (quando não se sabe como usar, seria a melhor escolha), vai ser criada toda vez que for injetada em alguma classe, funciona melhor em objetos leves ou serviços sem estado (ocupa mais memória, porque toda vez que é requisitado cria uma instancia);
- **Scoped**: Os objetos são criados uma vez por client request (por conexão), muito utilizado em aplicações Web;
- **Singleton**: Cria uma unica instancia para toda a aplicação (todo o tempo de execução da aplicação);

https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-3.1
https://www.palmmedia.de/blog/2011/8/30/ioc-container-benchmark-performance-comparison
https://simpleinjector.readthedocs.io/en/latest/index.html

### Clean Code
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
    
 - Menos é mais!
  * "A primeira regra dos métodos é que eles devem ser pequenos. A segunda regra é que eles devem ser menores ainda." (Uncle Bob)
  * Método <= 20 linhas;
  * Linha <= 100 caracteres;
  * Classe <= 500 linhas;

 - Métodos
  * Extraia trechos em métodos privados;
  * Métodos devem fazer apenas uma coisa, fazê-la certa e somente faze-la;
  * Evite muitos parâmetros(ex. criar DTO);
  * Não deixe o método mentir dizendo que faz uma coisa e faz outras "escondidas";
  * Se o método tiver mais de uma responsabilidade extraia em dois ou mais (cada um com sua responsabilidade);
  * Leia seu método de cima para baixo como uma narrativa, ele deve fazer sentido;
  * Aplique uma boa indentação;

 - Comentários
  * Comentários não vão ajudar um código ruim ser melhor interpretado;
  * Um código que requer comentário, precisa ser reescrito;
  * Não deixe trechos de código comentado;
  * Quando comentar?
    * Alertar consequências que pode vir a causar;
    * Licença, direitos autorais, etc;
    * Necessidade de explicar uma regra de negócio interna;
    * Decisões de design de código (ex.: ToDo);

 - Tratamento de erros
  * Tratar e prever possíveis exceções é de responsabilidade do desenvolvedor (try e catch só se for muito expecífico), logar;
  * Retorne exceptions e não código de erro;
  * Informe o máximo que puder em sua exception, por meio de log;
  * Se necessário crie exceptions personalizadas para um problema eespecífico;
  * Não retorne null;
  * Regra dos escoteiros: "Deixe a área de acampamento mais limpa de como você a encontrou" (melhorar(refatorar) o maximo possivel o codigo que você esta alterando);
    

### Design Patterns
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

https://www.dofactory.com/net/design-patterns
