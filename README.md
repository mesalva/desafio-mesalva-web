# Desafio Me Salva! - Web

Esse repositório foi criado para explicar o desafio técnico aplicado para candidatos à nossa vaga de pessoa desenvolvedora web.

## Contexto

O desafio será implementar um "console de aulas", que apresente conteúdos variados (vídeo, texto e exercício) relacionados à uma lista de estudos. O desafio deverá conter as seguintes funcionalidades:

- Lista de conteúdos
- Apresentação de um conteúdo completo
- Cada item da lista de conteúdos deverá ter um identificador do seu tipo (vídeo, texto e exercício)
- Ao clicar em um item da lista o seu conteúdo relacionado deverá ser mostrado
- Após um conteúdo ter sido consumido (respondido/assistido) deverá ser sinalizado para o usuário que ele já consumiu aquele item anteriormente
- Se a página for recarregada, a lista deverá apresentar a mesma sinalização indicada no item acima
- Um exercício deve ter a possibilidade de seleção de uma alterativa
- Após a seleção da alternativa o usuário poderá "VER A CORREÇÃO"

## Telas

Abaixo segue um esquema de base para a sua solução, porém fique à vontade para usar essa referência ou não:


![Aula em vídeo](https://user-images.githubusercontent.com/29892001/157113207-e5c0b933-3361-4af7-a4c2-44c677e28027.png)

![Aula em texto](https://user-images.githubusercontent.com/29892001/157113226-31d6a6a3-55c1-4862-a447-75a9d5298a25.png)

![Exercício](https://user-images.githubusercontent.com/29892001/157113253-117fa7cd-dc7f-49ca-86f6-2ec7fbc3ddd8.png)

![Exercício respondido](https://user-images.githubusercontent.com/29892001/157113262-abd5df64-c3e8-4bda-8355-fcd5c19ddf73.png)

## Tecnologias

Aqui no Me Salva! usamos as seguintes tecnologias, mas fique à vontade para usa-lás ou não:

- Typescript
- React
- Next.js
- Sass
- Jest
- Cypress
- Axios

## O que será avaliado

### Principal

- Utilização de alguma lib/framework em javascript como React, VueJs ou Angular
- Documentação (explique sobre as suas decisões técnicas, requisitos e arquitetura)
- Testes (muito importante)
- Arquitetura do projeto e organização
- Código (nome de variáveis, modularização, padronização, reutilização)
- Preocupação com a usuabilidade

### Secundário
- Interface responsiva
- Uso de typescript
- Preocupação com performace

:warning: Procure não usar lib, frameworks e pacotes, tanto para o css quanto para componentes, como Bootstrap e AntDesign por exemplo, pois queremos ver o seu conhecimento nessas tecnologias.

## Api

Para realizar as requisições, você deverá usar a seguintes rota:

GET: https://cdnqa.mesalva.com/data/pages/desafio-mesalva-web.json

```json
// Exemplo de resposta:
{
  "meta": {
    ...
  },
  "result": {
    "title": "Geografia",
    "type": "list",
    "slug": "desafio-mesalva-web",
    "description": "Lista de geografia",
    "children": [
      {
        "type": "video",
        "title": "Introdução à Geografia",
        "slug": "desafio-mesalva-web/introducao-a-geografia"
      },
      ...
    ]
  },
  "pagination": {
    ...
  }
}

```

No caso acima, para fazer pegar o conteúdo do primeiro item da lista, você deverá fazer uma requisão para:

GET: https://cdnqa.mesalva.com/data/pages/desafio-mesalva-web/introducao-a-geografia.json

```json
{
  "meta": {
    ...
  },
  "result": {
    "title": "Introdução à Geografia",
    "type": "video",
    "slug": "desafio-mesalva-web/introducao-a-geografia",
    "description": "Xuxuzada marota do Me Salva!, bem vindos. Nesta aula vamos falar dela, da icônica, da maravilinda, da fantasticobulosa... GEOGRAFIA! E de como ela aparece na tua prova do ENEM, também.",
    "children": [
      {
        "type": "video",
        "data": {
          "provider": "youtube",
          "link": "https://www.youtube.com/watch?v=fthMLBJXxRY",
          "durationInMinutes": 80
        }
      },
      {
        "type": "text",
        "data": {
          "title": "Introdução à Geografia",
          "html": "<p>Xuxuzada marota do Me Salva!, bem vindos. Nesta aula vamos falar dela, da icônica, da maravilinda, da fantasticobulosa... GEOGRAFIA! E de como ela aparece na tua prova do ENEM, também.</p><p><strong>Interação: </strong><a href=\"https://ms.mesalva.com/3K9sf9V\" target=\"blank\">https://ms.mesalva.com/3K9sf9V</a></p>"
        }
      },
      {
        "type": "pdf",
        "data": {
          "title": "Material de apoio",
          "description": "Aproveite o material de apoio em pdf utilizado em aula",
          "link": "https://cdn.mesalva.com/uploads/medium/attachment/bWF0ZXJpYWwtaW50cm9kdWNhby1hLWdlb2dyYWZpYTAyMDMyMDIyVDE4NDE%3D.pdf"
        }
      }
    ]
  },
  "pagination": null
}
```

## Como enviar o desafio

Envie o link do seu projeto no github para a pessoa que entrou em contato com você. Se possível, disponibilize o seu projeto na web, para que o time possa testar a interface sua solução.
