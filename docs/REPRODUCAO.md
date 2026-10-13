# Reprodução da Fase 6

O notebook publicado já contém as saídas da execução `20261004T164740010266Z`, realizada em 04/10/2026. Para ler os resultados, não é necessário treinar novamente.

## Executar em outra conta, sem acesso ao Drive do autor

1. Abrir [o notebook público no Colab](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb) e salvar uma cópia no próprio Drive.
2. Selecionar um ambiente Python com GPU, se disponível. A sessão original utilizou Tesla T4. A CNN e o benchmark comparativo de inferência usam CPU por definição do experimento.
3. Usar **Ambiente de execução → Executar tudo**. A primeira célula já contém estas configurações; não é preciso editá-las nem autorizar a montagem do Drive:

```python
USE_DRIVE = False
DATASET_ZIP_URL = "https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/DATASET-FARMTECH-FASE6.zip"
```

4. O dataset será baixado automaticamente. O auditor confere imagens, rótulos, classes, grupos e duplicatas antes do treino. O ZIP contém `images/`, `labels/`, `fontes.csv` e créditos diretamente na raiz.
5. Aguardar os treinos independentes de 30 e 60 épocas, a CNN, as avaliações e o benchmark. Os resultados terão um novo identificador de execução; não sobrescrevem os resultados publicados.
6. Ao final, baixar o ZIP solicitado pela última célula e salvar também o notebook com as saídas. Com `USE_DRIVE=False`, os arquivos ficam no disco temporário do Colab e devem ser baixados antes do encerramento da sessão.

As saídas, os contadores e a discussão do notebook principal continuam correspondendo à execução de 04/10, que usou os dados no Drive. Em 12/10, os dois padrões de acesso aos dados foram atualizados para os valores acima, já usados na execução integral de 06/10. Os cálculos, os splits e os hiperparâmetros foram preservados. Essa primeira mudança de configuração não representou um terceiro treinamento. Na revisão posterior de 12/10, o código recebeu versões centrais fixas, exibição explícita de PNGs e comentários. A nova verificação dessas correções está documentada separadamente em `evidencias/reexecucao-20261012/`; as métricas históricas desta análise não são substituídas pelas novas.

## Alternativa: usar o próprio Google Drive

Baixar [o dataset](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/DATASET-FARMTECH-FASE6.zip), extrair e copiar o conteúdo para `Meu Drive/FarmTechFase6/dataset/`. Alterar a primeira célula para `USE_DRIVE=True` e `DATASET_ZIP_URL=""`. Autorizar a montagem do próprio Drive quando o Colab solicitar. Não criar um nível adicional `dataset/dataset`.

Para apenas salvar os resultados no Drive e continuar baixando o dataset público, usar `USE_DRIVE=True` e manter a URL do ZIP. Os arquivos e uma cópia do ZIP final serão preservados em `Meu Drive/FarmTechFase6/resultados/`. A montagem concede ao código acesso ao Drive; usar somente uma cópia do notebook que você conferiu.

## Arquivos para download

Na [versão publicada](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/tag/fase6-2026-10-04):

- `DATASET-FARMTECH-FASE6.zip`: 80 fotografias e rótulos, manifesto, créditos e protocolo.
- `RESULTADOS-FARMTECH-20261004T164740010266Z.zip`: todos os 96 artefatos originais, a cópia do notebook revisado daquela publicação e os registros de evidência. Contém `best.pt` e `last.pt` de cada experimento, a CNN, métricas e imagens. Para iniciar uma reprodução com a configuração pública atual, usar o notebook da raiz do repositório.
- `yolov5s_30_best.pt`, `yolov5s_60_best.pt` e `cnn_do_zero.keras`: checkpoints separados para conveniência. Os nomes originais e seus hashes constam no inventário da execução.
- `SHA256SUMS.txt`: hashes dos downloads. No PowerShell, usar `Get-FileHash -Algorithm SHA256 -LiteralPath 'caminho-do-arquivo'` para conferir.

Os pesos externos de inicialização são obtidos das fontes oficiais pelo notebook. Não é necessário compilar Darknet: o YOLOv3 usa OpenCV DNN.

## Dependências e gráficos

O ambiente indicado é **Colab Linux com Python 3.13**; a referência usou Python 3.13.15. A célula de instalação contém as mesmas 28 versões centrais de [`requirements-colab.txt`](../requirements-colab.txt) e as instala junto com os requisitos da revisão fixada do YOLOv5. A lista é embutida para que a cópia do notebook seja autossuficiente. `torch==2.11.0` e `torchvision==0.26.0` aceitam o sufixo CUDA/CPU da distribuição já instalada. O ambiente utilizado efetivamente continua registrado no `pip freeze` de cada rodada.

Não se congela o ambiente inteiro do Colab: dependências transitivas não listadas e componentes do serviço podem variar. As versões centrais fixas reduzem essa variação, mas não prometem resultados numericamente idênticos em qualquer plataforma. Usar uma sessão nova e executar de cima para baixo evita misturar módulos já importados com versões instaladas posteriormente.

As cinco figuras do notebook são salvas e exibidas explicitamente por `IPython.display.Image`. Isso funciona mesmo depois que o YOLOv5 seleciona o backend Matplotlib `Agg`; não depende de `plt.show()`. Figuras acima de 400 kB recebem uma prévia JPEG compacta para acompanhar a exportação do Colab; os PNGs completos permanecem no ZIP. Os PNGs originais ausentes das exportações antigas foram incorporados documentalmente, sem recalcular os resultados.

## Limites de reprodução

A revisão do YOLOv5 e as seeds estão fixadas. O ambiente original e as versões instaladas estão em `resultados/20261004T164740010266Z/ambiente.json` e `requirements-executados.txt`. Alterações no Colab, bibliotecas, GPU ou rede podem modificar tempos e resultados. A execução original concluiu todas as células após ajustes operacionais; a segunda execução integral em sessão limpa foi concluída em 06/10/2026, usando o ZIP público e sem montar o Drive durante as 15 células. Ver [registro e diferenças](../evidencias/reexecucao-20261006/README.md). O código não usa as imagens de teste para ajustar hiperparâmetros.
