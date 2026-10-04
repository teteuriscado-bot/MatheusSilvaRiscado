# Dataset — imagens e rótulos validados em 04/10/2026

As pastas `images/train`, `images/val` e `images/test` já contêm 64, 8 e 8 fotografias, respectivamente: 40 garrafas e 40 bananas, com divisão 32/4/4 por classe. As pastas correspondentes de `labels` contêm 64, 8 e 8 arquivos TXT do Make Sense AI: 173 caixas, sendo 115 de garrafas e 58 de bananas/pencas/cachos.

Foram usados 14 arquivos do autor e 66 do Wikimedia Commons. As três fotos do autor com ambas as classes ficam fora deste conjunto, em `coleta/garrafas/extras_duas_classes/`. A numeração das garrafas tem intervalos por esse motivo; não renumerar para fechar os intervalos.

As 80 imagens são legíveis, RGB, sem EXIF/GPS e sem duplicatas exatas de arquivo ou pixels decodificados. Os grupos registrados não atravessam splits; isso não comprova independência absoluta das fontes públicas. Todos os arquivos da mesma sessão doméstica ficam no treino.

A convenção está em `PROTOCOLO-ROTULACAO.md`: cada garrafa e cada banana solta ou penca/cacho unido recebem uma caixa. `classes.txt` e `data.yaml` registram `garrafa=0`, `banana=1`. Manter `fontes.csv` e a pasta `creditos` na distribuição. O auditor do notebook foi executado com este dataset e aprovado. Os treinos e resultados posteriores estão preservados no notebook e na pasta de resultados do projeto.

O ZIP original do Make Sense foi preservado em `evidencias/exportacoes` no projeto. Após inspeção ampliada, apenas a primeira caixa de `garrafa_011` foi ajustada para retirar a colher atrás da garrafa; o registro está em `docs/AJUSTES-ROTULOS.json`. Não substituir os rótulos revisados por uma nova extração do ZIP original.

Em `fontes.csv`, usar uma linha por imagem. `arquivo` deve ser apenas o nome do arquivo, incluindo extensão. `split` deve ser `train`, `val` ou `test`; `classe` deve ser `garrafa` ou `banana` na configuração inicial. `grupo` identifica a cena/sessão/origem e não pode aparecer em splits diferentes. Se duas fotos foram capturadas na mesma sequência, usar o mesmo grupo.

Exemplo apenas de preenchimento, não um registro real:

```csv
arquivo,split,classe,grupo,origem,licenca_ou_autorizacao
garrafa_001.jpg,train,garrafa,sessao_01,fotografia propria,autorizada pelo autor
```

Não renomear imagens depois da rotulação sem renomear os `.txt` correspondentes. Não inserir valores fictícios de origem ou anotações vazias para fazer a checagem passar.
