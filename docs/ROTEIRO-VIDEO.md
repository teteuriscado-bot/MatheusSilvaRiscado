# Roteiro do vídeo — duração-alvo de 4min40s

O notebook foi executado e revisado. Ler a discussão para entender as conclusões e usar os resultados reais nas falas. Não dizer que a solução está validada em produção.

| Tempo | Tela e conteúdo |
|---|---|
| 00:00–00:25 | Apresentação: Matheus Silva Riscado, RM573622; problema do cliente fictício da FarmTech e as duas classes escolhidas |
| 00:25–01:00 | Dataset no Drive, contagens 32/4/4 por classe e exemplo da caixa anotada no Make Sense AI |
| 01:00–01:45 | Colab: dois treinos independentes de 30 e 60 épocas; mostrar mAP de validação 0,3861 → 0,4267 e tempos 202,40 → 341,11 s. Explicar a seleção de 60 épocas antes do teste |
| 01:45–02:35 | Executar uma inferência com pesos já treinados; mostrar as imagens de teste e pelo menos um caso difícil ou erro, se houver |
| 02:35–03:35 | Mostrar os acertos no teste: YOLOv3 7/8, YOLOv5 60 épocas 6/8, YOLOv5 30 épocas e CNN 5/8. Medianas CPU: YOLOv3 1.015,95 ms, YOLOv5 60 épocas 179,70 ms e CNN 24,31 ms. Distinguir acurácia de mAP e localização de classificação |
| 03:35–04:15 | Explicar que 30 épocas teve maior mAP no teste, mas a seleção pela validação foi mantida. Mostrar o sobreajuste da CNN; oito imagens são insuficientes para afirmar desempenho em produção |
| 04:15–04:40 | Abrir o GitHub e mostrar os links do notebook, dados e evidências; encerrar |

Não é necessário filmar o treinamento inteiro. Mostrar os logs preservados e executar a inferência ao vivo comprova o funcionamento de maneira mais clara. Separar a configuração da demonstração para não perder tempo instalando bibliotecas na gravação.

Antes de publicar: conferir duração inferior a 5 minutos, áudio compreensível e texto legível. Publicar como **não listado**, abrir o link em uma janela sem login e inseri-lo no README. Conferir as regras do portal sobre o horário de entrega.
