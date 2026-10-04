# Reprodução da Fase 6

O notebook publicado já contém as saídas da execução `20261004T164740010266Z`, realizada em 04/10/2026. Para ler os resultados, não é necessário treinar novamente.

## Executar em outra conta, sem acesso ao Drive do autor

1. Abrir [o notebook público no Colab](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb) e salvar uma cópia no próprio Drive.
2. Selecionar um ambiente Python com GPU, se disponível. A sessão original utilizou Tesla T4. A CNN e o benchmark comparativo de inferência usam CPU por definição do experimento.
3. Na **primeira célula de código**, substituir somente estas duas configurações:

```python
USE_DRIVE = False
DATASET_ZIP_URL = "https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/DATASET-FARMTECH-FASE6.zip"
```

4. Executar as células em ordem. O auditor confere imagens, rótulos, classes, grupos e duplicatas antes do treino. O ZIP contém `images/`, `labels/`, `fontes.csv` e créditos diretamente na raiz.
5. Aguardar os treinos independentes de 30 e 60 épocas, a CNN, as avaliações e o benchmark. Os resultados terão um novo identificador de execução; não sobrescrevem os resultados publicados.
6. Ao final, baixar o ZIP solicitado pela última célula e salvar também o notebook com as saídas. Com `USE_DRIVE=False`, os arquivos ficam no disco temporário do Colab e devem ser baixados antes do encerramento da sessão.

O notebook preserva as configurações da execução original, que usou `USE_DRIVE=True` e os dados já presentes no Drive. As duas alterações acima são instruções para reproduzir em outra conta; não alteram os splits ou os hiperparâmetros do experimento.

## Alternativa: usar o próprio Google Drive

Baixar [o dataset](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/DATASET-FARMTECH-FASE6.zip), extrair e copiar o conteúdo para `Meu Drive/FarmTechFase6/dataset/`. Manter `USE_DRIVE=True` e `DATASET_ZIP_URL=""`. Autorizar a montagem do próprio Drive quando o Colab solicitar. Não criar um nível adicional `dataset/dataset`.

## Arquivos para download

Na [versão publicada](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/tag/fase6-2026-10-04):

- `DATASET-FARMTECH-FASE6.zip`: 80 fotografias e rótulos, manifesto, créditos e protocolo.
- `RESULTADOS-FARMTECH-20261004T164740010266Z.zip`: todos os 96 artefatos originais, notebook revisado e registros de evidência. Contém `best.pt` e `last.pt` de cada experimento, a CNN, métricas e imagens.
- `yolov5s_30_best.pt`, `yolov5s_60_best.pt` e `cnn_do_zero.keras`: checkpoints separados para conveniência. Os nomes originais e seus hashes constam no inventário da execução.
- `SHA256SUMS.txt`: hashes dos downloads. No PowerShell, usar `Get-FileHash -Algorithm SHA256 -LiteralPath 'caminho-do-arquivo'` para conferir.

Os pesos externos de inicialização são obtidos das fontes oficiais pelo notebook. Não é necessário compilar Darknet: o YOLOv3 usa OpenCV DNN.

## Limites de reprodução

A revisão do YOLOv5 e as seeds estão fixadas. O ambiente original e as versões instaladas estão em `resultados/20261004T164740010266Z/ambiente.json` e `requirements-executados.txt`. Alterações no Colab, bibliotecas, GPU ou rede podem modificar tempos e resultados. A execução original concluiu todas as células após ajustes operacionais; uma segunda execução integral em sessão limpa ainda não foi realizada. O código não usa as imagens de teste para ajustar hiperparâmetros.
