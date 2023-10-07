## main

Toda aplicação escrita em `dart` precisará de uma função `void` chamada `main`. Aqui é onde começa a execução do projeto.

Exemplo:

```dart
void main() {
	// código
}
```


# Variáveis

Mesmo no código Dart, com o null safety, é possível declarar a maioria das variáveis ​​sem especificar explicitamente seu tipo usando a palavra-chave `var`. Graças à inferência de tipos, os tipos dessas variáveis ​​são determinados pelos seus valores iniciais:

Exemplo:

```dart
var name = 'Voyager I';
var year = 1977;
var antennaDiameter = 3.7;
var flybyObjects = ['Jupiter', 'Saturn', 'Uranus', 'Neptune'];
var image = {
  'tags': ['saturn'],
  'url': '//path/to/saturn.jpg'
};
```

## Estruturas de controles de estado

O Dart suporta as comuns estruturas para controles de estado.

Exemplo:

```dart
if (year >= 2001) {
  print('21st century');
} else if (year >= 1901) {
  print('20th century');
}

for (final object in flybyObjects) {
  print(object);
}

for (int month = 1; month <= 12; month++) {
  print(month);
}

while (year < 2016) {
  year += 1;
}
```

## Funções

A documentação oficial do Dart recomenda especificar o tipo de cada função e retornar algum valor:

```dart
int fibonacci(int n) {
  if (n == 0 || n == 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}

var result = fibonacci(20);
```

Uma sintaxe abreviada `=>` (_arrow function_) é útil para funções que contêm uma única instrução. Esta sintaxe é especialmente útil ao passar funções anônimas como argumentos:

```dart
flybyObjects.where((name) => name.contains('turn')).forEach(print);
```

Além de mostrar uma função anônima (o argumento para `where()`), este código mostra que você pode usar uma função como argumento: a função de nível superior `print()` é um argumento para `forEach()`.

## Imports

Para acessar APIs definidas em outras bibliotecas, use `import`.

```
// Importando bibliotecas principais
import 'dart:math';

// Importando bibliotecas de pacotes externos
import 'package:test/test.dart';

// Importando arquivos
import 'path/to/my_other_file.dart';
```