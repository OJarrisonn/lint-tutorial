# Tutorial Linters

## O que é um linter

Linters são ferramentas de análise estática de código que servem para detectar problemas semâticos do código que o compilador não pode detectar e que podem prejudicar a execução do programa ou a manutenibilidade do código.

Linters possuem uma configuração que pode ser personalizada para determinar como inspecionar o código através de regras e níveis.

Uma regra diz qual tipo de padrão o linter deve inspecionar no código. Existem regras para os mais diversos padrões, por exemplo: usar nomes `camelCase`, uso de notações de tipo (em linguagens dinâmicas), checar tamanho das funções, checagem de valores nulos, etc. 

Para cada regra se define o nível de severidade de uma infração dessa regra, em geral os níveis são: desligado, alerta e erro. Podemos configurar uma regra para usar nomes `snake_case` com nível de erro, desse modo, assim que uma variável não atender esse padrão o linter emite um erro.

## Javascript ESLint

> Referência https://eslint.org/

Adicione o ESLint ao seu projeto Node com

```sh
npm install --save-dev eslint @eslint/js
```

Crie o arquivo de configurações `eslint.config.js` e inicie com o setup padrão:

```js
import js from "@eslint/js";

export default [
    js.configs.recommended,
   {
       rules: {
           "no-unused-vars": "warn",
       }
   }
];
```

Veja todas opções de [configuração](https://eslint.org/docs/latest/use/configure/) e a [lista de regras](https://eslint.org/docs/latest/rules/).

Para executar o linter rode (na raiz do projeto):

```sh
npx eslint . # vai analisar todos arquivos do diretório atual
npx eslint . --fix # analisa e corrige os arquivos 
```

Editores de texto tem suporte a extensões para integrar o ESLint ao seu fluxo de trabalho. A extensão ESLint do VS Code executa a análise em tempo real, mostra problemas no código e fornece ações de código para aplicar correções.

## Python Pylint

> Referencia https://www.pylint.org/

Instale o pylint disponível no PyPI

```sh
pip install pylint
```

Crie o arquivo de configurações padrão

```sh
pylint --generate-rcfile
```

O arquivo é dividido em seções, uma para cada verificador (_checker_), você pode ver os diferentes [recursos](https://pylint.pycqa.org/en/latest/user_guide/configuration/all-options.html) (no formato de opções para a linha de comando) e mais [detalhes](https://pylint.pycqa.org/en/latest/user_guide/checkers/features.html)

Você pode passar as opções de linha de comando para o comando `pylint --generate-rcfile` e assim gerar um arquivo com as opções desejadas.

Para executar o linter rode (na pasta do projeto):

```sh
pylint . # vai analisar todos arquivos no diretório atual
```

Editores de texto tem suporte a extensões para integrar o Pyint ao seu fluxo de trabalho. A extensão Pylint do VS Code executa a análise em tempo real, mostra problemas no código e fornece ações de código para aplicar correções.

## Rust Clippy



## Kotlin Klint