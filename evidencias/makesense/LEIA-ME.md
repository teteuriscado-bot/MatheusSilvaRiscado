# Evidências de rotulação — 03/10/2026

As 80 capturas mostram as caixas no Make Sense AI, uma por imagem do dataset. Os nomes correspondem aos arquivos originais, mas estas cópias são **capturas de tela**, não imagens de treinamento. Não colocá-las em `dataset/images`.

`auditoria-interface.json` registra 173 caixas em 80 imagens, sem classe indefinida ou imagem sem caixa ao final da revisão. O registro vem dos rótulos visíveis na interface e não contém coordenadas YOLO.

Foi usada assistência YOLOv5m/COCO no navegador, seguida de inspeção, correção de limites, rejeição de classes alheias e complementação manual. Isso não é o treinamento customizado da atividade.

O download automático inicial não retornou arquivo. Em 04/10/2026, o autor salvou e forneceu o ZIP, agora preservado em `evidencias/exportacoes`. Os 80 TXT foram validados e distribuídos nos splits, com `garrafa=0`, `banana=1`. Um ajuste manual posterior na primeira caixa de `garrafa_011` está registrado em `docs/AJUSTES-ROTULOS.json`; as capturas desta pasta mostram o estado original do editor.

As caixas de banana seguem uma unidade por banana solta ou penca/cacho fisicamente unido. Ver `docs/PROTOCOLO-ROTULACAO.md`. Cenas densas e objetos parcialmente ocultos merecem revisão adicional após a exportação. As capturas não substituem o ZIP nem comprovam desempenho dos modelos.
