# ⚡ Otimização de Join com PySpark

Este projeto tem como objetivo explorar o potencial do PySpark para processar grandes volumes de dados de forma eficiente, por meio da leitura, transformação e junção de arquivos Parquet. O foco está na **otimização de desempenho**, utilizando técnicas como `repartition`, `coalesce` e análise com `EXPLAIN`.

## 📂 Dados Utilizados
- `videos-preparados.snappy.parquet`
- `video-comments-tratados.snappy.parquet`

## 🧪 Etapas Realizadas

1. **Leitura dos dados**  
   - Carregamento dos dois arquivos Parquet em DataFrames: `df_video` e `df_comments`.

2. **Criação de tabelas temporárias**  
   - Registro dos DataFrames como views temporárias no Spark SQL para facilitar consultas.

3. **Join inicial com Spark SQL**  
   - Realização do `JOIN` entre vídeos e comentários por meio de comandos SQL.

4. **Aplicação de particionamento**  
   - Repetição das etapas anteriores utilizando `repartition` e `coalesce` para testar diferentes estratégias de particionamento.

5. **Análise de plano de execução**  
   - Utilização de `EXPLAIN` para compreender o plano de execução dos joins e identificar gargalos de performance.

6. **Otimização do join final**  
   - Aplicação de filtros antes do join para trabalhar apenas com os dados necessários.
   - Uso combinado de particionamento adequado e seleção de colunas relevantes.

7. **Exportação do resultado**  
   - Salvamento do resultado final otimizado como `join-videos-comments-otimizado` no formato Parquet.

## 💡 Tecnologias
- PySpark (Spark SQL e DataFrame API)
- Python (executado no Google Colab ou ambiente local com PySpark configurado)
- Arquivos `.parquet` com compressão Snappy

