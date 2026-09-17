# Pokedex

Uma Pokedex simples feita com **HTML, CSS e JavaScript puro**, que consome a [PokeAPI](https://pokeapi.co/) para exibir todos os Pokémon existentes, com busca por nome e filtro por tipo.

## 🎮 Demonstração

Ao abrir a página, a aplicação carrega automaticamente todos os Pokémon (1 a 1008) e exibe cada um em um card colorido de acordo com seu tipo primário, mostrando:

- Sprite (imagem) do Pokémon
- Número da Pokedex e nome
- Ícone(s) do(s) tipo(s)

## ✨ Funcionalidades

- **Listagem completa**: busca todos os Pokémon da PokeAPI ao carregar a página.
- **Busca por nome**: campo de texto que filtra os cards conforme o usuário digita.
- **Filtro por tipo**: menu suspenso (`select`) com todos os 18 tipos de Pokémon, permitindo filtrar por tipo primário ou secundário.
- **Cards estilizados por tipo**: cada card recebe a cor de fundo correspondente ao tipo do Pokémon.

## 🛠️ Tecnologias utilizadas

- **HTML5**
- **CSS3** (fonte `Press Start 2P` do Google Fonts, para um visual estilo "game boy")
- **JavaScript** (Fetch API, `async/await`, `Promise.all`)
- **[PokeAPI](https://pokeapi.co/)** — API pública com dados de todos os Pokémon

## 📁 Estrutura do projeto

```
├── API_pokemon.html   # Página principal (HTML + CSS + JS)
├── Bug.png
├── Dark.png
├── Dragon.png
├── Electric.png
├── Fairy.png
├── Fighting.png
├── Fire.png
├── Flying.png
├── Ghost.png
├── Grass.png
├── Ground.png
├── Ice.png
├── Normal.png
├── Poison.png
├── Psychic.png
├── Rock.png
├── Steel.png
└── Water.png
```

As imagens `.png` são os ícones de cada tipo de Pokémon, usados nos cards para indicar o(s) tipo(s) de cada um.

> ⚠️ Os nomes dos arquivos de imagem devem estar em **letras minúsculas** (ex: `fire.png`, `water.png`) para corresponder ao que o código busca (`${pk.type.name}.png`), já que a PokeAPI retorna os nomes dos tipos em minúsculo.

## ▶️ Como executar

1. Baixe ou clone os arquivos do projeto.
2. Coloque o arquivo `API_pokemon.html` na mesma pasta que as imagens dos tipos.
3. Abra o arquivo `API_pokemon.html` diretamente no navegador (não é necessário servidor).

> É necessário estar conectado à internet, pois os dados são buscados em tempo real na PokeAPI.

## 🔍 Como funciona (resumo técnico)

1. **Carregamento inicial** (`carregarApi()`): gera URLs para os Pokémon de ID 1 a 1008 e faz o fetch de todos em paralelo com `Promise.all`.
2. **Montagem dos cards** (`montarCards()`): gera o HTML de cada card dinamicamente a partir dos dados recebidos.
3. **Estilização por tipo** (`cssCard()`): aplica a cor de fundo do card com base no tipo primário do Pokémon, usando a lista `coresTipos`.
4. **Filtro por tipo**: ao selecionar um tipo no `select`, o código filtra os Pokémon (verificando tipo primário e secundário) e remonta os cards.
5. **Busca por nome**: a cada caractere digitado, o código filtra os Pokémon cujo nome começa com o texto digitado.

## 📚 Créditos

- Dados fornecidos pela [PokeAPI](https://pokeapi.co/)
- Fonte "Press Start 2P" via [Google Fonts](https://fonts.google.com/specimen/Press+Start+2P)
