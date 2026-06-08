# 💼 Workflow Profissional — VSCode + Git + Vercel

## FASE 1: DESENVOLVIMENTO LOCAL (VSCode)

### 1.1 Estrutura de Ficheiros

```
kinga-website/
├── index.html              ← Ficheiro principal (production-ready)
├── README.md               ← Documentação
├── .gitignore              ← Ficheiros para ignorar
├── CHANGELOG.md            ← Histórico de mudanças
└── docs/
    ├── SETUP_VSCODE.md     ← Este ficheiro
    └── WORKFLOW.md         ← Guia de workflow
```

### 1.2 Como Editar Código em VSCode

**Exemplos reais:**

#### Mudança 1: Alterar título do hero
```html
<!-- Ctrl+F para encontrar -->
<h1 class="hero__title">Personal Trainer & Nutricionista</h1>

<!-- Muda para algo como -->
<h1 class="hero__title">Transforma tu cuerpo, tu salud y tu vida</h1>

<!-- Ctrl+S para salvar → Live Server atualiza automaticamente -->
```

#### Mudança 2: Mudar cor principal (rose)
```css
/* Ctrl+H para Find and Replace */
--color-rose: #c06080;

/* Muda para */
--color-rose: #d95a9f;

/* Salva → todas as cores no site mudam automaticamente */
```

#### Mudança 3: Adicionar nova seção
1. Encontra onde colocar (ex: antes de `</footer>`)
2. Copia a estrutura de outra seção (ex: `.about`)
3. Cola e adapta
4. Salva e testa

---

## FASE 2: VERSIONAMENTO COM GIT

### 2.1 Comandos Git Básicos

#### Setup inicial (primeira vez):
```bash
# Terminal VSCode: Ctrl+` (backtick)
cd caminho/para/kinga-website
git init
git config user.name "Seu Nome"
git config user.email "seu@email.com"
```

#### Fluxo diário:
```bash
# Ver estado dos ficheiros
git status

# Adiciona ficheiros modificados
git add .

# Cria um "snapshot" (commit) com mensagem
git commit -m "Fix: corrige hero layout no mobile"

# Ver histórico
git log --oneline
```

### 2.2 Padrão de Mensagens de Commit

Usa este padrão para clareza:

```
feat: adiciona nova seção de testimonials
fix: corrige layout do hero no mobile
style: muda cor principal de rose
refactor: simplifica CSS do hero
docs: atualiza README com instruções
```

---

## FASE 3: SINCRONIZAR COM GITHUB

### 3.1 Criar Repositório no GitHub

1. Vai a https://github.com/new
2. Nome: `kinga-website`
3. Descrição: "Landing page for Kinga — Personal Trainer & Nutritionist"
4. Escolhe: **Public** (para portfolio)
5. NÃO marca "Initialize with README" (já tens)
6. Click: **Create repository**

### 3.2 Push para GitHub (VSCode)

```bash
# Primeira vez: adiciona o repositório remoto
git remote add origin https://github.com/SEU_USERNAME/kinga-website.git

# Muda branch para main (se não existir)
git branch -M main

# Envia código para GitHub
git push -u origin main

# Próximas vezes: apenas
git push
```

### 3.3 Ver em GitHub

- Abre https://github.com/SEU_USERNAME/kinga-website
- Vê todo o histórico de commits
- Partilha o link (é portfolio!)

---

## FASE 4: DEPLOY NO VERCEL (Production)

### 4.1 Conectar Vercel com GitHub

1. Vai a https://vercel.com
2. Click: **Sign up** (com GitHub)
3. Autoriza Vercel a aceder ao GitHub
4. Click: **Import Project**
5. Seleciona: `kinga-website`
6. Click: **Deploy**

**Resultado:** Site em produção em: `kinga-website.vercel.app`

### 4.2 Auto-Deploy (Magic!)

Agora **qualquer push para GitHub → Vercel atualiza automaticamente**:

```bash
# Edita código em VSCode
# Salva (Ctrl+S)
# Testa localmente
# Quando pronto:

git add .
git commit -m "feat: melhora responsividade do mobile"
git push

# ✅ Vercel recebe o push → reconstrói e publica automaticamente
# 📱 Site atualizado em: kinga-website.vercel.app (em ~1 min)
```

---

## FASE 5: DOMÍNIO PERSONALIZADO (Opcional)

Se quiser usar domínio próprio (ex: `kinga.pt`):

1. Compra domínio em: GoDaddy, Namecheap, etc
2. Em Vercel → Project Settings → Domains
3. Adiciona domínio
4. Copia os DNS records
5. Cola no provider do domínio
6. Espera ~24h para propagar

Resultado: `www.kinga.pt` aponta para Vercel!

---

## CHECKLIST DIÁRIO

- [ ] Abro VSCode e Live Server (`Go Live`)
- [ ] Edito código conforme necessário
- [ ] Testo no browser (F12 para DevTools)
- [ ] Quando está OK:
  ```bash
  git add .
  git commit -m "descrição da mudança"
  git push
  ```
- [ ] Verifiqo em Vercel (1-2 min depois)

---

## TROUBLESHOOTING

### "Tenho um erro no código e não sei onde está"

1. Abre DevTools: **F12 no browser**
2. Vai a **Console**
3. Vê a mensagem de erro (mostra linha exata)
4. Vai a VSCode e corrige

### "Fiz mudanças e não consigo fazer git push"

```bash
git status  # Ver quais ficheiros mudaram
git add .
git commit -m "mensagem"
git push
```

### "Preciso desfazer último commit"

```bash
git revert HEAD  # Desfaz último commit (seguro)
git push
```

### "VSCode mostra ficheiro como modificado mas não vejo mudanças"

```bash
git diff  # Mostra exatamente o que mudou
```

---

## EXTRAS: Instalar Prettier (formatação automática)

1. **Extensão:** `Prettier - Code formatter`
2. **Abre settings:** `Ctrl+,`
3. Procura: `Format on Save`
4. Marca a checkbox

**Resultado:** Cada vez que salvas (`Ctrl+S`), código fica formatado automaticamente!

---

## Resumo Rápido

| Ação | Comando |
|------|---------|
| Ver mudanças | `git status` |
| Guardar mudanças | `git add . && git commit -m "msg"` |
| Enviar para GitHub | `git push` |
| Ver histórico | `git log` |
| Desfazer mudança | `git revert HEAD` |

---

**Pronto! Agora tens um workflow profissional.** 🚀

