# Protocolo de rotulação — garrafa e banana

Aplicar a mesma regra em treino, validação e teste. As fotos já estão separadas; não mudar a divisão em função dos resultados.

## Classes no Make Sense AI

Criar nesta ordem: **garrafa (0)** e **banana (1)**. A CNN classifica a imagem inteira; por isso o conjunto principal contém apenas uma dessas classes por imagem, mesmo quando há vários objetos dessa classe.

### Garrafa

Anotar cada recipiente reconhecível como garrafa: água, refrigerante, vinho, azeite, vinagre e garrafas reutilizáveis de plástico, vidro ou metal. Incluir tampa e alça integrada quando presentes. Garrafas deitadas, vazias, amassadas e parcialmente escondidas também contam quando identificáveis.

Não anotar potes de boca larga, copos, panelas, latas, baldes, caixas nem galões do tipo bombona. Nas fotos da cozinha, o pote de milho é fundo, não uma garrafa. Anotar também as garrafas identificáveis no fundo; não apenas o objeto maior em primeiro plano.

### Banana

Anotar independentemente de estar verde, amarelo ou com manchas. **Unidade de anotação definida antes do treino: uma banana solta ou uma penca/cacho fisicamente unido.** Bananas soltas recebem caixas individuais. Uma penca ou cacho unido recebe uma caixa nos limites dos frutos visíveis do conjunto; não adicionar caixas individuais sobre esses mesmos frutos. Pencas distintas e separadas recebem caixas separadas. Não agrupar objetos apenas por proximidade. Não anotar folhas, flores, tronco, galhos nus ou objetos com desenho de banana.

Cachos densos exigem inspeção ampliada. Não inventar a extensão de frutos inteiramente escondidos. A anotação representa a localização do fruto ou conjunto comercial unido, não a contagem de bananas individuais. Essa convenção deve aparecer no relatório e ser aplicada em todos os splits; o modelo COCO pode produzir caixas individuais ou agrupadas, o que também afeta a comparação de localização.

As sugestões iniciais de YOLOv5m/COCO no Make Sense AI são apenas pré-anotações. Conferir limites, completar objetos omitidos e rejeitar classes estranhas. Guardar a exportação do site e informar a assistência de IA; ela não equivale ao treinamento customizado solicitado na atividade.

## Desenho das caixas

1. Usar retângulos justos nos limites visíveis do objeto, sem margem larga.
2. Incluir todas as instâncias identificáveis. Partes fora da fotografia não entram na caixa.
3. Em objetos ocluídos, seguir os extremos visíveis da mesma instância, sem adivinhar seu contorno completo.
4. Ampliar a foto para verificar objetos pequenos, transparentes e cortados pela borda.
5. Exportar em **YOLO** e preservar o ZIP original da exportação como evidência do Make Sense AI.
6. Colocar cada TXT em `dataset/labels/<split>/`, com o mesmo nome-base da imagem em `dataset/images/<split>/`.

Cada linha é `classe x_centro y_centro largura altura`, com coordenadas entre 0 e 1. Os arquivos de nomes de classes exportados pela ferramenta não são rótulos de imagens. Em 04/10/2026 foram importados e validados 80 TXT, somando 173 caixas. O ZIP original está em `evidencias/exportacoes`; um ajuste manual posterior em `garrafa_011` está documentado em `docs/AJUSTES-ROTULOS.json`.

## Três fotos com as duas classes

Os arquivos originais terminados em `202909009_HDR`, `202924740_HDR` e `202929450_HDR` mostram banana e garrafas na mesma cena. Estão preservados na coleção e separados como extras. Podem ilustrar detecção simultânea, desde que as duas classes sejam anotadas.

Esses extras pertencem à mesma sessão de captura usada no treino. Portanto, uma demonstração com eles **não é um teste independente de generalização** e não deve ser misturada às métricas dos oito arquivos de teste reservados. A CNN atual de uma classe por imagem não se aplica a esses extras sem adaptação.
