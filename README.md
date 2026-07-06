# 🎬 StreamTV — Filmes e Séries Online para Smart TV

> Site completo de streaming feito em **HTML5 + CSS3 + JavaScript puro**, sem frameworks,
> otimizado para **Android TV, Google TV, Samsung Tizen, LG webOS, Amazon Fire TV, TV Box e Chrome**.

---

## 🌐 Demo ao Vivo

**👉 [seuusuario.github.io/streamtv](https://seuusuario.github.io/streamtv)**

> Substitua `seuusuario` pelo seu nome de usuário do GitHub após fazer o deploy.

---

## 📺 Compatibilidade

| Plataforma           | Status |
|----------------------|--------|
| Android TV / Google TV | ✅ 100% |
| Amazon Fire TV       | ✅ 100% |
| TV Box (Android)     | ✅ 100% |
| Samsung Smart TV (Tizen) | ✅ 100% |
| LG Smart TV (webOS)  | ✅ 100% |
| Google Chrome (desktop) | ✅ 100% |
| Firefox / Edge       | ✅ 100% |

---

## 🎮 Controle Remoto

| Botão         | Ação                                     |
|---------------|------------------------------------------|
| ↑ ↓ ← →       | Navegar entre filmes, botões, menus       |
| OK (Enter)    | Selecionar / Confirmar / Play            |
| Voltar (Back) | Página anterior / Fechar player           |
| Home          | Volta direto para a tela inicial          |
| ← → no player | Retroceder / Avançar 10 segundos         |
| ↑ ↓ no player | Aumentar / Diminuir volume               |
| Play/Pause físico | Play / Pause do vídeo               |

---

## ✨ Funcionalidades

- 🏠 **Home** com banner em destaque rotativo (até 10 banners)
- 📂 **Categorias**: Ação, Drama, Comédia, Terror, Ficção, Infantil, Fantasia
- 🔍 **Pesquisa** com teclado virtual para controle remoto
- ❤️ **Favoritos** e 🕐 **Recentes** salvos localmente
- 🎬 **Player HTML5** fullscreen com controles completos
- ➕ **Painel de Adicionar** filmes com 3 abas:
  - 📋 Informações (título, sinopse, elenco, diretor...)
  - 🖼️ Imagens (poster + banner com preview ao vivo)
  - 🎬 Vídeo (MP4, M3U8/HLS, Google Drive ID, YouTube ID + Trailer)
- 💾 **Persistência** — conteúdo adicionado salvo no localStorage
- ⌨️ **Foco visual** sempre visível, animação de pressionar OK

---

## 🚀 Como publicar no GitHub Pages

### Opção 1 — Upload direto (mais simples)

1. Crie um repositório no GitHub chamado `streamtv` (ou qualquer nome)
2. Faça upload dos arquivos:
   - `index.html`
   - `404.html`
   - `.nojekyll`
   - `README.md`
3. Vá em **Settings → Pages**
4. Em **Source**, selecione **Deploy from a branch**
5. Escolha a branch `main` e pasta `/root`
6. Clique **Save**
7. Aguarde ~1 minuto e acesse: `https://seuusuario.github.io/streamtv`

### Opção 2 — Via Git (linha de comando)

```bash
git clone https://github.com/seuusuario/streamtv.git
cd streamtv
# Copie os arquivos para esta pasta
git add .
git commit -m "StreamTV inicial"
git push origin main
```

---

## 📁 Estrutura do Projeto

```
streamtv/
├── index.html      ← Site completo (único arquivo, tudo inline)
├── 404.html        ← Página de erro do GitHub Pages
├── .nojekyll       ← Desativa processamento Jekyll
└── README.md       ← Este arquivo
```

O projeto inteiro é **um único arquivo `index.html`** — HTML, CSS e JavaScript todos inline.
Não precisa de servidor, build, npm, ou qualquer dependência além de um navegador.

---

## 🎬 Como adicionar filmes e séries

### Pelo site (interface gráfica)

1. Abra o site e pressione o botão **＋** no canto superior direito
2. Preencha as 3 abas: **Informações**, **Imagens** e **Vídeo**
3. Clique **💾 Salvar Conteúdo**
4. O filme aparece imediatamente no catálogo e fica salvo no localStorage

### Pelo código (permanente)

Abra `index.html` em um editor e encontre `const DB = {`. Dentro do array `movies` adicione:

```javascript
{
  id: "m99",                    // ID único
  title: "Nome do Filme",
  year: 2024,
  genre: ["Ação", "Drama"],
  rating: "8.5",
  duration: "120 min",
  classification: "14+",
  director: "Nome do Diretor",
  cast: ["Ator 1", "Ator 2"],
  synopsis: "Descrição do filme...",
  poster: "https://url-da-imagem/poster.jpg",
  banner: "https://url-da-imagem/banner.jpg",
  category: ["acao", "destaque"],

  // Escolha UMA das opções abaixo:
  videoType: "mp4",    videoUrl: "https://servidor.com/video.mp4",
  // videoType: "hls",    videoUrl: "https://servidor.com/playlist.m3u8",
  // videoType: "gdrive", videoId: "1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs",
  // videoType: "youtube", videoId: "dQw4w9WgXcQ",
}
```

### Google Drive — como obter o ID

1. Faça upload do vídeo no [Google Drive](https://drive.google.com)
2. Clique com botão direito → **Compartilhar** → "Qualquer pessoa com o link"
3. Copie o link: `https://drive.google.com/file/d/`**`ID_AQUI`**`/view?usp=sharing`
4. Use só o ID no campo `videoId`

---

## 🛠️ Debug de Controle Remoto

Se algum botão não funcionar, ative o modo debug no código:

```javascript
// Encontre esta linha e mude para true:
const TV_DEBUG_KEYS = false;  →  const TV_DEBUG_KEYS = true;
```

Uma notificação aparecerá na tela mostrando o `keyCode` de cada botão pressionado.
Me envie o código e adicionarei ao mapeamento.

---

## 📄 Licença

MIT License — use, modifique e distribua livremente.

---

**Feito com ❤️ — HTML5 + CSS3 + JavaScript puro. Zero frameworks. Zero dependências.**
