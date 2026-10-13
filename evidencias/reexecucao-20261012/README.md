# Verificação integral das correções — 12/10/2026

Execução `20261013T005458935971Z`, em Colab Linux, Python 3.13.15 e GPU Tesla T4, iniciada em 12/10 no horário de Brasília (13/10 UTC). **As 15 células terminaram na ordem 1–15, sem saídas de erro e sem mudanças no código durante a execução.** A sessão foi reiniciada e as saídas foram limpas antes da execução. O dataset foi baixado da URL pública; `USE_DRIVE=True` foi usado nesta cópia para preservar os resultados no Drive, com autorização do autor. O notebook principal mantém `USE_DRIVE=False` por padrão.

- [Notebook desta rodada com discussão revisada](VERIFICACAO_CORRECOES_2026-10-12.ipynb)
- [Exportação original, preservada](notebook-original-executado.ipynb)
- [Registro verificável e inventário de hashes](VERIFICACAO.json)
- [ZIP completo dos resultados, incluindo pesos](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/RESULTADOS-FARMTECH-20261013T005458935971Z.zip)

## Correções verificadas

1. As cinco figuras geradas ficaram embutidas nas saídas, inclusive CNN, matrizes e painel. Figuras acima de 400 kB usam uma prévia JPEG compacta para evitar a externalização de imagens pelo Colab; os PNGs completos também estão no ZIP. Cada imagem embutida coincide byte a byte com seu arquivo correspondente no pacote, identificado em `VERIFICACAO.json`. Não houve incorporação manual de gráficos nesta rodada.
2. As 28 versões centrais instaladas coincidem com `requirements-colab.txt`, respeitando o sufixo CUDA do PyTorch. O `pip freeze` completo está preservado. Essa lista não fixa todas as dependências transitivas do Colab.
3. O código das 15 células foi comparado estruturalmente com o notebook principal corrigido: a única diferença é `USE_DRIVE=True` nesta cópia, para salvar os resultados. Comentários não alteram os cálculos.
4. Conferidos os 80 registros do manifesto, 173 caixas, divisão 32/4/4, pixels e grupos iguais à referência. Recalculadas as métricas por imagem a partir das 64 previsões e a mediana/P95 a partir das 160 medições; valores coincidentes.
5. Históricos completos, checkpoints presentes, CRC do ZIP válido e inventário de todos os arquivos com SHA-256. A exportação original do notebook não foi editada; a cópia revisada altera somente Markdown.

## Resultados desta verificação

O critério de validação selecionou o experimento de **60 épocas**; essa escolha foi mantida no teste. Os históricos contêm 30 e 60 épocas completas.

| Conjunto | Épocas | mAP@0,5 | mAP@0,5:0,95 |
|---|---:|---:|---:|
| val | 30 | 0.5770 | 0.4047 |
| val | 60 | 0.6220 | 0.4073 |
| test | 30 | 0.8414 | 0.5239 |
| test | 60 | 0.6636 | 0.3615 |

| Modelo | Acertos no teste | Sem detecção | Mediana CPU (ms) |
|---|---:|---:|---:|
| CNN_do_zero | 5/8 | 0 | 40.65 |
| YOLOv3_padrao | 7/8 | 1 | 1046.55 |
| YOLOv5_30 | 6/8 | 1 | 195.21 |
| YOLOv5_60 | 4/8 | 4 | 177.11 |

A CNN executou 7 épocas e restaurou a época 1, de menor perda de validação. Continua sendo uma classificadora com 23.714 parâmetros, sem localização de objetos. A comparação usa oito imagens de teste; ausências de detecção contam como erro.

Esta rodada serve para verificar a execução das correções, não para escolher um resultado mais favorável. O vídeo e a discussão principal permanecem vinculados à referência de 04/10. Variações nos YOLOv5 e nos tempos entre sessões não são evidência de melhora causada pela correção de exibição ou pelas versões fixadas; essa relação causal não foi testada. Repetições com a mesma divisão pequena não substituem testes independentes nem demonstram desempenho de produção.

## Preservação

SHA-256 do notebook original: `7006e446a1450605f8a8d5e57e61f33cd3ea67e1a3831374b1acf762e8663cbb`.

SHA-256 do ZIP: `dec8e35b22a07ecad86a77fe16e9c5c7a54b35e4a05407860ae7155cffe3cafb`.

O notebook principal conserva a análise de 04/10. Na cópia revisada de 06/10, foi acrescentado o PNG histórico da CNN que faltava e uma nota explicativa; o código e a exportação original foram preservados. Este diretório documenta exclusivamente a rodada final que testa as correções. Uma tentativa anterior de 12/10 concluiu os cálculos, mas não permitiu recuperar o ZIP antes de a sessão temporária ser renovada e externalizou duas imagens grandes; por isso não foi usada como comprovação final. A rodada documentada aqui verifica também a correção das prévias e a preservação do pacote.
