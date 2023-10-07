O propósito do Dart é baseado no mesmo que o Java. Na aba "Overview" do site ele possui esta descrição:

"Dart é uma linguagem otimizada para cliente para desenvolver aplicativos rápidos em qualquer plataforma."

Segundo a documentação da linguagem, "as linguagens de programação são definidas pelo seu *envelope técnico* - as escolhas feitas durante o desenvolvimento que moldam a capacidade e a força da linguagem".

# Dart - A linguagem

O Dart é uma linguagem construída em cima de um envelope técnico que, particularmente, é adequado para o desenvolvimento de *client*, priorizando o desenvolvimento (com recargas dinâmicas com estados em menos de um segundo) e abrangendo uma variedade de alvos de compilação (web, desktop e mobile). O Dart também forma a base para o Flutter (framework inspirado no React, voltado para o desenvolvimento UI), fornecendo a linguagem e os tempos de execução que alimentam os aplicativos Flutter, mas o Dart também oferece suporte a muitas tarefas básicas do desenvolvedor, como formatação, análise e teste de código.

Dart é baseado em *type safe* (verifica o tipo estático para garantir que o valor de uma variável sempre corresponda ao tipo estático da variável). Algumas vezes isso é chamado de *sound typing* (digitação sonora). Embora os tipos sejam obrigatórios, também é possível optar pela alternativa de inferência, utilizando-se de palavras chaves que automaticamente atribuem o tipo estático da variável, de acordo com o valor atribuído a ela. É interessante também citar acerca do flexível tipo `dynamic` combinado a verificações de tempo de execução que podem ser muito úteis durante testes ou para códigos que precisem serem especialmente dinâmicos.

O Dart possui o `null safety` integrado, o que significa que os valores não podem serem nulos, a menos que seja inferido que aquele valor pode receber o tipo nulo. Com a segurança de nulabilidade, o Dart protege o desenvolvedor de `null exceptions` em tempo de execução por meio de análise estática de código. Ao contrário de muitas outras linguagens seguras para nulos, quando o Dart determina que uma variável não é anulável, essa variável nunca pode ser nula. Caso o desenvolvedor queria inspecionar o código em execução no depurador, verá que a não nulidade é mantida em tempo de execução; portanto, parece segurança nula.

# Dart - Bibliotecas

Dart tem um incrível e rico set de bibliotecas. Alguma delas são:

- `dart:core`: tipos incorporados, coleções e outras funcionalidades essenciais para todo programa Dart;
- `dart:collection`: tipos de coleção mais ricos, como filas, listas encadeadas, mapas de hash e árvores binárias;
- `dart:convert`: codificadores e decodificadores para a conversão entre diferentes representações de dados, incluindo JSON e UTF-8;
- `dart:math`: Constantes e funções matemáticas, e geração de números aleatórios;
- `dart:io`: suporte de E/S para arquivos, sockets, HTTP e outras operações para aplicativos não web;
- `dart:async`: suporte para programação assíncrona, com classes como Future e Stream;
- `dart:typed_data`: listas que manipulam eficientemente dados de tamanho fixo (por exemplo, inteiros sem sinal de 8 bytes) e tipos numéricos SIMD;
- `dart:ffi`: interfaces de função estrangeira para interoperabilidade com outros códigos que apresentam uma interface no estilo C;
- `dart:isolate`: programação concorrente usando isolados - trabalhadores independentes semelhantes a threads, mas que não compartilham memória e se comunicam apenas por meio de mensagens;
- `dart:html`: elementos HTML e outros recursos para aplicativos baseados na web que precisam interagir com o navegador e o Modelo de Objeto do Documento (DOM);

Além das bibliotecas principais, muitas APIs são fornecidas por meio de um conjunto abrangente de pacotes. A equipe Dart publica muitos pacotes complementares úteis, como:

- characters
- intl
- http
- crypto
- markdown

Além disso, editores terceirizados e a comunidade em geral publicam milhares de pacotes, com suporte para recursos como estes:

- XML
- Windows integration
- SQLite
- compression

## Dart - Plataformas

As tecnologias do compilador do Dart, permitem o desenvolvedor escrever código de duas formas diferentes:

- `Plataforma nativa`: para aplicativos direcionados a dispositivos móveis e desktop, o Dart inclui uma VM Dart com compilação just-in-time (JIT) e um compilador antecipado (AOT) para produzir código de máquina;
- `Plataforma web`: para aplicativos direcionados à web, o Dart pode compilar para fins de desenvolvimento ou produção. Seu compilador web traduz Dart em JavaScript.
![An illustration of the targets supported by Dart](https://dart.dev/assets/img/Dart-platforms.svg)

O framework Flutter é um kit de ferramentas de UI multiplataforma popular desenvolvido pela plataforma Dart e que fornece ferramentas e bibliotecas de UI para criar experiências de UI que são executadas em iOS, Android, macOS, Windows, Linux e na web.

## Dart Native (código de máquina JIT e AOT)

Durante o desenvolvimento, um ciclo de desenvolvimento rápido é fundamental para a iteração. O Dart VM oferece um compilador just-in-time (JIT) com recompilação incremental (permitindo recarga a quente), coleções de métricas ao vivo (alimentando [DevTools](https://dart.dev/tools/dart-devtools) ) e suporte avançado de depuração.

Quando os aplicativos estão prontos para serem implantados na produção, seja publicando em uma loja de aplicativos ou implantando em um back-end de produção, o compilador Dart ahead of time (AOT) pode compilar para código de máquina ARM nativo ou x64. Seu aplicativo compilado AOT é iniciado com um tempo de inicialização curto e consistente.

O código compilado AOT é executado dentro de um tempo de execução Dart eficiente que reforça o sistema sonoro do tipo Dart e gerencia a memória usando alocação rápida de objetos e um [coletor de lixo geracional](https://medium.com/flutter-io/flutter-dont-fear-the-garbage-collector-d69b3ff1ca30) .

Mais Informações:

- [Primeiros passos: aplicativos de linha de comando e de servidor](https://dart.dev/tutorials/server/get-started)
- [`dart`ferramenta para execução com compilação JIT ou AOT para código de máquina](https://dart.dev/tools/dart-tool)
- [Escreva aplicativos de linha de comando](https://dart.dev/tutorials/server/cmdline)
- [Escreva servidores HTTP](https://dart.dev/tutorials/server/httpserver)

## Dart Web (desenvolvimento e produção de JavaScript)

O Dart Web permite a execução de código Dart em plataformas web alimentadas por JavaScript. Com o Dart Web, você compila o código Dart em código JavaScript, que por sua vez é executado em um navegador, por exemplo, [V8](https://v8.dev/) dentro [do Chrome](https://www.google.com/chrome/) .

O Dart web contém dois modos de compilação:

- Um compilador de desenvolvimento incremental que permite um ciclo de desenvolvimento rápido
- Um compilador de produção otimizador que compila código Dart para JavaScript rápido, compacto e implantável. Essas eficiências vêm de técnicas como a eliminação de código morto.

Mais Informações:

- [Primeiros passos: aplicativos da Web](https://dart.dev/tutorials/web/get-started)
- [`dart compile js`](https://dart.dev/tools/dart-compile#js)
- [`webdev`ferramenta](https://dart.dev/tools/webdev)
- [Dicas de implantação da Web](https://dart.dev/web/deployment)

#### O tempo de execução do Dart

Independentemente de qual plataforma você usa ou como você compila seu código, a execução do código requer um tempo de execução Dart. Este tempo de execução é responsável pelas seguintes tarefas críticas:

- Gerenciando memória: o Dart usa um modelo de memória gerenciada, onde a memória não utilizada é recuperada por um coletor de lixo (GC).

- Aplicando o sistema de tipo Dart: embora a maioria das verificações de tipo no Dart sejam estáticas (tempo de compilação), algumas verificações de tipo são dinâmicas (tempo de execução). Por exemplo, o tempo de execução do Dart impõe verificações dinâmicas por [verificação de tipo e operadores de conversão](https://dart.dev/language/operators#type-test-operators)
- Gerenciando [isolados](https://dart.dev/language/concurrency) : o tempo de execução do Dart controla o isolado principal (onde o código normalmente é executado) e quaisquer outros isolados criados pelo aplicativo

Em plataformas nativas, o tempo de execução do Dart é automaticamente incluído em executáveis ​​independentes e faz parte da VM do Dart fornecida pelo comando [`dart run`](https://dart.dev/tools/dart-run).