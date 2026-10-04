# Estado da validação — 04/10/2026

## Verificado localmente

- Notebook com 32 células, incluindo 15 células de código Python.
- Estrutura JSON básica, identificadores únicos e sintaxe Python de todas as células. A versão final preserva os códigos, contadores e saídas reais da exportação executada, com reincorporação de dois PNGs originais documentada abaixo.
- Auditor de dataset exercitado com imagens artificiais criadas **somente como fixtures de teste de código**, fora da pasta do projeto.
- Aceitação de uma fixture estrutural com 32/4/4 imagens por classe.
- Rejeição de seis falhas introduzidas deliberadamente: imagem duplicada, grupo de captura atravessando conjuntos, caixa fora da imagem, divergência entre classe e procedência, rótulo vazio e contagem insuficiente.

Esses testes não treinam modelos, não medem acurácia e não fornecem imagens utilizáveis na atividade.

## Coleta verificada

- 80 fotografias reais selecionadas visualmente: 40 de garrafas e 40 de bananas, divisão 32/4/4 por classe.
- 14 fotografias do autor e 66 do Wikimedia Commons; origem e licença/autorização registradas por arquivo.
- 80 hashes de arquivo e 80 hashes de pixels decodificados distintos; todas as imagens legíveis, RGB e sem EXIF/GPS nas versões do dataset.
- Nenhum grupo registrado atravessa os splits. Fotografias do autor mantidas no treino; autores do Commons agrupados de forma conservadora. Essa regra não comprova independência absoluta de cena/origem.
- Três fotos extras do autor com as duas classes, fora do conjunto principal; não são teste independente por pertencerem à sessão usada no treino.
- 80 imagens com 173 caixas no Make Sense AI, usando sugestões YOLOv5m/COCO revisadas e caixas manuais. Auditoria final da interface: nenhuma imagem sem caixa e nenhuma caixa com classe indefinida.
- Exportação YOLO recebida: ZIP original preservado e 80 TXT importados nos splits; 173 caixas (115 garrafa, 58 banana/penca/cacho).
- Classes, cinco campos finitos, dimensões positivas, limites dentro da imagem, contagens do editor e correspondência dos nomes verificados. Nenhum TXT vazio ou órfão.
- Auditor do próprio notebook executado com os dados reais: divisão 32/4/4 por classe, sem duplicatas exatas nem grupos registrados entre splits. Manifesto em `auditoria-dataset/manifesto_auditado.csv`.
- Cinco folhas de revisão do ZIP inspecionadas, cobrindo as 80 imagens. Uma caixa de `garrafa_011` foi ajustada após inspeção ampliada para retirar uma colher ao fundo; revisão final renderizada e inspecionada. Registro em `AJUSTES-ROTULOS.json`.
- 80 capturas do editor em `evidencias/makesense/` e folhas da exportação em `evidencias/rotulos-exportados/`. Casos densos e parcialmente ocultos mantêm incerteza de delimitação; a revisão não demonstra desempenho do modelo.
- Validação final: `VERIFICACAO-ROTULOS.json`.
- Registro das verificações: `VERIFICACAO-COLETA.json`.

Os originais foram preservados. Fotos públicas podem ter integrado o pré-treino de modelos externos; essa sobreposição não foi auditada. A auditoria estrutural e a revisão visual das anotações não validam o desempenho dos modelos.

## Execução real no Colab

- Execução `20261004T164740010266Z`, em 04/10/2026; dataset auditado novamente no Colab antes do treino.
- YOLOv5s: dois treinos independentes completos, 30 e 60 épocas, mesmos pesos iniciais, seed 42, imagens 640 e batch 8, em GPU Tesla T4.
- Modelo de 60 épocas selecionado pela validação antes do teste; a seleção foi mantida apesar da maior mAP de teste do treino de 30 épocas.
- CNN do zero: 23.714 parâmetros, treino em CPU encerrado em 7 épocas por parada antecipada; checkpoint da época 1 restaurado pela menor perda de validação.
- YOLOv3 original carregado e avaliado com OpenCV DNN. Download oficial corrigido após HTTP 403; fontes e hashes registrados.
- Quatro soluções avaliadas nas mesmas oito imagens de teste; ausências de detecção mantidas como erros. Benchmark de inferência em CPU com mediana e P95.
- As 15 células de código possuem contadores de execução e não contêm saídas de erro na exportação final. A sessão teve retomadas para autorização do Drive e correção do download; não foi uma segunda execução integral em sessão limpa.
- 96 artefatos recuperados do Drive, totalizando 84.013.913 bytes, incluindo gráficos, CSVs, oito imagens de teste e pesos. Inventário e hashes em `VERIFICACAO-EXECUCAO.json`.
- Curvas de treino, matriz de confusão e painel completo de teste inspecionados. A discussão explica as métricas, sobreajuste da CNN, falhas, latência e limitações de anotação/base.
- Notebook original executado preservado em `evidencias/colab/notebook-executado-original.ipynb`. Na versão revisada, somente o markdown e os dois gráficos ausentes das células 24/26 foram atualizados; esses gráficos são os PNGs originais da execução, sem alteração. Códigos, contadores e demais saídas preservados.
- Versão revisada enviada como nova versão do mesmo arquivo do Drive, mantendo o ID e as permissões existentes. Notebook final também salvo na raiz do projeto.

## Pendências para a entrega

1. Fazer uma segunda reprodução integral em sessão limpa e verificar acesso ao dataset em outra conta.
2. A publicação disponibiliza repositório, dados e pesos com créditos e um link público do Colab baseado no GitHub. A cópia de desenvolvimento no Drive mantém as permissões do autor.
3. Gravar vídeo não listado de até 5 minutos, incluir seu link no README e testar os acessos do avaliador.
4. Conferir horário-limite no portal, enviar antes de 13/10/2026 e não fazer commits após o envio final.

A validação local da estrutura usa JSON e AST; não substitui o validador oficial nbformat. Os modelos foram executados efetivamente no Colab, conforme as saídas preservadas. Execução técnica concluída não equivale à entrega acadêmica completa.
