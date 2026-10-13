# Ranking HELP — Campanha de outubro de 2026

Painel separado para a nova competição do grupo “Help - Campanha Premiação Reclame aqui”. O app usa o CSV público e mantém o layout do ranking anterior, com atualização, KPIs, prêmios, gráfico Top 7 e busca por participante.

## Dados públicos e locais

O repositório público contém o código e `ranking_publico.csv`, com nomes, votos HELP e, quando conhecido, os quatro últimos dígitos do celular. O ZIP do WhatsApp, as imagens, o relatório detalhado, o cache OCR e as dimensões locais ficam fora do Git.

## Processar novo ZIP no Windows

Instale Python 3.10+, Tesseract OCR com os idiomas Portuguese (`por`) e English (`eng`), e rode:

```powershell
python -m pip install -r requirements.txt
python .\conta_votos_help.py --zip "C:\caminho\WhatsApp Chat.zip" --output ".\contagem_local.xlsx" --tesseract "C:\Program Files\Tesseract-OCR\tesseract.exe"
```

O script gera um Excel local e `contagem_local_ranking.csv`. Confira os casos em “Revisar” e ajuste `correcoes_votos.csv` localmente. Depois copie o ranking final para `ranking_publico.csv` e publique apenas esse CSV.

O cache OCR SQLite é local e evita reler imagens idênticas em ZIPs futuros. Os arquivos com dados pessoais e comprovantes estão cobertos pelo `.gitignore`.

## Publicação Streamlit

O repositório pode ser conectado ao Streamlit Community Cloud escolhendo `main` e `app.py`. A página ficará pública, assim como o CSV.
