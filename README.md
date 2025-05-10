
# Exemplo GitHub Actions com Action Personalizada

Este projeto mostra como conectar um workflow do GitHub Actions com uma action personalizada simples.

### ✨ O que faz

- **Action personalizada** (`.github/actions/hello/action.yml`):
  - Recebe um input `the-caller` (padrão: World).
  - Escreve no log: `Hello <the-caller>`.
  - Gera um número aleatório e expõe como output `random-number`.

- **Workflow** (`.github/workflows/steps-example.yml`):
  - Dispara quando ocorre um `push` no repositório.
  - Faz checkout do código.
  - Executa a action personalizada passando `the-caller: 'Myself'`.
  - Usa o número aleatório gerado no log.

### 📂 Estrutura

```
.github/
├── actions/
│   └── hello/
│       └── action.yml
└── workflows/
    └── steps-example.yml
```

### 💻 Exemplo de saída esperada no log

```
Hello Myself.
random-number <número aleatório>
```

👉 Use como modelo para lembrar como:
- Criar uma action reutilizável.
- Passar inputs para a action.
- Capturar outputs no workflow.
