# Verificação em sessão limpa — 06/10/2026

Execução `20261006T122041599048Z`, concluída em uma nova sessão T4. As 15 células científicas terminaram em ordem, sem erros nem correções intermediárias. Os únicos ajustes prévios foram `USE_DRIVE=False` e o link público do ZIP.

- [Notebook revisado com saídas desta rodada](VERIFICACAO_LIMPA_2026-10-06_MatheusSilvaRiscado_rm573622.ipynb)
- [Exportação original antes da revisão](notebook-original-executado.ipynb)
- [Registro de conferência e hashes](../../docs/VERIFICACAO-SESSAO-LIMPA.json)
- [ZIP completo dos resultados](https://github.com/teteuriscado-bot/MatheusSilvaRiscado/releases/download/fase6-2026-10-04/RESULTADOS-FARMTECH-20261006T122041599048Z.zip)

## Achados

As 15 células foram executadas em uma sessão T4 nova, na ordem 1–15, sem erro e sem ajustes intermediários no código. O dataset foi obtido pelo link público do GitHub, com `USE_DRIVE=False`. Apenas as duas configurações documentadas de acesso aos dados diferem da execução de 04/10; splits, seed e hiperparâmetros permanecem iguais.

Os históricos contêm 30 e 60 épocas completas. Os tempos foram 191,27 s e 300,08 s. O checkpoint de 60 épocas voltou a ser selecionado pela validação: mAP@0,5:0,95 de 0,4244, contra 0,3618 em 30 épocas. No teste, os valores foram 0,5556 e 0,5944, respectivamente; a seleção pela validação foi mantida.

| Modelo | Acertos no teste | Sem detecção | Mediana CPU (ms) |
|---|---:|---:|---:|
| CNN_do_zero | 5/8 | 0 | 36.10 |
| YOLOv3_padrao | 7/8 | 1 | 994.67 |
| YOLOv5_30 | 6/8 | 2 | 161.77 |
| YOLOv5_60 | 5/8 | 3 | 170.54 |


A CNN novamente parou em 7 épocas e restaurou a época 1, com perda de validação mínima de 0,6945. As curvas mostram a perda de treino caindo e a de validação subindo, evidência de sobreajuste. A CNN e o YOLOv3 mantiveram os acertos da primeira execução; os dois YOLOv5 variaram em uma imagem de teste cada: 30 épocas passou de 5/8 para 6/8, e 60 épocas passou de 6/8 para 5/8. A ausência de detecção conta como erro; acurácia por imagem não substitui mAP de localização.

O painel mostra todas as oito imagens. O YOLOv5 selecionado não detectou a banana solta sobre tecido nem duas cenas de garrafas. Em outra cena, também incluiu uma caixa de papelão entre as detecções. Esses exemplos mostram por que acertar a classe predominante não garante contar ou localizar corretamente todos os objetos.

O código é reproduzível operacionalmente, mas os treinos YOLOv5 não produziram métricas idênticas entre as duas sessões, mesmo com seed fixa e a mesma GPU declarada. A causa exata dessa variação não foi isolada. Duas execuções e oito imagens de teste são insuficientes para caracterizar estabilidade ou desempenho de produção. As medições de tempo dependem da sessão; não representam uma mudança de arquitetura.

Esta rodada verifica a execução do projeto e não substitui a análise nem os pesos publicados da rodada original. O relatório principal continua vinculado à execução de 04/10/2026; este caderno conserva exclusivamente as saídas de `20261006T122041599048Z`.
