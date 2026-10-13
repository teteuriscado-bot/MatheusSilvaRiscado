# Fase 6 — guia de leitura e entrega

**Matheus Silva Riscado · RM573622 · individual**  
**Atualizado em 12/10/2026 · prazo confirmado no portal: 13/10/2026, às 23h59.**

As 80 imagens reais e seus 80 rótulos (173 caixas) estão organizados e validados. Os modelos foram executados em 04/10/2026; resultados, pesos e discussão estão preservados no notebook e em `resultados/20261004T164740010266Z/`. Reproduções integrais em sessão limpa foram concluídas em 06/10 e 12/10/2026; a última testou as correções de gráficos e dependências, com 15 células sem erro e cinco figuras embutidas automaticamente. O vídeo corrigido foi publicado como não listado e incluído no README. **Resta enviar pelo portal o [PDF de entrega com os links](docs/MatheusSilvaRiscado_rm573622_pbl_fase6.pdf).**

## Começar a avaliação

1. Ler o [notebook executado](MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb), que reúne método, código, saídas e conclusões.
2. Assistir ao [vídeo demonstrativo](https://youtu.be/zm5nAksnAlU), não listado, com aproximadamente 4min30s.
3. Para reproduzir, abrir uma cópia [no Colab](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb), selecionar GPU quando disponível e executar tudo. O dataset público já está configurado; não é necessário montar o Drive nem editar caminhos. Ver [reprodução e preservação dos resultados](docs/REPRODUCAO.md).
4. Consultar o [checklist do barema](docs/CHECKLIST-BAREMA.md) e a [evidência da sessão limpa](evidencias/reexecucao-20261006/README.md), caso queira conferir a execução independente.

## Solução entregue

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

As folhas locais `CONTATO-01.jpg` e `CONTATO-02.jpg`, em cada pasta de `coleta`, registram a seleção. As imagens e os rótulos finais estão publicados em `dataset/`. A rotulação seguiu o [protocolo](docs/PROTOCOLO-ROTULACAO.md); o dataset foi organizado no Drive e usado no Colab. A lista abaixo registra os critérios usados na coleta e orienta novos experimentos, sem alterar retroativamente os conjuntos da execução concluída.

1. Fotografar objetos reais, em imagens diferentes; não contar cópias, recortes ou aumentos artificiais como novas fotos.
2. Variar iluminação, distância, orientação, tamanho aparente e fundo. Fotografar ambas as classes em fundos variados para evitar que a rede aprenda apenas o cenário.
3. Para a comparação com a CNN, cada imagem deve conter **uma única classe de interesse**. Pode haver vários objetos dessa mesma classe; anotar todos. Evitar garrafa e banana juntas nesta versão.
4. Separar por cena/sessão/origem antes de treinar. Fotos quase idênticas da mesma sequência não podem ir para conjuntos diferentes. Se possível, reservar exemplares físicos distintos para validação e teste.
5. Registrar origem, licença ou autorização e grupo de captura no arquivo `dataset/fontes.csv`. Fotografias próprias simplificam a procedência. Não publicar rostos ou informações pessoais desnecessárias.
6. Revisar a separação visualmente. A checagem automática encontra duplicatas exatas, mas não garante a ausência de imagens quase iguais.

Uma forma prática de obter 40 imagens por classe é fazer 10 grupos de 4 fotos: 8 grupos para treino, 1 para validação e 1 para teste. Isso atende à contagem, mas a diversidade de apenas um grupo em validação e teste é limitada; mais grupos independentes são preferíveis. O campo `grupo` identifica a origem real da cena, não um identificador inventado para cada foto.

## Rotulação no Make Sense AI

Na preparação local, `coleta/IMAGENS-PARA-ROTULAR.zip` reuniu as 80 fotos, a ordem das classes, os créditos e o manifesto. A lista abaixo registra o procedimento seguido. Para reproduzir os experimentos, usar diretamente o [dataset final com anotações](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/DATASET-FARMTECH-FASE6.zip).

1. Abrir [Make Sense AI](https://www.makesense.ai/), carregar as fotos e selecionar detecção de objetos.
2. Criar as classes nesta ordem: `garrafa`, depois `banana`.
3. Desenhar uma caixa justa em cada objeto de interesse, incluindo os objetos parcialmente visíveis quando identificáveis.
4. Exportar as anotações em formato YOLO. Guardar o ZIP original da exportação como evidência.
5. Repetir também para validação e teste, mantendo os mesmos IDs de classe. Esses rótulos são necessários para avaliar as caixas previstas.
6. Cada imagem deve ter um `.txt` de mesmo nome-base. Exemplo: `garrafa_001.jpg` e `garrafa_001.txt`.

O formato é `classe x_centro y_centro largura altura`, com coordenadas normalizadas entre 0 e 1. Não usar coordenadas em pixels. O arquivo de nomes de classes eventualmente exportado pela ferramenta não é uma anotação de imagem.

## Organização original no Google Drive

A sessão original utilizou a pasta `Meu Drive/FarmTechFase6/dataset/` com esta estrutura:

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

A organização original no Drive foi preservada. A configuração pública atual baixa o ZIP para o disco temporário do Colab e salva ali os novos resultados, sem acessar o Drive do autor. A última célula oferece o ZIP para download. O [guia de reprodução](docs/REPRODUCAO.md) documenta também a alternativa com o próprio Drive.

## Notebook

Arquivo: `MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb`.

Abrir [o notebook executado no Colab](https://colab.research.google.com/github/teteuriscado-bot/MatheusSilvaRiscado/blob/main/MatheusSilvaRiscado_rm573622_pbl_fase6.ipynb). A versão publicada contém os resultados e a análise de 04/10. Para reproduzir, salvar uma cópia na própria conta, selecionar GPU quando disponível e executar tudo; o download público já está configurado. A sessão de 04/10 confirmou o funcionamento com Python 3.13.15, PyTorch 2.11.0+cu130 e TensorFlow 2.20.0; houve retomadas para autorização do Drive e correção do download dos pesos. A segunda execução integral em sessão limpa foi concluída em 06/10/2026, sem erro nas 15 células; consultar `evidencias/reexecucao-20261006/`.

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

## Etapas concluídas e envio

As datas abaixo registram a execução do projeto. O envio acadêmico permanece pendente.

| Data | Etapa |
|---|---|
| 03–04/10 | Coleta, rotulação, auditoria, treinos e preservação dos resultados |
| 06/10 | Segunda execução integral em sessão limpa, sem erros nas 15 células |
| 09–12/10 | Revisão e gravação da apresentação |
| 12/10 | Vídeo corrigido publicado, README atualizado e acesso público ao dataset configurado por padrão |
| Até 13/10, às 23h59 | Enviar o link do repositório pelo portal e preservar o comprovante — pendente |

Depois do envio final, não realizar novos commits, conforme a orientação do enunciado.

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
- [x] Segunda reprodução do início ao fim em sessão limpa em 06/10/2026: 15 células sem erro nem intervenções.
- [x] Dados baixados por URL pública e reprodução integral testada em 06/10/2026.
- [x] README com links para notebook, Colab, dados, resultados e vídeo.
- [x] Vídeo não listado de aproximadamente 4min30s, demonstrando os resultados reais.
- [x] Notebook com download público do dataset configurado por padrão.
- [x] Repositório público com notebook, dados e resultados.
- [ ] Link enviado no portal antes do prazo.
- [ ] Nenhum commit posterior ao envio final.

## Referências técnicas

- [YOLOv5: treinamento customizado](https://docs.ultralytics.com/yolov5/tutorials/train-custom-data).
- [YOLOv3: projeto original](https://pjreddie.com/darknet/yolo/).
- [Make Sense: formatos de exportação](https://github.com/SkalskiP/make-sense).
- [TensorFlow: classificação de imagens](https://www.tensorflow.org/tutorials/images/classification).

Materiais FIAP consultados: PDFs dos capítulos 03, 09 e 10 disponíveis localmente na pasta `Graduação/Fase 6`. Não incluir esses PDFs de acesso individual no repositório público.


## Verificação concluída em 06/10/2026

A segunda execução em sessão limpa terminou: 15 células em ordem, sem erro, com download público do dataset. As evidências estão em `evidencias/reexecucao-20261006/`. O notebook principal e o vídeo continuam vinculados à rodada original de 04/10; as métricas das duas rodadas estão documentadas separadamente. O vídeo está publicado e incluído no README; resta o envio pelo portal.
