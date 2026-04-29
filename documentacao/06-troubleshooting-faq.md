# 🧯 06 - Troubleshooting e FAQ

<p align="left">
  <img src="https://img.shields.io/badge/Doc-Suporte-red?style=flat&logo=sentry&logoColor=white" alt="Suporte">
  <img src="https://img.shields.io/badge/Foco-Resolucao_de_Problemas-orange?style=flat&logo=helpdesk&logoColor=white" alt="Resolucao">
</p>

**Navegacao:** [📚 Dicionario](./README.md) • [🛠️ Anterior: Operacao](./05-operacao-manutencao.md) • [🚀 Proximo: Roadmap](./07-roadmap.md)

## ❗ Problemas comuns

### `python` nao reconhecido

- Verificar versao com `python --version`.
- Tentar `python3 --version`.
- No Windows, validar Python no PATH.

### Falha ao ativar `.venv` no PowerShell

```bash
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

### Erro ao instalar dependencias

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt --force-reinstall
```

### Docker nao inicia corretamente

```bash
docker compose version
docker compose down
docker compose up --build
```

## ❓ FAQ rapido

- **Preciso usar Docker?** Nao. O modo local funciona bem para desenvolvimento.
- **Onde fica a equipe do projeto?** Em `api_python/app/ui/sobre/sobre.py`.
- **Qual arquivo principal de entrada?** `api_python/main.py`.

---

**Proxima leitura recomendada:** [🚀 07 - Roadmap e Proximos Passos](./07-roadmap.md)
