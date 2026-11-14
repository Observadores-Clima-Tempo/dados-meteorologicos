# dados-meteorologicos

Previsão mais recente de temperatura e umidade relativa para Macaé (RJ).

## Endpoint

```
https://raw.githubusercontent.com/Observadores-Clima-Tempo/dados-meteorologicos/main/PrevisaoMacae/macae_rj_previsao.csv
```

Arquivo único, sobrescrito a cada nova rodada, com CORS liberado e sem consumo de cota da API do GitHub.
CSV separado por vírgula, em ordem cronológica:

| Coluna | Descrição |
| --- | --- |
| `rodada` | Rodada do modelo WRF no formato `AAAAMMDD00` (UTC) |
| `data_hora_utc` | Data/hora em UTC |
| `data_hora_local` | Data/hora local (UTC-3) |
| `temperatura_C` | Temperatura a 2 m, em °C |
| `umidade_relativa_pct` | Umidade relativa a 2 m, em % |

## Fonte

Dados derivados do repositório DefesaCivil (`Macae_RJ/Temperatura` e `Macae_RJ/UmidadeRelativa`).
A sincronização é feita pelo script `sync_previsao.py`, que só publica quando há uma rodada mais nova
que a registrada na coluna `rodada`.