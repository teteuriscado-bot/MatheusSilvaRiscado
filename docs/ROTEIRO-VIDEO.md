# Roteiro clicável de apresentação — Fase 6

**[Abrir versão HTML para tablet](https://teteuriscado-bot.github.io/MatheusSilvaRiscado/roteiro-video.html)** · [Arquivo HTML](roteiro-video.html)

Matheus Silva Riscado · RM573622 · individual. Meta: **4min30s**, limite: **5 minutos**. Resultados apresentados: **04/10/2026**.

## Antes de gravar

1. Use o tablet para acompanhar este roteiro e o computador para mostrar os materiais na gravação. Abra no computador as telas essenciais antes de começar.
2. A gravação analisada passou de cinco minutos. Esta versão foi encurtada, mas a duração só estará confirmada depois de ensaiar com as trocas de tela.
3. Durante gráficos, tabelas e detecções, oculte a câmera ou posicione-a fora do conteúdo. O rosto não é exigido pelo enunciado. Na abertura e no encerramento, use se quiser.
4. Amplie os textos e confira uma captura de teste. Use a tabela ampliada na etapa 5. Se possível, grave em 1080p; resolução maior é uma melhoria de legibilidade, não uma exigência do enunciado.
5. Leia somente o bloco “Sua fala”. Os passos e lembretes servem para orientar você e não precisam ser narrados.
6. As quebras de parágrafo sugerem pequenas pausas. Use a fala como apoio e mantenha seu jeito de explicar; não precisa decorar nem acrescentar “né” ou “é” a cada frase.
7. Para os nomes, mantenha “YOLO vê três” e “YOLO vê cinco”. Leia CNN como “sê-ene-ene”. O glossário nas dúvidas tem os outros termos.
8. Toque nos botões na ordem indicada. Os materiais externos abrem em outra aba; volte a esta aba para continuar a leitura.
9. O notebook público já tem as saídas salvas. Os links do Colab apontam para células específicas; se ele abrir no início, use o índice e o nome da seção indicado.
10. Faça um ensaio com cronômetro. A meta é 4min30s, com margem de 30 segundos até o limite de 5 minutos. Os horários são metas, não a duração já medida da sua fala. Não espere o intervalo terminar para avançar.
11. Teste o áudio por dez segundos e confira a legibilidade das tabelas. Avance com calma e mantenha as notificações fechadas.

## 1. 00:00–00:20 — Apresentação

**Abra nesta ordem:** [Abrir início do notebook](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-000)

**O que mostrar:**

1. Deixe o título, seu nome e RM visíveis. Não precisa mostrar código nesta abertura.
2. Apresente o problema do cliente: reconhecer e localizar garrafas e bananas em imagens.

**Sua fala:**

> Olá, sou Matheus Silva Riscado, RM573622. Neste projeto individual da Fase 6, comparei três abordagens para reconhecer garrafas e bananas, demonstrando visão computacional para um cliente da FarmTech Solutions.

**O que precisa ficar claro:** Nome correto: Matheus Silva Riscado · RM573622. Projeto individual.

**Lembrete:** Comece com a tela posicionada. Mantenha nome e RM na abertura. O RM registrado é 573622: cinco, sete, três, seis, dois, dois.

**Links de apoio — use se precisar:**

- [README do projeto](https://github.com/teteuriscado-bot/MatheusSilvaRiscado#readme)

## 2. 00:20–00:55 — Dados e rotulação

**Abra nesta ordem:** [Abrir pastas no Drive](https://drive.google.com/drive/folders/1vtCE3Yxtwg4QInujzWFNeSr1az2zXsX6) → [Abrir caixa no Make Sense](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/evidencias/makesense/garrafa_001.jpg)

**O que mostrar:**

1. No Drive, mostre as pastas train, val e test. Elas correspondem a treino, validação e teste.
2. Na captura do Make Sense, aponte para a caixa ao redor da garrafa e para sua classe.
3. Explique a divisão por classe: 32 / 4 / 4. No total, são 64 / 8 / 8 imagens.

**Sua fala:**

> Organizei 80 fotos: 40 de garrafas e 40 de bananas. Por classe, são 32 para treino, quatro para validação e quatro para teste.
>
> As imagens e os rótulos estão no Drive. Revisei 173 caixas no Make Sense AI e conferi duplicatas e grupos, para reduzir o risco de vazamento entre os conjuntos.

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

> Treinei o YOLOv5 por 30 e 60 épocas, em experimentos independentes, com os mesmos pesos iniciais e parâmetros principais.
>
> Comparei as curvas de perda e a mAP de validação, que passou de 0,386 para 0,427. O treino em GPU levou 202 e 341 segundos.
>
> Escolhi 60 épocas pela validação, antes de olhar o teste. No teste, 30 épocas teve maior mAP. Neste experimento, treinar mais não garantiu melhor detecção nas imagens de teste.

**O que precisa ficar claro:** 60 épocas não continua o treino de 30. Os dois começam nos mesmos pesos pré-treinados.

**Lembrete:** Leia mAP como “ême-á-pê”. A conclusão vale para este experimento: não diga que treinar mais nunca ajuda. A mAP avalia detecção e localização; 0,4267 não significa 42,67% das imagens acertadas. Não deixe a câmera cobrir o gráfico.

**Links de apoio — use se precisar:**

- [Configuração das épocas e seed](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-001)
- [Código e logs de treino](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-009)
- [Resumo dos dois treinos](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-014)
- [Métricas de validação e teste](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/metricas_deteccao.csv)

## 4. 01:40–02:20 — Demonstração das detecções

**Abra nesta ordem:** [Abrir as oito imagens processadas](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/painel_teste.png) → [Abrir código e saída no Colab](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-026)

**O que mostrar:**

1. Oculte a câmera ou coloque-a fora do conteúdo. No vídeo anterior, ela cobriu as garrafas de vidro no canto inferior esquerdo.
2. No painel completo, aponte com o cursor as três garrafas de vidro: primeira imagem da linha inferior.
3. Aponte a falha na banana solta sobre tecido: primeira imagem da linha superior.
4. Aponte o cacho na árvore: terceira imagem da linha superior. A caixa cobre só parte do alvo.
5. Use as ampliações abaixo se precisar mostrar melhor um detalhe.

**Sua fala:**

> Aqui estão as oito imagens de teste. O modelo encontrou essas garrafas e desenhou as caixas.
>
> Nessa banana sobre tecido, não houve detecção acima do limite de confiança. Nesse cacho, a caixa cobriu só parte do alvo.
>
> Reconhecer a classe e localizar corretamente são coisas diferentes. Por isso, mostrei acertos e falhas.

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

**Abra nesta ordem:** [Abrir tabela ampliada para o vídeo](https://teteuriscado-bot.github.io/MatheusSilvaRiscado/comparacao-video.html) → [Abrir tabela original no notebook](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-028)

**O que mostrar:**

1. Mostre a coluna de acertos: YOLOv3 = 7; YOLOv5 60 = 6; YOLOv5 30 = 5; CNN = 5, sempre de oito imagens.
2. Depois, mostre a mediana de inferência em CPU: aproximadamente 1 segundo, 180 ms e 24 ms.
3. Diga que a CNN classifica a imagem inteira; YOLO também localiza com caixas.
4. A tabela ampliada usa os mesmos CSVs originais. Mantenha o notebook aberto para mostrar a origem, se necessário.
5. Não deixe colunas ocultas por reticências. Aponte cada linha enquanto fala.

**Sua fala:**

> Nas mesmas oito imagens, o YOLOv3 acertou a classe em sete; o YOLOv5 de 60 épocas, em seis; o de 30 épocas e a CNN, em cinco.
>
> Se o modelo não detectou o objeto, contei como erro. Esses acertos avaliam a classe, não a qualidade das caixas.
>
> Na inferência em CPU, as medianas foram cerca de um segundo para o YOLOv3, 180 milissegundos para o YOLOv5 de 60 épocas e 24 para a CNN. Ela foi treinada do zero em dez segundos, em CPU, e apenas classifica a imagem.

**O que precisa ficar claro:** Sem detecção entra como erro. Esses acertos são de classe por imagem e não significam que todas as caixas estejam corretas.

**Lembrete:** Diga “inferência”, não “interferência”. São modelos comparados nas mesmas oito imagens, não oito modelos. Faça uma pequena pausa entre os tempos. A comparação de inferência foi em CPU; os treinos YOLOv5 foram em GPU T4 e o da CNN em CPU.

**Links de apoio — use se precisar:**

- [Comparação original em CSV](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/comparacao_final.csv)
- [Discussão e tabelas explicadas](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-029)
- [CNN do zero: arquitetura e treino](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-015)
- [YOLOv3: implementação](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-017)
- [Matrizes de confusão](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/matrizes_confusao_teste.png)

## 6. 03:15–04:10 — Conclusões e limitações

**Abra nesta ordem:** [Abrir curvas da CNN](https://raw.githubusercontent.com/teteuriscado-bot/MatheusSilvaRiscado/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/cnn_curvas.png) → [Abrir discussão e conclusões](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-029)

**O que mostrar:**

1. No gráfico de perda da CNN, aponte a curva de treino descendo e a de validação subindo.
2. Explique o sobreajuste em linguagem simples: aprender o treino sem manter a qualidade na validação.
3. Compare o esforço de integração: rotular e treinar YOLOv5; configurar pesos e OpenCV no YOLOv3; treinar a CNN no TensorFlow.
4. Conclua com a escolha pela validação e a necessidade de ampliar as cenas antes de uso real.

**Sua fala:**

> Na integração, o YOLOv5 exigiu rotulação e treino. O YOLOv3 usou pesos prontos com OpenCV, sem treino local. Na CNN, defini e treinei a rede no TensorFlow.
>
> A CNN apresentou sobreajuste: a perda de treino caiu e a de validação subiu. A parada antecipada recuperou os melhores pesos de validação.
>
> Mantive o YOLOv5 de 60 épocas para continuar o protótipo de localização. O YOLOv3 segue como referência pelos acertos. Como são só oito imagens de teste, é preciso ampliar a base e avaliar novas condições antes de usar em produção.

**O que precisa ficar claro:** No teste, 30 épocas teve maior mAP de localização e 60 épocas teve mais acertos de classe. São critérios diferentes; isso não é uma contradição.

**Lembrete:** A primeira parte compara o trabalho para integrar cada solução. Em seguida, mostre o sobreajuste na curva da CNN. Com oito imagens de teste, cada imagem muda a acurácia em 12,5 pontos percentuais; não é uma garantia de desempenho em produção.

**Links de apoio — use se precisar:**

- [Treino e parada antecipada da CNN](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb#scrollTo=fase6-016)
- [Configuração executada da CNN](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/cnn_configuracao.json)
- [Critério registrado de seleção](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/resultados/20261004T164740010266Z/selecao_validacao.json)

## 7. 04:10–04:30 — Reprodução e encerramento

**Abra nesta ordem:** [Abrir README no GitHub](https://github.com/teteuriscado-bot/MatheusSilvaRiscado#readme) → [Abrir evidência da sessão limpa](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/tree/main/evidencias/reexecucao-20261006)

**O que mostrar:**

1. No README, mostre os links do notebook, dos dados e dos resultados.
2. Mostre rapidamente que a sessão limpa terminou com 15 células sem erro.
3. Encerre. A publicação do vídeo e o envio pelo portal são realizados depois da gravação.

**Sua fala:**

> O GitHub reúne o notebook, os dados, os modelos e os resultados. Na segunda execução em sessão limpa, as 15 células terminaram sem erro. A variação das métricas está documentada. Obrigado.

**O que precisa ficar claro:** Os números apresentados até aqui são de 04/10/2026. A rodada de 06/10 confirma execução e registra a variação separadamente.

**Lembrete:** Depois, publique no YouTube como não listado, inclua o link no README e envie o GitHub no portal antes do prazo. Evite novos commits após a entrega final.

**Links de apoio — use se precisar:**

- [Baixar dataset público](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/DATASET-FARMTECH-FASE6.zip)
- [Modelos e resultados para download](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/tag/fase6-2026-10-04)
- [Como reproduzir](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/docs/REPRODUCAO.md)
- [Registro das 15 células](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/main/docs/VERIFICACAO-SESSAO-LIMPA.json)
- [Checklist de avaliação](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/blob/aa36b194fc8cc42f98099f350a9f562e5cd8db0a/docs/CHECKLIST-BAREMA.md)

## Dúvidas para o ensaio

**A observação sobre os labels da CNN exige refazer as caixas?**

Não neste projeto. O notebook transforma a classe das anotações em um rótulo por imagem: 0 para garrafa e 1 para banana. A CNN recebe a imagem inteira e esse rótulo; não usa as coordenadas das caixas como alvo. Isso foi conferido no manifesto e na função de carregamento da CNN.

**A frase sobre treinar mais estava errada?**

Não. Na gravação, você disse que treinar mais não garantiu resultado melhor em novas imagens, depois de comparar validação e teste. A revisão acrescenta “neste experimento” e especifica detecção. Mais épocas pode ajudar em outros cenários; aqui, a mAP de teste foi maior com 30 épocas.

**Qual trecho merece uma fala mais clara?**

Na gravação, a frase sobre ausência de detecção ficou ambígua na transcrição automática. Isso não comprova erro conceitual, mas vale dizer com clareza: “Se o modelo não detectou o objeto, contei como erro.” O código trata ausência de detecção como erro na comparação por imagem.

**Como leio os nomes dos modelos?**

Use “YOLO vê três” para YOLOv3 e “YOLO vê cinco” para YOLOv5. “Version three” e “version five” também são compreensíveis, mas não é preciso usar inglês. Escolha um padrão e mantenha. CNN: “sê-ene-ene”. CPU: “sê-pê-u”. mAP: “ême-á-pê”.

**Preciso falar meu RM?**

O enunciado exige nome completo e RM no nome do notebook, mas não determina que sejam narrados. O roteiro mantém os dois na abertura para identificar a apresentação. Seu RM é 573622: cinco, sete, três, seis, dois, dois.

**O que foi ajustado depois do ensaio?**

A fala foi dividida em frases e parágrafos menores, com transições mais naturais. Diga “inferência”, “os modelos nas mesmas oito imagens” e “o modelo reconheceu a classe”. Os tempos de inferência foram medidos em CPU; os treinos YOLOv5 ocorreram em GPU T4. A separação dos grupos reduz o risco de vazamento; revisar caixas, sozinho, não garante essa separação.

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
