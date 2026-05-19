# Tech Sul PA

Site estatico da comunidade Tech Sul PA, criada para conectar pessoas de tecnologia de Xinguara e do sul do Para.

O projeto tem uma landing page institucional e uma pagina de cadastro integrada ao Firebase/Firestore. Depois do envio do formulario, o usuario e redirecionado para o Discord da comunidade.

## Arquivos principais

- `tech-sul-pa.html`: pagina principal da comunidade.
- `formulario-firebase.html`: formulario oficial de cadastro com Firebase.
- `tech-sul-pa-logo-azul.svg`: logo principal, usada no topo e na hero.
- `tech-sul-pa-logo-verde.svg`: logo alternativa, usada em areas de apoio.
- `tech_sul_pa_logo_system.html`: referencia visual do sistema de logos e cores.

## Como abrir

Por ser um site estatico, basta abrir o arquivo abaixo no navegador:

```text
tech-sul-pa.html
```

A landing page leva para:

```text
formulario-firebase.html
```

## Fluxo de cadastro

1. O usuario acessa a landing.
2. Clica em `Quero fazer parte`, `Entrar` ou `Abrir formulario de cadastro`.
3. Preenche o formulario em `formulario-firebase.html`.
4. Os dados sao enviados para a colecao `membros` no Firestore.
5. Apos o envio com sucesso, o usuario e redirecionado para o Discord:

```text
https://discord.gg/ycFuMSFgzr
```

## Configuracao do Firebase

A configuracao fica no topo de `formulario-firebase.html`, dentro de:

```js
const firebaseConfig = {
  apiKey: "...",
  authDomain: "...",
  projectId: "...",
  storageBucket: "...",
  messagingSenderId: "...",
  appId: "..."
};
```

O formulario salva os dados nesta colecao:

```js
collection(db, "membros")
```

Importante: confira as regras do Firestore antes de publicar. Para um formulario publico, evite deixar permissao aberta demais por muito tempo. O ideal e permitir apenas criacao de documentos e validar os campos esperados.

## Identidade visual

Cores principais:

- Azul principal: `#378ADD`
- Azul escuro: `#0C447C`
- Verde principal: `#1D9E75`
- Verde escuro: `#085041`
- Vermelho de alerta: `#E24B4A`

Fontes usadas:

- `Sora`: textos e titulos.
- `Space Mono`: labels, numeros e detalhes tecnicos.

## Responsividade e animacoes

As paginas foram ajustadas para desktop, tablet e celular, com breakpoints para telas pequenas. Tambem ha animacoes suaves de entrada, hover e movimento da logo.

O CSS respeita `prefers-reduced-motion`, reduzindo animacoes para usuarios que ativaram essa preferencia no sistema.

## Observacoes

- A landing nao possui formulario interno.
- O formulario oficial fica somente em `formulario-firebase.html`.
- O projeto nao depende de build, framework ou instalacao de pacotes.
