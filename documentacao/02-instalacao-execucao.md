# ⚙️ 02 - Instalacao e Execucao

<p align="left">
  <img src="https://img.shields.io/badge/Doc-Instalacao-3776AB?style=flat&logo=python&logoColor=white" alt="Instalacao">
  <img src="https://img.shields.io/badge/Suporte-Docker_+_Local-2496ED?style=flat&logo=docker&logoColor=white" alt="Suporte">
</p>

**Navegacao:** [📚 Dicionario](./README.md) • [🧭 Anterior: Visao Geral](./01-visao-geral.md) • [🏗️ Proximo: Arquitetura](./03-arquitetura-tecnica.md)

## ✅ Pre-requisitos

- Python 3.11+
- pip atualizado
- Git
- (Opcional) Docker Desktop + Docker Compose

## 🐍 Execucao local (recomendado para desenvolvimento)

```bash
git clone https://github.com/carmipa/CHALLENGE_2026_PRIDE_SECURITY.git
cd CHALLENGE_2026_PRIDE_SECURITY/api_python
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install -r requirements.txt
python main.py
```

## 🐳 Execucao com Docker

```bash
git clone https://github.com/carmipa/CHALLENGE_2026_PRIDE_SECURITY.git
cd CHALLENGE_2026_PRIDE_SECURITY/api_python
docker compose up --build
```

Para parar:

```bash
docker compose down
```

## 🔎 Como validar que subiu corretamente

- O menu principal deve aparecer no terminal.
- As opcoes de navegacao devem responder sem erro.

---

**Proxima leitura recomendada:** [🏗️ 03 - Arquitetura Tecnica](./03-arquitetura-tecnica.md)
