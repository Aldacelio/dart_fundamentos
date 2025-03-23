# DART FUNDAMENTOS

## Nomeclaturas

- `snake_case` para nomes de arquivos:
  - `calculation_age.dart`
  - `user_repository.dart`

- `camelCase` para variáveis, atributos e métodos;
  - `String userName`
  - `void calculateTotal()`

- `PascalCase` para classes, enum e interfaces;
  - `class UserModel`
  - `enum StatusOrder`

- `SCREAMING_SNAKE_CASE` para constantes.
  - `const double PI = 3.14`
  - `const String API_URL = "https://api.exemplo.com"`

## Tipos no Dart

- No Dart não existem tipos primitivos - tudo na linguagem são objetos
- Mesmo os tipos básicos como `int`, `double` e `bool` são objetos que herdam de `Object`
- Isso permite que você possa chamar métodos diretamente nestes tipos

### Exemplos práticos:

```dart
void main() {
  // Números como objetos
  int number = 42;
  print(number.isEven);      // true - verifica se é par
  print(number.toString());   // "42" - converte para String
  
  // Double como objeto
  double pi = 3.14;
  print(pi.round());         // 3 - arredonda para inteiro
  print(pi.toStringAsFixed(1)); // "3.1" - formata com 1 casa decimal
  
  // String como objeto
  String name = "Dart";
  print(name.toUpperCase()); // "DART"
  print(name.length);        // 4 - tamanho da string
  
  // Boolean como objeto
  bool active = true;
  print(active.toString());   // "true"
  
  // Demonstração de que todos são Object
  print(number is Object);   // true
  print(pi is Object);       // true
  print(name is Object);     // true
  print(active is Object);    // true
}
```

### Diferenças entre Dart e Java:

| Característica | Dart | Java |
|---------------|------|------|
| Tipos básicos | Todos são objetos | Possui tipos primitivos (`int`, `double`, `boolean`) |
| Wrapper Classes | Não necessárias | Necessárias (`Integer`, `Double`, `Boolean`) |
| Métodos | Disponíveis diretamente | Precisa converter para wrapper class |

## Nível Superior

- Variáveis e funções de nível superior são declaradas fora de qualquer classe
- São acessíveis em todo o arquivo e podem ser importadas por outros arquivos
- São úteis para constantes, utilitários e configurações globais

### Exemplos

```dart
// Variáveis de nível superior
String name = 'Minha Aplicação';
const double FEES = 0.08;

// Função de nível superior
int soma(int a, int b) {
  return a + b;
}

// Exemplo de uso dentro de uma classe
class Calculator {
  double calculateFees(double value) {
    return value * FEES; // Acesso à constante de nível superior
  }
}

void main() {
  print(appName);        // Acesso direto à variável
  print(soma(10, 20));   // Acesso direto à função
  
  var calc = Calculator();
  print(calc.calculateFees(100)); // Usa FEES internamente
}
```

## Comandos do Dart

### Criar um projeto
```bash
dart create -t <template> nome-do-projeto
```

### Tipos de Projeto (Templates)

1. **cli**
   - Projeto básico para aplicações de linha de comando.
   - Focado em aplicações de linha de comando com parsing de argumentos usando o pacote `package:args`.
   - Ideal para scripts que precisam processar argumentos de linha de comando.

2. **console**
   - Projeto básico para aplicações de linha de comando.
   - Estrutura simples com um arquivo `main.dart`.
   - Não inclui parsing de argumentos por padrão, mas você pode adicionar manualmente.
   - Ideal para scripts e utilitários.

3. **package**
   - Para criar bibliotecas/pacotes Dart.
   - Inclui estrutura para publicação no pub.dev.
   - Configuração inicial para documentação.

4. **server-shelf**
   - Projeto base para servidor web usando Shelf.
   - Inclui configuração básica de rotas.
   - Pronto para desenvolvimento de APIs.

5. **web**
   - Projeto para aplicações web.
   - Inclui um arquivo `index.html` básico e um arquivo `main.dart`.
   - Configurado para compilação de Dart para JavaScript usando o `webdev`.

### Comandos Úteis

```bash
# Criar novo projeto
dart create -t cli meu_projeto

# Executar projeto
dart run

# Compilar projeto
dart compile exe bin/main.dart

# Instalar dependências
dart pub get

# Atualizar dependências
dart pub upgrade

# Rodar testes
dart test
```

### Estrutura básica de um projeto CLI

```
meu_projeto/
├── bin/
│   └── main.dart
├── lib/
│   └── meu_projeto.dart
├── test/
│   └── meu_projeto_test.dart
├── analysis_options.yaml
├── CHANGELOG.md
├── README.md
└── pubspec.yaml
```
