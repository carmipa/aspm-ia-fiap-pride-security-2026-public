# 🐍 ASPM IA - Python API Core

<p align="center">
  <img src="../logo_projeto.png" alt="ASPM Logo" width="400">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Em_Desenvolvimento-yellow?style=for-the-badge&logo=rocket" alt="Status Badge">
  <img src="https://img.shields.io/badge/Python-3.11+-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python Badge">
  <img src="https://img.shields.io/badge/Docker-Pronto-blue?style=for-the-badge&logo=docker&logoColor=white" alt="Docker Badge">
</p>

<p align="center">
  <a href="../README.md">🏠 README Raiz</a> •
  <a href="../documentacao/README.md">📚 Dicionario</a> •
  <a href="#-como-executar">🚀 Como Executar</a> •
  <a href="#-roadmap--proximos-passos">🗺️ Roadmap</a>
</p>

---

## 📖 Sobre o Modulo

Este diretório contém o **Core da API Python** do projeto **ASPM IA FIAP - Desafio Pride 2026**. Atualmente, o projeto está em suas fases iniciais ("engatinhando"), focando na estrutura base de gerenciamento de usuários e segurança de ativos.

O objetivo futuro é integrar motores de busca de vulnerabilidades e análise de postura de segurança (ASPM) em uma interface CLI intuitiva e containerizada.

---

## 🏗️ Arquitetura do Modulo (Fase Atual)

Abaixo, os diagramas em Mermaid adaptados para renderizacao no GitHub:

```mermaid
flowchart TD
    A[main.py] --> B[Menu principal]
    B --> C{Opcoes}
    C -->|1| D[Menu de cadastro]
    C -->|0| E[Sair]

    subgraph CAD[Modulo cadastro - app/ui/cadastro]
        D --> D1[Criar usuario]
        D --> D2[Listar usuarios]
        D1 --> DB[database.py]
        D2 --> DB
        DB --> TXT[(usuarios.txt)]
    end

    subgraph UTL[Utilitarios - app/utils]
        H[helpers.py] --> Visual[Limpar tela]
        T[tempo.py] --> Log[Timestamp UTC]
    end
```

```mermaid
flowchart LR
    DEV[Desenvolvedor] --> LOCAL[Execucao local]
    DEV --> CONT[Execucao container]
    LOCAL --> CMD1[python main.py]
    CONT --> CMD2[docker compose up --build]
    CMD1 --> CLI[CLI ativa]
    CMD2 --> CLI
```

---

## 🛠️ Tecnologias e Ferramentas

| Tecnologia | Descrição | Ícone |
| :--- | :--- | :---: |
| **Python** | Linguagem base do projeto | ![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white) |
| **Docker** | Containerização e isolamento | ![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white) |
| **Colorama** | Interface CLI colorida | ![CLI](https://img.shields.io/badge/-CLI-black?style=flat&logo=terminal&logoColor=white) |
| **Text DB** | Persistência simples via arquivo .txt | ![DB](https://img.shields.io/badge/-Database-grey?style=flat&logo=databricks&logoColor=white) |

---

## 📂 Estrutura de Pastas

```text
api_python/
├── app/
│   ├── ui/               # Interface de Usuário (CLI)
│   │   ├── menu.py       # Menu principal
│   │   └── cadastro/     # Sistema de CRUD de usuários
│   └── utils/            # Funções utilitárias (tempo, helpers)
├── main.py               # Ponto de entrada da aplicação
├── requirements.txt      # Dependências do projeto
├── Dockerfile            # Configuração da imagem Docker
└── docker-compose.yml    # Orquestração do container
```

---

## 🚀 Como Executar

### 🐳 Via Docker (Recomendado)

Para rodar o ambiente completamente isolado e interativo:

```bash
docker compose up --build
```

### 🐍 Via Python Local

1. Crie um ambiente virtual:

   ```bash
   python -m venv .venv
   ```

2. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

3. Execute:

   ```bash
   python main.py
   ```

---

## 🖥️ Demonstração do Módulo CLI/CMD

O módulo CLI/CMD do ASPM IA permite executar varreduras locais em projetos de software, identificar padrões de risco e gerar relatórios estruturados para análise posterior.

### Funcionalidades demonstradas

- Menu interativo em terminal;
- Scan de projetos locais;
- Barra de progresso da varredura;
- Resumo consolidado de ocorrências;
- Classificação por severidade: crítico, alto, médio e baixo;
- Detecção de padrões como RCE, credenciais hardcoded, SSRF, XSS, path traversal, TLS/SSL inseguro, JWT inseguro, CORS e queries SQL;
- Geração de relatório estruturado em JSON;
- Listagem de relatórios anteriores;
- Visualização detalhada de cada achado;
- Exibição do arquivo, linha, padrão detectado e trecho de código;
- Referências técnicas CWE/OWASP;
- Abertura automática do arquivo-fonte no editor para facilitar correção.

---

## 📈 Roadmap / Próximos Passos

- [x] Estrutura base de pastas.
- [x] CRUD básico de usuários.
- [x] Suporte a Docker.
- [ ] Integração com Banco de Dados persistente (SQLite/MongoDB).
- [ ] Implementação de Scanners de Vulnerabilidades.
- [ ] Dashboard de logs com IA.

---

<p align="center">
  <b>RM 570877 - Paulo André Carminati</b><br>
  FIAP - 1TDCPV - 2026
</p>
