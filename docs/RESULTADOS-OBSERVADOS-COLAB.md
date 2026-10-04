# Execução observada no Colab — 04/10/2026

Registro das saídas reais lidas na interface do notebook e conferidas nos CSVs recuperados do Drive. A análise completa está no notebook executado; este arquivo mantém um resumo da evidência da sessão.

- Autor: Matheus Silva Riscado, RM573622.
- Execução: `20261004T164740010266Z`.
- [Notebook executado](https://colab.research.google.com/drive/1-sFLeLbrjNCv6DkZIa4gj57npGw_rIHP). Permissões públicas ainda não verificadas.
- Resultados no Drive: `Meu Drive/FarmTechFase6/resultados/20261004T164740010266Z`.
- Ambiente observado: Python 3.13.15, PyTorch 2.11.0+cu130, Tesla T4; revisão YOLOv5 `2b1bdcd03663afe204bb614593f78be3facfbcaa`.
- Auditoria do dataset aprovada no Colab: 32/4/4 imagens de cada classe.

## Detecção YOLOv5

Valores arredondados como exibidos na célula 22. Precisão e recall desta tabela são os retornados pelo avaliador de detecção, distintos da classificação por imagem.

| Conjunto | Épocas | Precisão | Recall | mAP@0,5 | mAP@0,5:0,95 | Treino (s) |
|---|---:|---:|---:|---:|---:|---:|
| Validação | 30 | 0,8658 | 0,5689 | 0,6190 | 0,3861 | 202,4026 |
| Validação | 60 | 0,8377 | 0,6188 | 0,6654 | 0,4267 | 341,1113 |
| Teste | 30 | 0,8544 | 0,7970 | 0,8538 | 0,5703 | 202,4026 |
| Teste | 60 | 0,9272 | 0,6171 | 0,8247 | 0,5454 | 341,1113 |

O modelo de 60 épocas foi selecionado pela maior mAP@0,5:0,95 de validação, antes do teste. No teste, 30 épocas alcançaram maior mAP. A seleção não deve ser alterada retroativamente pelo teste; a inversão evidencia a incerteza da comparação com apenas oito imagens por conjunto.

## Classificação por imagem e inferência

Saídas das células 20, 22 e 28. Ausência de detecção conta como erro; F1 macro considera as duas classes-alvo. Tempos medidos em CPU, uma thread por biblioteca, imagens previamente carregadas, três aquecimentos e cinco repetições das oito imagens de teste. Incluem o pré-processamento da função de predição; não incluem leitura do disco. YOLOv5 usa entrada 640, YOLOv3 416 e CNN 128; a comparação é das soluções configuradas, não isola a arquitetura.

| Modelo | Acertos validação | Acertos teste | Sem detecção no teste | Acurácia teste | F1 macro teste | Mediana (ms) | p95 (ms) | Treino (s) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| YOLOv5 — 30 épocas | 8/8 | 5/8 | 2 | 0,625 | 0,7083 | 177,3641 | 240,0879 | 202,4026 |
| YOLOv5 — 60 épocas | 7/8 | 6/8 | 2 | 0,750 | 0,8571 | 179,6975 | 282,6380 | 341,1113 |
| YOLOv3 padrão | 6/8 | 7/8 | 1 | 0,875 | 0,9286 | 1015,9531 | 1265,0463 | Não aplicável |
| CNN do zero | 5/8 | 5/8 | 0 | 0,625 | 0,5636 | 24,3145 | 34,5118 | 10,4486 |

O custo do pré-treino externo do YOLOv3 não foi medido. O YOLOv3 teve mais acertos de classificação no teste, porém maior latência em CPU. O YOLOv5 de 60 épocas oferece localização e menor latência que o YOLOv3, mas deixou duas imagens sem detecção no limiar adotado. A CNN foi mais rápida e teve menor F1; não produz caixas. Não se deve comparar a acurácia da CNN diretamente com a mAP dos detectores.

## CNN e limitações

A CNN tem 23.714 parâmetros e foi inicializada do zero. A parada antecipada encerrou o treino após sete épocas e restaurou o melhor checkpoint de validação. A perda de treino caiu de 0,6914 para 0,4609, enquanto a perda de validação subiu de 0,6945 para 1,0890. A acurácia de treino chegou a 0,8281 e a de validação da última época ficou em 0,5000: sinal de sobreajuste. O modelo restaurado acertou 5/8 imagens tanto na validação como no teste. A hipótese de memorizar cores/fundos deve ser apresentada como hipótese, não como causa comprovada.

O conjunto tem 80 imagens, uma única divisão e uma seed; um erro representa 12,5 pontos percentuais no teste. Pré-treino externo, fotografias públicas, possíveis semelhanças de cena e a convenção banana/penca/cacho limitam a comparação. Não houve avaliação de classes desconhecidas nem validação em produção. Mais épocas não garantiram melhor teste. A recomendação é ampliar e diversificar a base, repetir o protocolo com grupos independentes e revisar os casos de falha antes de escolher uma solução para uso real.

## Correção operacional e preservação

O endereço antigo dos pesos YOLOv3 retornou HTTP 403. A [página oficial](https://pjreddie.com/darknet/yolo/) indica `https://data.pjreddie.com/files/yolov3.weights`. O download nesse endereço funcionou com `urllib.request.Request` e cabeçalho `User-Agent`; o arquivo foi gravado primeiro em `.part` e renomeado após a transferência. A célula registra as fontes e hashes em JSON. A correção foi aplicada no Colab e no código local.

Os treinos, avaliações, medição de tempo e checagem final dos artefatos foram concluídos. O notebook original executado e os 96 arquivos de resultados foram recuperados do Drive e preservados localmente. As curvas, matrizes de confusão e todas as oito imagens do painel de teste foram inspecionadas; a discussão foi concluída com base nesses dados.

A versão final mantém os códigos e contadores da exportação executada. Os dois gráficos das células 24 e 26, ausentes na exportação inicial, foram reincorporados a partir dos PNGs originais gravados por essas células, com origem e SHA-256 registrados. Nenhuma métrica ou saída numérica foi inventada. A cópia original está em `evidencias/colab/notebook-executado-original.ipynb`; a verificação e os hashes estão em `docs/VERIFICACAO-EXECUCAO.json`.

As retomadas da sessão estão documentadas. Ainda falta uma segunda reprodução integral em sessão limpa, publicar os acessos para o avaliador, gravar o vídeo e enviar a entrega no portal.
