# 📊 Análise de Opções com Black-Scholes (SPY)

Este projeto identifica **oportunidades de compra em opções de compra (calls)** do ETF SPY com base no **modelo Black-Scholes** e dados reais extraídos do Yahoo Finance.

## 🧠 Objetivo

Encontrar opções que o mercado está precificando como **baratas**, usando um modelo matemático robusto e não apenas análise gráfica ou dados passados.

## 🔍 O que o script faz

1. Coleta dados de preço do ETF SPY dos últimos 60 dias;
2. Seleciona vencimentos de opções com ~30 dias de distância;
3. Filtra as **calls** com strikes próximos ao preço atual (±5%);
4. Calcula a **volatilidade histórica** do ativo (30 dias);
5. Usa o **modelo Black-Scholes** para estimar:
   - Preço justo da opção;
   - Delta;
6. Compara o preço justo com o preço de mercado para classificar as opções em:
   - Caras;
   - Justas;
   - Baratas;
7. Compara a **volatilidade implícita (IV)** com a **volatilidade histórica (HV)**:
   - IV > HV: mercado otimista;
   - IV < HV: mercado calmo;
   - IV ≈ HV: neutro.

## 📈 Exemplo de saída

O script imprime duas tabelas:
- Opções **caras** (acima de 10% do preço justo)
- Opções **baratas** (abaixo de 10% do preço justo)

Inclui também o volume e o open interest para avaliar liquidez.

## 🛠️ Requisitos

- Python 3.8+
- Bibliotecas:
  ```bash
  pip install yfinance numpy pandas scipy

