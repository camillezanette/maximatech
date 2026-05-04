# Forecast Comercial — MáximaTech

## Estrutura do repositório

```
/
├── index.html                    ← dashboard principal
├── forecast_2026-05-04.json     ← snapshot semana 1
└── README.md
```

## Como publicar no GitHub Pages

1. Crie um repositório no GitHub (pode ser privado)
2. Faça upload dos arquivos `index.html` e `forecast_YYYY-MM-DD.json`
3. Vá em **Settings → Pages → Source → Deploy from branch → main → / (root)**
4. Aguarde ~1 min e acesse o link gerado

## Como atualizar semanalmente

1. Exporte o relatório do HubSpot
2. Envie para a Cami processar → novo `forecast_YYYY-MM-DD.json` gerado
3. Adicione o novo JSON ao repositório
4. Atualize o `index.html` com o novo snapshot (a Cami gera o HTML atualizado)
5. Commit e push — o site atualiza automaticamente

## Senha de acesso

`maxima2026`

> ⚠️ Senha protegida via JavaScript — adequada para uso interno. Para segurança avançada, migrar para Netlify com password protection nativa.

## Adicionando novo snapshot ao histórico

No `index.html`, localize o objeto `SNAPSHOTS` e adicione:
```javascript
SNAPSHOTS['forecast_2026-05-11'] = await fetch('forecast_2026-05-11.json').then(r=>r.json());
```
