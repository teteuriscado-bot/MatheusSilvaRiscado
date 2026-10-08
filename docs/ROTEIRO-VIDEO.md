# Roteiro clicável de apresentação — Fase 6

**[Abrir versão HTML para tablet](https://teteuriscado-bot.github.io/MatheusSilvaRiscado/roteiro-video.html)** · [Arquivo HTML](roteiro-video.html)

Matheus Silva Riscado · RM573622 · individual. Meta: **4min40s**, limite: **5 minutos**. Resultados apresentados: **04/10/2026**.

## Antes de gravar

1. Use o tablet para acompanhar este roteiro e o computador para mostrar os materiais na gravação. Abra no computador as telas essenciais antes de começar.
2. Leia somente o bloco “Sua fala”. Os passos e lembretes servem para orientar você e não precisam ser narrados.
3. Toque nos botões na ordem indicada. Os materiais externos abrem em outra aba; volte a esta aba para continuar a leitura.
4. O notebook público já tem as saídas salvas. Os links do Colab apontam para células específicas; se ele abrir no início, use o índice e o nome da seção indicado.
5. Faça um ensaio com cronômetro. A meta é 4min40s, com margem de 20 segundos até o limite de 5 minutos. Não precisa esperar até o fim de cada intervalo para avançar.
6. Teste o áudio por dez segundos e confira a legibilidade das tabelas. Avance com calma e mantenha as notificações fechadas.

## 1. 00:00–00:20 — Apresentação

**Abra nesta ordem:** [Abrir início do notebook](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-000)

**O que mostrar:**

1. Deixe o título, seu nome e RM visíveis. Não precisa mostrar código nesta abertura.
2. Apresente o problema do cliente: reconhecer e localizar garrafas e bananas em imagens.

**Sua fala:**

> Olá, meu nome é Matheus Silva Riscado, RM573622. Este é meu projeto individual da Fase 6. O objetivo é demonstrar, para um cliente da FarmTech Solutions, como reconhecer garrafas e bananas em imagens, comparando três abordagens de visão computacional.

**O que precisa ficar claro:** Nome correto: Matheus Silva Riscado · RM573622. Projeto individual.

**Lembrete:** Comece falando com a tela já posicionada. Não gaste tempo procurando o arquivo.

**Links de apoio — use se precisar:**

- [README do projeto](https://github.com/teteuriscado-bot/MatheusSilvaRiscado#readme)

## 2. 00:20–00:55 — Dados e rotulação

**Abra nesta ordem:** [Abrir pastas no Drive](https://drive.google.com/drive/folders/1vtCE3Yxtwg4QInujzWFNeSr1az2zXsX6) → [Abrir caixa no Make Sense](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/evidencias/makesense/garrafa_001.jpg)

**O que mostrar:**

1. No Drive, mostre as pastas train, val e test. Elas correspondem a treino, validação e teste.
2. Na captura do Make Sense, aponte para a caixa ao redor da garrafa e para sua classe.
3. Explique a divisão por classe: 32 / 4 / 4. No total, são 64 / 8 / 8 imagens.

**Sua fala:**

> Organizei 80 fotografias reais: 40 de garrafas e 40 de bananas. Para cada classe, separei 32 para treino, quatro para validação e quatro para teste. Os dados e rótulos estão organizados no Drive. As caixas foram revisadas no Make Sense AI, totalizando 173 anotações. A auditoria verificou duplicatas e a separação dos grupos entre os conjuntos.

**O que precisa ficar claro:** 173 é a quantidade de caixas anotadas. Uma penca ou cacho conectado pode receber uma única caixa.

**Lembrete:** Não precisa falar “14 fotos próprias e 66 da internet”. Os créditos continuam documentados. O Drive requer a conta do projeto; as pastas públicas são a alternativa para visualizar os dados.

**Links de apoio — use se precisar:**

- [Treino no Drive](https://drive.google.com/drive/folders/1HztuD8YZfSciZcvmKBTZfq6_xy7DdoQb)
- [Validação no Drive](https://drive.google.com/drive/folders/11J5X5gVXRGmcfe5QoFvqSQ1u885ZzMM7)
- [Teste no Drive](https://drive.google.com/drive/folders/1gbfAwNKidjwgRUfaRwGmttgOhzHnXv_Y)
- [Rótulos no Drive](https://drive.google.com/drive/folders/1R6MvIBucF8M5j5z9ds0Ar6vACxqgW5uU)
- [Pastas públicas — alternativa ao Drive](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/tree/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/dataset/images)
- [Auditoria no Colab](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-004)
- [Exemplos de caixas revisadas](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/amostras_rotuladas.png)
- [Origens e créditos das fotos](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/dataset/fontes.csv)

## 3. 00:55–01:40 — Treinamento e seleção

**Abra nesta ordem:** [Abrir os dois experimentos](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-008) → [Abrir gráfico de 30 × 60 épocas](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/comparacao_epocas.png)

**O que mostrar:**

1. Mostre que foram executados dois treinos independentes: 30 e 60 épocas.
2. No gráfico, identifique as duas curvas e as perdas de localização e de classe.
3. Na comparação, aponte a mAP de validação: 0,3861 → 0,4267; tempo: 202,40 → 341,11 segundos.
4. Explique que a seleção de 60 épocas foi feita pela validação, antes de olhar o teste.

**Sua fala:**

> Treinei o YOLOv5 em dois experimentos independentes, com 30 e 60 épocas, mantendo os mesmos pesos iniciais e parâmetros principais. Uma época corresponde a uma passagem pelos dados de treino. A mAP de validação, que avalia a qualidade das detecções, passou de aproximadamente 0,386 para 0,427. O tempo de treino aumentou de 202 para 341 segundos. Por esse critério, selecionei 60 épocas antes de consultar o teste. No teste, 30 épocas teve maior mAP, mostrando que mais treinamento não garante melhor resultado em novas imagens.

**O que precisa ficar claro:** 60 épocas não continua o treino de 30. Os dois começam nos mesmos pesos pré-treinados.

**Lembrete:** Leia mAP como “éme-á-pê”. Ela avalia detecção e localização; não diga que 0,4267 significa 42,67% das imagens acertadas.

**Links de apoio — use se precisar:**

- [Configuração das épocas e seed](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-001)
- [Código e logs de treino](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-009)
- [Resumo dos dois treinos](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-014)
- [Métricas de validação e teste](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/metricas_deteccao.csv)

## 4. 01:40–02:20 — Demonstração das detecções

**Abra nesta ordem:** [Abrir as oito imagens processadas](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/painel_teste.png) → [Abrir código e saída no Colab](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-026)

**O que mostrar:**

1. No painel completo, comece pelas três garrafas de vidro: primeira imagem da linha inferior.
2. Aponte a falha na banana solta sobre tecido: primeira imagem da linha superior.
3. Aponte o cacho na árvore: terceira imagem da linha superior. A caixa cobre só parte do alvo.
4. Use as ampliações abaixo se precisar mostrar melhor um detalhe.

**Sua fala:**

> Aqui estão as saídas reais do modelo selecionado nas oito imagens de teste. Nas garrafas de vidro, ele encontrou os objetos e desenhou as caixas. Já na banana solta sobre tecido, não houve detecção acima do limiar definido. Também há um cacho em que a caixa cobre apenas parte do alvo. Por isso, reconhecer a classe e localizar corretamente o objeto são avaliações diferentes. Mantive os acertos e as falhas no relatório.

**O que precisa ficar claro:** As caixas laranja são previsões do modelo. As caixas revisadas para treino são anotações de referência: são etapas diferentes.

**Lembrete:** Este roteiro mostra saídas reais já executadas. Não precisa clicar em “Executar tudo”. Diga “aqui estão as saídas”, sem afirmar que acabou de executar algo que já estava salvo.

**Links de apoio — use se precisar:**

- [Ampliar acerto: garrafas de vidro](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/imagens_teste/garrafa_020_predicao.jpg)
- [Ampliar falha: banana solta](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/imagens_teste/banana_002_predicao.jpg)
- [Ampliar caixa parcial: cacho](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/imagens_teste/banana_035_predicao.jpg)
- [Ampliar falha: garrafa na lama](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/imagens_teste/garrafa_038_predicao.jpg)
- [Código da inferência](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-018)
- [Avaliação no teste](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-022)

## 5. 02:20–03:15 — Comparação dos modelos

**Abra nesta ordem:** [Abrir tabela de resultados](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-028) → [Abrir comparação em CSV](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/comparacao_final.csv)

**O que mostrar:**

1. Mostre a coluna de acertos: YOLOv3 = 7; YOLOv5 60 = 6; YOLOv5 30 = 5; CNN = 5, sempre de oito imagens.
2. Depois, mostre a mediana de inferência em CPU: aproximadamente 1 segundo, 180 ms e 24 ms.
3. Diga que a CNN classifica a imagem inteira; YOLO também localiza com caixas.
4. Não leia todas as colunas. A fala já seleciona o que importa.

**Sua fala:**

> Comparei os modelos nas mesmas oito imagens. O YOLOv3 acertou a classe em sete; o YOLOv5 de 60 épocas, em seis; o de 30 épocas e a CNN, em cinco. Ausências de detecção contam como erro. Esses números medem classificação por imagem, não a qualidade completa das caixas. Na inferência em CPU, as medianas foram aproximadamente um segundo para o YOLOv3, 180 milissegundos para o YOLOv5 de 60 épocas e 24 para a CNN. A CNN foi treinada do zero em cerca de dez segundos, mas só classifica a imagem: ela não localiza os objetos.

**O que precisa ficar claro:** Sem detecção entra como erro. Esses acertos são de classe por imagem e não significam que todas as caixas estejam corretas.

**Lembrete:** Inferência é usar o modelo treinado para prever uma imagem. A CNN foi rápida nesta configuração, mas não resolve sozinha a localização.

**Links de apoio — use se precisar:**

- [Discussão e tabelas explicadas](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-029)
- [CNN do zero: arquitetura e treino](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-015)
- [YOLOv3: implementação](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-017)
- [Matrizes de confusão](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/matrizes_confusao_teste.png)

## 6. 03:15–04:15 — Conclusões e limitações

**Abra nesta ordem:** [Abrir curvas da CNN](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/cnn_curvas.png) → [Abrir discussão e conclusões](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-029)

**O que mostrar:**

1. No gráfico de perda da CNN, aponte a curva de treino descendo e a de validação subindo.
2. Explique o sobreajuste em linguagem simples: aprender o treino sem manter a qualidade na validação.
3. Compare o esforço de integração: rotular e treinar YOLOv5; configurar pesos e OpenCV no YOLOv3; treinar a CNN no TensorFlow.
4. Conclua com a escolha pela validação e a necessidade de ampliar as cenas antes de uso real.

**Sua fala:**

> Na integração, o YOLOv5 exigiu rotulação e treinamento, mas entrega classes e caixas. O YOLOv3 dispensou treino local, usando pesos prontos e OpenCV. A CNN tem integração compacta com TensorFlow, porém apresentou sobreajuste: a perda de treino caiu enquanto a de validação aumentou. O treinamento foi interrompido e os melhores pesos de validação foram recuperados. Para continuar o protótipo de localização, mantive o YOLOv5 de 60 épocas, escolhido pela validação. O YOLOv3 permanece como referência, pois acertou mais classes neste teste. Como há apenas oito imagens de teste, seria necessário ampliar a base e avaliar novas condições antes de usar a solução em produção.

**O que precisa ficar claro:** No teste, 30 épocas teve maior mAP de localização e 60 épocas teve mais acertos de classe. São critérios diferentes; isso não é uma contradição.

**Lembrete:** Apenas oito imagens de teste: cada imagem muda a acurácia em 12,5 pontos percentuais. Apresente um protótipo acadêmico, sem prometer desempenho geral.

**Links de apoio — use se precisar:**

- [Treino e parada antecipada da CNN](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-016)
- [Configuração executada da CNN](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/cnn_configuracao.json)
- [Critério registrado de seleção](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/selecao_validacao.json)

## 7. 04:15–04:40 — Reprodução e encerramento

**Abra nesta ordem:** [Abrir README no GitHub](https://github.com/teteuriscado-bot/MatheusSilvaRiscado#readme) → [Abrir evidência da sessão limpa](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/tree/main/evidencias/reexecucao-20261006)

**O que mostrar:**

1. No README, mostre os links do notebook, dos dados e dos resultados.
2. Mostre rapidamente que a sessão limpa terminou com 15 células sem erro.
3. Encerre. A publicação do vídeo e o envio pelo portal são realizados depois da gravação.

**Sua fala:**

> O repositório reúne o notebook executado, os dados, os modelos e os resultados. Também fiz uma segunda execução completa em sessão limpa, com as 15 células concluídas sem erro. Houve variação nas métricas, registrada separadamente. O projeto demonstra o funcionamento da solução e apresenta seus limites e os próximos passos. Obrigado.

**O que precisa ficar claro:** Os números apresentados até aqui são de 04/10/2026. A rodada de 06/10 confirma execução e registra a variação separadamente.

**Lembrete:** Depois, publique no YouTube como não listado, inclua o link no README e envie o GitHub no portal antes do prazo. Evite novos commits após a entrega final.

**Links de apoio — use se precisar:**

- [Baixar dataset público](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/DATASET-FARMTECH-FASE6.zip)
- [Modelos e resultados para download](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/tag/fase6-2026-10-04)
- [Como reproduzir](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/docs/REPRODUCAO.md)
- [Registro das 15 células](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/main/docs/VERIFICACAO-SESSAO-LIMPA.json)
- [Checklist de avaliação](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/docs/CHECKLIST-BAREMA.md)

## Dúvidas para o ensaio

**Preciso dizer quantas fotos são minhas e quantas vieram da internet?**

Não é obrigatório narrar essa contagem. Diga que organizou 80 fotografias reais, 40 por classe. A origem e as licenças continuam no manifesto e nos créditos; se perguntarem, informe 14 próprias e 66 do Wikimedia Commons.

**Preciso treinar tudo enquanto gravo?**

Não. Mostre o código, os registros de execução e as saídas reais já preservadas. Se quiser demonstrar uma inferência ao vivo, prepare antes uma sessão com os pesos da rodada de 04/10 e execute apenas a inferência; não apresente saída salva como execução ao vivo.

**Por que escolhi 60 épocas se 30 teve maior mAP no teste?**

A escolha foi feita antes, pela validação. Manter essa escolha preserva o papel do teste como avaliação final. Mais épocas melhorou a validação desta rodada, mas não garantiu maior mAP no teste.

**Por que não escolhi automaticamente o YOLOv3?**

Ele acertou mais classes no pequeno teste, mas a escolha entre os dois YOLOv5 já tinha sido feita pela validação. Para continuar o protótipo, foram considerados localização, integração e latência. O YOLOv3 segue como referência, sem afirmar que um modelo é superior em qualquer cenário.

**Qual é a diferença entre acurácia e mAP?**

Acurácia por imagem responde quantas imagens tiveram a classe correta. A mAP de detecção também considera a localização das caixas. Acertar “banana” não garante cobrir corretamente todo o cacho.

**Como explico o sobreajuste?**

O modelo melhora no conjunto de treino, mas não mantém essa melhora nos dados separados para validação. Nas curvas da CNN, a perda de treino cai enquanto a perda de validação sobe.

**Os resultados da sessão limpa são iguais?**

Não exatamente. Em 06/10, os YOLOv5 variaram em uma imagem de teste cada. A segunda execução confirmou o funcionamento do código, e a variação está documentada. Este roteiro usa apenas os números de 04/10.

**O Drive pediu autorização. O que faço?**

Abra a conta do Google em que o projeto foi organizado. Para mostrar os arquivos sem depender dessa conta, use o botão “Pastas públicas — alternativa ao Drive”. Não é preciso alterar o compartilhamento das pastas pessoais.

## Conferência dos números

| Modelo | Acertos no teste | Acurácia | Mediana CPU |
|---|---:|---:|---:|
| YOLOv3 padrão | 7/8 | 87,5% | 1.015,95 ms |
| YOLOv5 · 60 épocas | 6/8 | 75,0% | 179,70 ms |
| YOLOv5 · 30 épocas | 5/8 | 62,5% | 177,36 ms |
| CNN do zero | 5/8 | 62,5% | 24,31 ms |

mAP@0,5:0,95 de validação: **0,3861 → 0,4267**. No teste: **0,5703 → 0,5454**. Tempo dos treinos YOLOv5: **202,40 → 341,11 s** em T4. CNN: **10,45 s** em CPU, sete épocas, recuperação da época 1.

As 173 caixas não equivalem a 173 frutos individuais. A CNN classifica e não prevê caixas. Inferência inclui pré/pós-processamento, mas exclui leitura de disco e carregamento dos modelos. O pré-treino externo do YOLOv3 não foi medido.

Depois de gravar: vídeo não listado no YouTube, link no README, envio no portal dentro do prazo e nenhum commit após a entrega final. Fontes: enunciado fornecido, notebook principal e CSVs da execução `20261004T164740010266Z`.
