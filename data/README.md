# Dados

| Arquivo | Origem | Uso no notebook |
|---|---|---|
| `crop_yield.csv` | portal FIAP (anexo da Entrega 1) | base principal — seções 2 a 8 |
| `mall.csv` | material do Cap. 10 | apêndice 9.1 — K-Means (segmentação de clientes) |
| `moons.csv` | material do Cap. 10 | apêndice 9.2 — DBSCAN vs K-Means em grupos não convexos |

## crop_yield.csv

156 registros, sem nulos e sem duplicatas.

**Estrutura:** 39 observações climáticas **idênticas** replicadas para 4 culturas
(`Cocoa, beans`, `Oil palm fruit`, `Rice, paddy`, `Rubber, natural`), 39 registros cada.
Isso significa que o número de observações independentes é **39**, não 156 — ver seção 3.2
do notebook.

| Coluna original | Nome interno | Unidade |
|---|---|---|
| `Crop` | `Cultura` | categórica |
| `Precipitation (mm day-1)` | `Precipitacao` | mm/dia |
| `Specific Humidity at 2 Meters (g/kg)` | `Umidade_Especifica` | g/kg |
| `Relative Humidity at 2 Meters (%)` | `Umidade_Relativa` | % |
| `Temperature at 2 Meters (C)` | `Temperatura` | °C |
| `Yield` | `Rendimento` | hg/ha (ver nota) |

> **Nota sobre a unidade:** o enunciado fala em toneladas/hectare, mas os valores chegam a
> 203.399. A escala corresponde a hg/ha (padrão FAO): 203.399 hg/ha = 20,3 t/ha.

A função `padroniza_colunas()` do notebook aceita tanto os nomes em inglês quanto em português,
então versões diferentes do arquivo funcionam sem alteração de código.
