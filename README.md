# 🎬 CinéDuo

> Escolham juntos o próximo filme para assistir — estilo Tinder para filmes!

---

## O que é?

**CinéDuo** é um app web para casais escolherem filmes juntos. Dois usuários entram na mesma sala virtual e deslizam cartões de filmes: para a direita se quiserem assistir, para a esquerda se não quiserem. Quando **os dois curtirem o mesmo filme**, aparece um **Match** com confetes 🎉

---

## Funcionalidades

- 🏠 **Criação de sala** com código de 6 dígitos para compartilhar
- 🃏 **Swipe de filmes** — arraste com o mouse ou toque na tela
- 💕 **Match em tempo real** quando os dois curtirem o mesmo filme
- 📋 **Tela de resultados** com todos os filmes em comum ao final
- 🎥 20 filmes variados: ação, romance, ficção científica, animação, drama e mais
- 📱 Funciona em desktop e mobile (touch)

---

## Como usar

### 1. Criar uma sala

1. Acesse o site
2. Digite seu apelido no campo **"Criar nova sala"**
3. Clique em **Criar sala**
4. Compartilhe o código de 6 letras com seu parceiro(a)

### 2. Entrar em uma sala

1. Acesse o site no seu dispositivo
2. Digite seu apelido e o código recebido em **"Entrar em sala existente"**
3. Clique em **Entrar**

### 3. Jogar

- Quando os dois estiverem conectados, os cartões de filmes aparecem automaticamente
- **Arraste para a direita** ou clique em **♥** para salvar um filme
- **Arraste para a esquerda** ou clique em **✕** para descartar
- Se os dois curtirem o mesmo filme → **Match!** 🎉
- Ao final dos 20 filmes, uma tela mostra todos os filmes em comum

---

## Instalação e hospedagem

O CinéDuo é um **arquivo HTML único**, sem dependências externas para instalar.

### Opção 1 — Netlify Drop (mais rápido)

1. Acesse [app.netlify.com/drop](https://app.netlify.com/drop)
2. Arraste o arquivo `cine-casal.html` para a página
3. Pronto! Você recebe uma URL pública em segundos

### Opção 2 — GitHub Pages

1. Crie um repositório público no GitHub
2. Faça upload de `cine-casal.html` e renomeie para `index.html`
3. Vá em **Settings → Pages → Branch: main → Save**
4. Seu site estará em `https://seuusuario.github.io/nome-do-repositorio`

### Opção 3 — Qualquer servidor estático

Basta colocar o arquivo em qualquer servidor que sirva arquivos HTML estáticos (Vercel, Surge.sh, servidor Apache/Nginx, etc.).

---

## ⚠️ Limitação importante

A versão atual usa `localStorage` do navegador para simular a sala compartilhada. Isso significa que **dois dispositivos diferentes não se comunicam entre si** — o app funciona localmente em um mesmo navegador (para testes) mas **não sincroniza entre dois celulares/computadores diferentes**.

### Para funcionar entre dois dispositivos:

É necessário integrar um banco de dados em tempo real. A solução recomendada é o **Firebase Realtime Database** (plano gratuito suficiente):

1. Crie um projeto em [firebase.google.com](https://firebase.google.com)
2. Ative o **Realtime Database**
3. Substitua as funções `saveRoom` / `loadRoom` pelas chamadas do SDK do Firebase
4. Configure as regras de segurança do banco

---

## Tecnologias utilizadas

- HTML5, CSS3 e JavaScript puro (sem frameworks)
- Google Fonts: `Bebas Neue` + `Inter`
- `localStorage` para persistência local da sala
- Animações CSS e eventos de touch/mouse para o swipe

---

## Estrutura do projeto

```
cine-casal.html   ← arquivo único com todo o app (HTML + CSS + JS)
README.md         ← este arquivo
```

---

## Personalização

Para adicionar ou trocar filmes, edite o array `MOVIES` no JavaScript do arquivo HTML:

```javascript
const MOVIES = [
  {
    id: 21,
    title: "Meu Novo Filme",
    year: 2024,
    genre: "Comédia",
    rating: "8.0",
    emoji: "😂",
    synopsis: "Descrição do filme aqui."
  },
  // ...
];
```

---

## Licença

Projeto de uso livre para fins pessoais.
