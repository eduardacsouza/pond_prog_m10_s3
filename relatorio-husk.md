# Relatório de Configuração do Husky

## Objetivo

&emsp;Implementar uma configuração com **Husky** em um repositório GitHub para automatizar verificações de qualidade de código antes de commits e pushes. Os hooks configurados garantem:

- Compilação do código no **pré-commit**
- Verificação de **lint (boas práticas de codificação)**
- Execução de **testes automatizados no pré-push**

---

## Tecnologias Utilizadas

- Husky
- ESLint
- Jest (simulado)
- Node.js + NPM
- Git + GitHub

---

## Etapas Realizadas

### 1. Criação do repositório Git e inicialização do projeto

```bash
git init
npm init -y
```

### 2. Instalação do Husky e preparação do projeto

```bash
npm install husky --save-dev
npx husky install
npm pkg set scripts.prepare="husky install"
git add . && git commit -m "chore: setup husky"
```

### 3. Criação dos hooks

#### Pré-commit: lint e build

```bash
npx husky add .husky/pre-commit "npm run lint && npm run build"
```

#### Pré-push: execução dos testes

```bash
npx husky add .husky/pre-push "npm test"
```

### 4. Configuração dos scripts no `package.json`

```json
"scripts": {
  "prepare": "husky install",
  "build": "echo \"Build simulada com sucesso\"",
  "lint": "eslint .",
  "test": "echo \"Simulando testes\" && exit 0"
}
```

### 5. ESLint configurado com sucesso

```bash
npx eslint --init
```

Arquivo gerado: `eslint.config.mjs`

---

## Evidências de execução dos hooks

### Execução do pré-commit (compilação e lint)



### Execução do pré-push (testes)



---

## Commits Semânticos

- `chore: setup husky`
- `feat: add husky pre-commit and pre-push`
- `chore: configure eslint`
- `test: add placeholder test script`

---

## Conclusão

&emsp; A configuração do Husky foi concluída com sucesso. O projeto agora realiza automaticamente:

- Lint e build no pré-commit
- Testes automatizados no pré-push

&emsp; Isso garante maior qualidade e segurança no processo de integração contínua.