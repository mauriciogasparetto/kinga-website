# 🚀 Setup VSCode para Projeto Kinga

## PASSO 1 — Download e Instalação

### 1.1 Baixar VSCode
- Acede a: https://code.visualstudio.com/
- Download para Windows/Mac/Linux
- Instala normalmente

### 1.2 Baixar o ficheiro HTML
- Vai a: `/mnt/user-data/outputs/index.html`
- Clica com botão direito → "Guardar como"
- Guarda em: `C:\Users\SEU_USUARIO\Documents\kinga-website\index.html`
  (ou em qualquer pasta que prefiras)

---

## PASSO 2 — Abrir em VSCode

### 2.1 Abre VSCode
- Clica no ícone do VSCode
- Vai em: **File → Open Folder**
- Seleciona a pasta `kinga-website` (a que criaste acima)

### 2.2 Verifica se o ficheiro aparece
- No painel esquerdo (Explorer), deve aparecer `index.html`

---

## PASSO 3 — Instalar Extensões Essenciais

No VSCode, clica no ícone de **Extensions** (ou prime `Ctrl+Shift+X`):

#### ✅ Instala ESTAS extensões:

| Extensão | Por quê |
|----------|--------|
| **Live Server** (Ritwick Dey) | Abre o site em tempo real com auto-refresh |
| **Prettier** (Code formatter) | Formata código automaticamente |
| **HTML CSS Support** | Autocomplete para HTML/CSS |
| **Thunder Client** | Para testar APIs (opcional) |

---

## PASSO 4 — Usar Live Server

### 4.1 Abre o ficheiro `index.html`
- Clica em `index.html` no painel esquerdo

### 4.2 Clica com botão direito no ficheiro
- Escolhe: **"Open with Live Server"**
- OU no canto inferior direito, clica: **"Go Live"**

### 4.3 Pronto!
- Browser abre automaticamente em: `http://localhost:5500`
- **QUALQUER mudança que faças no código → site atualiza automaticamente**

---

## PASSO 5 — Estrutura de Projeto (Melhor Prática)

Cria uma estrutura assim:

```
kinga-website/
├── index.html          ← Ficheiro principal (já tem tudo)
├── assets/
│   ├── css/           ← (futuro) estilos separados
│   ├── js/            ← (futuro) scripts separados
│   └── images/        ← (futuro) imagens externas
├── README.md          ← Documentação do projeto
└── .gitignore         ← (futuro) para Git
```

**Por enquanto:** tudo está no `index.html` (é OK — é production-ready assim)

---

## PASSO 6 — Fluxo de Trabalho

### Editar código:

1. **Abre VSCode**
2. **Edita `index.html`** (Live Server já está observando)
3. **Salva** (`Ctrl+S`) — browser atualiza sozinho
4. **Testa no browser** (F12 para DevTools)
5. **Se está certo → pronto**

### Exemplo de mudança rápida:

```html
<!-- Original -->
<h1 class="hero__title">Personal Trainer & Nutricionista</h1>

<!-- Depois de editar e salvar → site atualiza em tempo real -->
```

---

## PASSO 7 — Atalhos Úteis VSCode

| Atalho | Função |
|--------|--------|
| `Ctrl+S` | Salvar |
| `Ctrl+Shift+P` | Abrir comando rápido |
| `Ctrl+/` | Comentar/descomentar linha |
| `Ctrl+D` | Selecionar palavra + próximas iguais |
| `F12` | DevTools (no browser) |
| `Ctrl+Shift+X` | Extensions |

---

## PASSO 8 — Git (Opcional mas recomendado)

Para controlar versões do código:

### 8.1 Instala Git
- https://git-scm.com/

### 8.2 No VSCode, abre Terminal
- `Ctrl+` (backtick)
- Escreve:
```bash
cd C:\Users\SEU_USUARIO\Documents\kinga-website
git init
git add .
git commit -m "Initial commit: Kinga landing page"
```

### 8.3 GitHub (futuro)
- Cria conta em https://github.com
- Cria repositório `kinga-website`
- Faz push do código

---

## PASSO 9 — Deploy para Vercel (Depois)

Quando estiver pronto:

1. **Push para GitHub** (passo 8.3)
2. **Vai a Vercel.com** → Login com GitHub
3. **Import project** → seleciona `kinga-website`
4. **Deploy** → site fica em: `kinga-website.vercel.app`

---

## TROUBLESHOOTING

### "Live Server não funciona"
- Reinstala a extensão
- Ou clica no ícone `Go Live` no canto inferior

### "VSCode não encontra o ficheiro"
- Verifica se a pasta está correta
- Abre via: **File → Open Folder** (não File → Open File)

### "Browser não atualiza"
- Faz F5 (refresh manual)
- Ou reinicia Live Server

---

## Próximos Passos

1. ✅ Setup VSCode
2. ✅ Instalar extensões
3. ✅ Abrir com Live Server
4. 📝 Editar código conforme necessário
5. 🚀 Deploy no Vercel (quando tudo OK)

---

**Dúvidas? Pede ajuda!**

