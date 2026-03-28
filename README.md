# Windows File Organizer

Skill de sistema para organizar arquivos no Windows com regras por extensão, nome e categoria de documento.

## O que faz

- Organiza arquivos por tipo (`Imagens`, `Documentos`, `Videos`, `Musica`, `Outros`)
- Classifica documentos por palavras-chave (`Financeiro`, `RH`, `Juridico`, `Saude`)
- Evita sobrescrita com sufixos automáticos (`_1`, `_2`, ...)
- Gera log de movimentação (`organizacao.log`)
- Suporta modo contínuo (`--watch`), NLP para PDF (`--nlp`) e seleção gráfica (`--gui`)

## Estrutura

- `SKILL.md`
- `agents/openai.yaml`
- `scripts/windows_dir_organizer.py`
- `references/document_keywords_ptbr.md`

## Requisitos

- Python 3.10+
- Opcional para monitoramento: `watchdog`
- Opcional para NLP em PDF: `pdfplumber`

Instalação opcional de dependências:

```powershell
pip install watchdog pdfplumber
```

## Uso

Exemplo básico:

```powershell
python scripts/windows_dir_organizer.py --source "C:\Users\me\Downloads" --destination "D:\Organizados"
```

Com monitoramento contínuo:

```powershell
python scripts/windows_dir_organizer.py --source "C:\Users\me\Downloads" --destination "D:\Organizados" --watch --workers 4
```

Com classificação semântica de PDFs:

```powershell
python scripts/windows_dir_organizer.py --source "C:\Users\me\Downloads" --destination "D:\Organizados" --nlp
```

Modo GUI:

```powershell
python scripts/windows_dir_organizer.py --gui
```

## Validação da skill

```powershell
python "C:\Users\arlei\.codex\skills\.system\skill-creator\scripts\quick_validate.py" "C:\Users\arlei\Desktop\Apps\Skills Codex\windows-file-organizer"
```

## Publicação no GitHub

1. Criar repositório e enviar esta pasta.
2. Manter a estrutura da skill exatamente como está.
3. Versionar mudanças em `SKILL.md`, `agents/openai.yaml`, `scripts/` e `references/`.

Exemplo rápido:

```powershell
git init
git add .
git commit -m "feat: add windows-file-organizer skill"
git branch -M main
git remote add origin <URL_DO_REPOSITORIO>
git push -u origin main
```

