# Fase 6 — plano de entrega

**Matheus Silva Riscado · RM573622 · individual**  
**Prazo informado: 13/10/2026. Meta de conclusão: 12/10/2026.**

As 80 imagens reais e seus 80 rótulos (173 caixas) estão organizados e validados. Os modelos foram executados em 04/10/2026; resultados, pesos e discussão estão preservados no notebook e em `resultados/20261004T164740010266Z/`. A publicação inicial está em `teteuriscado-bot/MatheusSilvaRiscado`. Ainda faltam a segunda reprodução integral em sessão limpa, o vídeo e o envio no portal. A entrega acadêmica ainda não está completa.

## O que vamos construir

Uma demonstração da FarmTech Solutions que localiza dois tipos de objeto em imagens e compara três abordagens: YOLOv5 customizado, YOLOv3 pré-treinado e uma CNN de classificação treinada do zero.

Classes escolhidas: **garrafa (classe 0) e banana (classe 1)**. São objetos visualmente distintos e têm classes correspondentes no YOLOv3 padrão: `bottle` e `banana`.

O capítulo 03 da Fase 6 ensina o YOLOv5 customizado. O capítulo 10, no exemplo prático das páginas 37–38, usa YOLOv3/Darknet. A CNN se apoia no capítulo 09. A referência do enunciado a “capítulo 3 de Redes Neurais” deve ser entendida no contexto das disciplinas, não apenas pela numeração dos PDFs.

## Imagens coletadas

| Classe | Treino | Validação | Teste | Total |
|---|---:|---:|---:|---:|
| Garrafa | 32 | 4 | 4 | 40 |
| Banana | 32 | 4 | 4 | 40 |
| **Total** | **64** | **8** | **8** | **80** |

O ZIP do autor trouxe 17 fotos: 14 compõem o treino e três, com banana e garrafas juntas, ficam em `coleta/garrafas/extras_duas_classes/`. As 26 garrafas complementares e as 40 bananas vieram do Wikimedia Commons, com créditos registrados. As três fotos extras compartilham a sessão do treino e não são um teste independente.

As folhas `CONTATO-01.jpg` e `CONTATO-02.jpg`, em cada pasta de `coleta`, mostram a seleção. A rotulação seguiu o [protocolo](docs/PROTOCOLO-ROTULACAO.md); o dataset já foi copiado para o Drive e usado no Colab. A lista abaixo registra os critérios usados na coleta e orienta novos experimentos, sem alterar retroativamente os conjuntos da execução concluída.

1. Fotografar objetos reais, em imagens diferentes; não contar cópias, recortes ou aumentos artificiais como novas fotos.
2. Variar iluminação, distância, orientação, tamanho aparente e fundo. Fotografar ambas as classes em fundos variados para evitar que a rede aprenda apenas o cenário.
3. Para a comparação com a CNN, cada imagem deve conter **uma única classe de interesse**. Pode haver vários objetos dessa mesma classe; anotar todos. Evitar garrafa e banana juntas nesta versão.
4. Separar por cena/sessão/origem antes de treinar. Fotos quase idênticas da mesma sequência não podem ir para conjuntos diferentes. Se possível, reservar exemplares físicos distintos para validação e teste.
5. Registrar origem, licença ou autorização e grupo de captura no arquivo `dataset/fontes.csv`. Fotografias próprias simplificam a procedência. Não publicar rostos ou informações pessoais desnecessárias.
6. Revisar a separação visualmente. A checagem automática encontra duplicatas exatas, mas não garante a ausência de imagens quase iguais.

Uma forma prática de obter 40 imagens por classe é fazer 10 grupos de 4 fotos: 8 grupos para treino, 1 para validação e 1 para teste. Isso atende à contagem, mas a diversidade de apenas um grupo em validação e teste é limitada; mais grupos independentes são preferíveis. O campo `grupo` identifica a origem real da cena, não um identificador inventado para cada foto.

## Rotulação no Make Sense AI

Para facilitar, `coleta/IMAGENS-PARA-ROTULAR.zip` reúne as 80 fotos em uma pasta, a ordem das classes, os créditos e o manifesto com a divisão. Extrair o ZIP antes de selecionar as imagens no site. Esse pacote ainda não contém anotações e não substitui o dataset final de treinamento.

1. Abrir [Make Sense AI](https://www.makesense.ai/), carregar as fotos e selecionar detecção de objetos.
2. Criar as classes nesta ordem: `garrafa`, depois `banana`.
3. Desenhar uma caixa justa em cada objeto de interesse, incluindo os objetos parcialmente visíveis quando identificáveis.
4. Exportar as anotações em formato YOLO. Guardar o ZIP original da exportação como evidência.
5. Repetir também para validação e teste, mantendo os mesmos IDs de classe. Esses rótulos são necessários para avaliar as caixas previstas.
6. Cada imagem deve ter um `.txt` de mesmo nome-base. Exemplo: `garrafa_001.jpg` e `garrafa_001.txt`.

O formato é `classe x_centro y_centro largura altura`, com coordenadas normalizadas entre 0 e 1. Não usar coordenadas em pixels. O arquivo de nomes de classes eventualmente exportado pela ferramenta não é uma anotação de imagem.

## Organização no Google Drive

Copiar a pasta `dataset` preenchida para `Meu Drive/FarmTechFase6/dataset/`:

```text
FarmTechFase6/
  dataset/
    fontes.csv
    images/
      train/     # 64 imagens
      val/       # 8 imagens
      test/      # 8 imagens
    labels/
      train/     # 64 arquivos TXT
      val/       # 8 arquivos TXT
      test/      # 8 arquivos TXT
```

O Colab copiará os dados para o disco temporário da sessão, para acelerar a leitura, e salvará os resultados no Drive. O professor deve conseguir obter os dados por um link de download autorizado, sem depender de acesso ao seu Drive pessoal. Preparar um ZIP público somente com os dados permitidos e configurar `DATASET_ZIP_URL` no notebook; manter também a organização no seu Drive exigida pelo enunciado.

## Notebook

Arquivo: `MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb`.

Abrir [o notebook executado no Colab](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb). A versão local também contém os resultados e a análise revisada. Para reproduzir, preparar os dados no próprio Drive, selecionar GPU quando disponível e executar as células em ordem. A sessão de 04/10 confirmou o funcionamento com Python 3.13.15, PyTorch 2.11.0+cu130 e TensorFlow 2.20.0; houve retomadas para autorização do Drive e correção do download dos pesos. Uma segunda execução integral em sessão limpa está pendente.

O experimento usa 30 e 60 épocas, iniciando ambos os treinos dos mesmos pesos pré-treinados. A seleção ocorre pela validação. Os testes ficam reservados para a avaliação final. A CNN começa com pesos aleatórios; não é uma rede pré-treinada disfarçada de CNN “do zero”.

Para detectar objetos, usamos precision, recall, mAP@0.5 e mAP@0.5:0.95. Para comparar também com a CNN, usamos acurácia e F1 de classificação por imagem. **mAP, confiança de uma detecção e acurácia são conceitos diferentes.**

A versão portátil `DATASET-FARMTECH-FASE6.zip` contém os arquivos de `dataset` na raiz. Para usar no Drive, extrair seu conteúdo dentro de `FarmTechFase6/dataset`, sem criar uma pasta `dataset/dataset`. Créditos, manifesto e protocolo acompanham o pacote.

## Como atender ao barema

| Critério | Peso | Evidência necessária |
|---|---:|---|
| GitHub | 1,5 | Repositório público, nome apropriado, notebook nomeado corretamente e entrega no prazo |
| Notebook | 3,0 | Código executado, saídas salvas, comparação das épocas, três abordagens e conclusões próprias baseadas nos números |
| README | 2,0 | Introdução curta, identificação, link do Colab e link do vídeo |
| Vídeo | 2,0 | Funcionamento demonstrado em até 5 minutos, YouTube não listado |
| Organização | 1,5 | Arquivos claros, resultados localizáveis, imagens de teste e documentação coerente |

O [checklist por critério](docs/CHECKLIST-BAREMA.md) registra o estado e as evidências ainda necessárias. As **Entregas 1 e 2 são obrigatórias**, conforme o barema. Os desafios “Ir Além” não aumentam a nota acadêmica. Só trabalhar neles depois de concluir os itens acima.

## Cronograma sugerido

As etapas de coleta, rotulação, treino e análise foram antecipadas e concluídas em 03–04/10. As datas abaixo são a referência inicial; publicação, vídeo e conferência da entrega ainda precisam ser concluídos.

| Data | Resultado esperado |
|---|---|
| 03–04/10 | Confirmar objetos, coletar as imagens e registrar as fontes |
| 05–06/10 | Rotular, separar os conjuntos, revisar caixas e conferir contagens |
| 07–08/10 | Executar YOLOv5 com 30 e 60 épocas, YOLOv3 e CNN |
| 09/10 | Conferir métricas, investigar erros e escrever a análise |
| 10/10 | Revisar README, notebook, dados e links do repositório |
| 11/10 | Gravar e publicar o vídeo não listado |
| 12/10 | Reexecutar em sessão limpa, testar links e concluir a entrega |
| 13/10 | Prazo informado; conferir o horário exato no portal |

Depois do envio final, não realizar novos commits, conforme a orientação do enunciado. Não há monitoramento ou lembrete automático configurado por este cronograma.

## Checklist final

- [x] 40 imagens reais de cada classe, divisão 32/4/4 por classe.
- [x] Origem das imagens documentada; nenhum grupo registrado atravessa os conjuntos.
- [x] Caixas revisadas no Make Sense AI, incluindo validação e teste; capturas preservadas.
- [x] ZIP YOLO recuperado, coordenadas validadas e 80 TXT distribuídos nos splits.
- [x] Dataset e rótulos organizados no Google Drive.
- [x] Dois treinos completos, com parâmetros e tempos registrados.
- [x] YOLO padrão e CNN do zero executados sobre a mesma divisão de dados.
- [x] Métricas de validação e teste, curvas de erro e imagens com as detecções.
- [x] Comparação de facilidade de integração, qualidade, treino e inferência.
- [x] Conclusões revisadas com resultados e limitações reais.
- [x] Notebook com todas as células executadas e saídas preservadas.
- [ ] Segunda reprodução do início ao fim em sessão limpa, sem intervenções.
- [ ] Dados acessíveis ao avaliador e instruções de reprodução testadas.
- [ ] README sem links pendentes.
- [ ] Vídeo não listado de até 5 minutos, demonstrando uma execução real.
- [x] Repositório público com notebook, dados e resultados.
- [ ] Link enviado no portal antes do prazo.
- [ ] Nenhum commit posterior ao envio final.

## Referências técnicas

- [YOLOv5: treinamento customizado](https://docs.ultralytics.com/yolov5/tutorials/train-custom-data).
- [YOLOv3: projeto original](https://pjreddie.com/darknet/yolo/).
- [Make Sense: formatos de exportação](https://github.com/SkalskiP/make-sense).
- [TensorFlow: classificação de imagens](https://www.tensorflow.org/tutorials/images/classification).

Materiais FIAP consultados: PDFs dos capítulos 03, 09 e 10 disponíveis localmente na pasta `Graduação/Fase 6`. Não incluir esses PDFs de acesso individual no repositório público.
