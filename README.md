# Desafio Me Salva! - Web

Esse repositório foi criado para explicar o desafio técnico aplicado para candidatos à nossa vaga de pessoa desenvolvedora web.

## Contexto

O desafio será implementar um "console de aulas", que apresente conteúdos variados (vídeo, texto e exercício) relacionados à uma lista de estudos. O desafio deverá conter as seguintes funcionalidades:

- Lista de estudos
- Apresentação de um conteúdo completo
- Cada item da lista de estudos deverá ter um identificador do seu tipo (vídeo, texto e exercício)
- Ao clicar em um item da lista de estudos o seu conteúdo relacionado deverá ser mostrado para o estudante
- Deverá ser sinalizado na lista de estudos quando um conteúdo já foi consumido (respondido/assistido)
- Se a página for carregada, a lista de estudos deverá manter a sinalização de quais conteúdos já foram consumidos (respondido/assistido)
- Um exercício deve ter a possibilidade de seleção de uma alternativa
- Após a seleção da alternativa o estudante poderá "VER A CORREÇÃO"

## Telas

Abaixo segue um esquema de base para a sua solução, porém fique à vontade para usar essa referência ou não:

![Aula em vídeo](https://user-images.githubusercontent.com/29892001/157113207-e5c0b933-3361-4af7-a4c2-44c677e28027.png)

![Aula em texto](https://user-images.githubusercontent.com/29892001/157113226-31d6a6a3-55c1-4862-a447-75a9d5298a25.png)

![Exercício](https://user-images.githubusercontent.com/29892001/157113253-117fa7cd-dc7f-49ca-86f6-2ec7fbc3ddd8.png)

![Exercício respondido](https://user-images.githubusercontent.com/29892001/157113262-abd5df64-c3e8-4bda-8355-fcd5c19ddf73.png)

## Tecnologias

Aqui no Me Salva! usamos as seguintes tecnologias, mas fique à vontade para usá-las ou não:

- Typescript
- React
- Next.js
- Sass
- Jest
- Cypress
- Axios

## O que será avaliado

### Principal

- Documentação (explique sobre as suas decisões técnicas, requisitos e arquitetura)
- Testes (muito importante!)
- Arquitetura do projeto e organização
- Código (nomenclaturas, modularização, padronização, reutilização)
- Preocupação com a usabilidade

### Secundário

- Utilização de alguma lib/framework em javascript como React, VueJs ou Angular
- Interface responsiva
- Uso de typescript
- Preocupação com performance
- Usar padrões de CSS, como o [BEM](https://en.bem.info/) ou outro

:warning: Procure não usar libs para o css e com componentes prontos, como Bootstrap e AntDesign por exemplo, pois queremos ver os seus conhecimentos nessas tecnologias.

## Api

Para realizar as requisições, você deverá usar as seguintes rotas:

GET: <https://bff-qa.mesalva.com/json/pages/desafio-mesalva-web>

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
        "slug": "introducao-a-geografia"
      },
      ...
    ]
  },
  "pagination": {
    ...
  }
}

```

No caso acima, para pegar o conteúdo do primeiro item da lista, você deverá fazer uma requisição para:

GET: <https://bff-qa.mesalva.com/json/pages/desafio-mesalva-web/introducao-a-geografia>

```json
{
  "meta": {
    ...
  },
  "result": {
    "title": "Introdução à Geografia",
    "type": "video",
    "slug": "introducao-a-geografia",
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

Ou seja, para pegar os outros conteúdos, você deve utilizar o slug de cada item:

```
https://bff-qa.mesalva.com/json/pages/desafio-mesalva-web/{SLUG_DO_ITEM}
```

## Como enviar o desafio

Envie o link do seu projeto no github para a pessoa que entrou em contato com você. Se possível, disponibilize o seu projeto na web, para que o time possa testar a sua solução.
