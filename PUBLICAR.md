# Como publicar no GitHub (vigmiranda/nomo-mt5-eas)

O repositório remoto existe, mas ainda está **vazio**. O `git push` pede login do GitHub.

## Passo a passo no seu PC (Windows)

Abra o terminal **dentro da pasta do projeto** (ex.: `C:\Users\vitor\projects\nomo-mt5-eas`).

### 1. Conferir se há commit local

```powershell
git status
git log --oneline -1
```

Se der erro *"not a git repository"* ou *"does not have any commits yet"*, faça:

```powershell
git init
git add README.md .gitignore eas/
git commit -m "Initial commit: Nomo MT5 Expert Advisors"
git branch -M main
```

### 2. Apontar para o remoto (só uma vez)

```powershell
git remote remove origin
git remote add origin https://github.com/vigmiranda/nomo-mt5-eas.git
```

### 3. Fazer login no GitHub e enviar

**Opção A — GitHub CLI (recomendado)**

```powershell
gh auth login
git push -u origin main
```

**Opção B — Token pessoal (PAT)**

1. GitHub → Settings → Developer settings → Personal access tokens → Generate (scope `repo`)
2. No push, usuário: `vigmiranda`, senha: **cole o token**

```powershell
git push -u origin main
```

**Opção C — URL com token (uma vez)**

Substitua `SEU_TOKEN` pelo PAT:

```powershell
git push https://vigmiranda:SEU_TOKEN@github.com/vigmiranda/nomo-mt5-eas.git main
git branch --set-upstream-to=origin/main main
```

### 4. Confirmar

Abra: https://github.com/vigmiranda/nomo-mt5-eas

Deve aparecer `README.md` e a pasta `eas/`.

## Se a pasta local estiver vazia

Copie para ela o conteúdo de `eas/`, `README.md` e `.gitignore` (deste projeto ou do zip `nomo-mt5-eas.zip`) e repita o passo 1.
