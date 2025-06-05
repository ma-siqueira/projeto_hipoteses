# Projeto de Análise de Dados: Validação de Hipóteses em Popularidade de Músicas

## 📌 Informações Gerais  
- **Ferramentas:** Google Sheets, BigQuery, SQL, Power BI, Python  

## 🎯 Objetivo
Identificar padrões e características que influenciam a popularidade (número de *streams*) de músicas em plataformas como Spotify, Apple Music e Deezer, validando hipóteses estratégicas para a indústria musical.

---

## 📊 Metodologia

### 1. **Preparação dos Dados**
- **Fontes:**  
  - `track_in_competition` (posições em charts/playlists)  
  - `track_in_spotify` (dados de streams e lançamento)  
  - `track_technical_info` (características técnicas das músicas)  

- **Processos:**  
  - Tratamento de nulos, duplicatas e outliers com SQL (`COUNT`, `GROUP BY`, `SAFE_CAST`, `REGEXP_REPLACE`).  
  - Correção de dados discrepantes (ex: datas de lançamento incorretas).  
  - Criação de variáveis derivadas (ex: data completa `AAAA-MM-DD`, soma de playlists).  
  - União de tabelas com `LEFT JOIN`.  

### 2. **Análise Exploratória (EDA)**
- **Agrupamentos:**  
  - Quantidade de músicas por artista (ex: Taylor Swift lidera com 34 faixas).  
  - Distribuição de lançamentos por ano.  
- **Estatísticas:**  
  - Medidas de tendência central (média, mediana) e dispersão para *streams* e playlists.  
  - Quartis para categorização de popularidade (ex: top 25% com *streams* > 1 bilhão).  
- **Visualizações:**  
  - Histogramas (Python) mostrando distribuição assimétrica de *streams* (long tail).  
  - Correlações (Pearson) entre variáveis (ex: playlists vs. *streams*: `r=0.78`).  

### 3. **Validação de Hipóteses**
| Hipótese | Resultado | Correlação |  
|----------|-----------|------------|  
| BPM alto aumenta *streams* | ❌ Não válida | `r ≈ 0` |  
| Popularidade no Spotify ≈ Deezer | ✅ Parcial | `r=0.55` |  
| Mais playlists = Mais *streams* | ✅ Forte | `r=0.78` |  
| Artistas com mais músicas têm mais *streams* | ✅ Forte | `r=0.77` |  
| Características técnicas influenciam *streams* | ❌ Não válida | Sem padrão claro |  

---

## 📌 Principais Conclusões
- **Fatores críticos para sucesso:**  
  - Presença em múltiplas playlists (`+playlists → +streams`).  
  - Lançamento frequente de músicas (`+volume → +alcance`).  
  - Distribuição em várias plataformas (Spotify, Deezer, Apple Music).  
- **Baixo impacto:** Características técnicas (BPM, energia, dançabilidade).  

---

## 📂 Entregas

- **Dashboard interativo** (Power BI)  
- **Scripts de análise** (SQL/Python)  
- **Vídeo de apresentação dos resultados**:  
  [🎥 Assistir apresentação de 5 minutos](https://www.loom.com/share/03a2cebeb5824c3c9c5f81a79cc1510b?sid=b47453d4-f2e5-4a09-9851-3a62105f6e0e)  
  

