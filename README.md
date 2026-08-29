# Baseline e Prova de Hardware — Experiência Criativa

Para validar a viabilidade técnica da metodologia proposta e certificar que o hardware disponível (GPU NVIDIA RTX 3060 de 12 GB) comporta o treinamento sem estouro de memória (OOM), executamos dois experimentos preliminares com uma quantidade reduzida de épocas, voltados estritamente à comprovação computacional:

1. **Modelo Point Cloud Mamba (PCM) no dataset S3DIS**
   - **Objetivo:** Prova de conceito da arquitetura Mamba / State Space Model (SSM) em um dataset de referência de larga escala estruturado em blocos espaciais. O teste valida que conseguimos treinar o modelo PCM em um dataset de tarefa e tamanho semelhante ao PSNet5.
   - [logs](https://github.com/trampo-tech/PCM_compute_test/blob/main/proofs/s3dis-train-PCM-ngpus1-20260827-020346-9RxWmqLJCHwaZ79QDizFwu.log)

2. **Modelo ResPointNet++ no dataset PSNet5**
   - **Objetivo:** O teste valida a integridade do pipeline de dados, o particionamento das cenas industriais (área-based) e a capacidade do ambiente em processar as 5 classes MEP do cenário industrial real antes da adaptação do modelo principal.
   - [logs](https://github.com/trampo-tech/respointnet_compute_proof/tree/main/log/psnet5/respointnet2_dp_fi_df_fc1_max_20260829184931)

Ambos os experimentos foram executados intencionalmente por poucas épocas apenas para aferição de consumo de memória, latência por iteração e estabilidade do fluxo de dados, assegurando a base necessária para as etapas completas de treino e ablações.
