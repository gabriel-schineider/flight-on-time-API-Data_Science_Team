# ✈️ Previsão de Atraso de Voos — Hackathon

Este projeto tem como objetivo desenvolver um MVP capaz de prever se um voo nacional será **Pontual** ou **Atrasado**, utilizando técnicas de Ciência de Dados e Machine Learning, com posterior integração a uma API REST desenvolvida em Java (Spring Boot).

---

## 🎯 Objetivo do Projeto

Criar um modelo de **classificação binária** que, a partir de informações básicas de um voo, retorne:
- a previsão de atraso (`Pontual` ou `Atrasado`)
- a probabilidade associada à previsão

O projeto foi desenvolvido no contexto de um hackathon educacional, com foco em boas práticas de Data Science aplicadas a um cenário real.

---

## 🧠 Abordagem de Data Science

O trabalho de Data Science contempla:

- Exploração e limpeza dos dados (EDA)
- Criação de variáveis temporais e operacionais
- Avaliação de diferentes modelos de classificação:
  - Logistic Regression (baseline)
  - Random Forest
  - XGBoost
- Tratamento de variáveis categóricas com **Target Encoding**
- Avaliação com métricas adequadas a dados desbalanceados:
  - ROC-AUC
  - Recall
  - Precision
  - Log Loss
- Serialização do modelo final com `joblib`

O modelo escolhido para entrega foi o **XGBoost com Target Encoding**, por apresentar o melhor equilíbrio entre desempenho e robustez.

---

## 📊 Modelo Final

- **Modelo:** XGBoost
- **Tipo:** Classificação Binária
- **Target:** `voo_com_atraso` (0 = Pontual, 1 = Atrasado)
- **Threshold padrão:** 0.5 (ajustável conforme estratégia operacional)
- **Serialização:** `joblib`

Arquivo gerado:

models/modelo_atraso_voos_xgb_te_v1.pkl  


---

## 🔗 Contrato de Integração — Data Science ↔ Back-End

### 📥 Entrada da API (JSON)

```json
{
  "companhia": "AZ",
  "origem": "GIG",
  "destino": "GRU",
  "data_partida": "2025-11-10T14:30:00",
  "distancia_km": 350
}

### Transformação Esperada ((Back-End)

| Campo da API | Feature do Modelo                                        |
| ------------ | -------------------------------------------------------- |
| companhia    | icao_empresa_aerea                                       |
| origem       | icao_aerodromo_origem                                    |
| destino      | icao_aerodromo_destino                                   |
| data_partida | hora_prevista_frac, mes, eh_fim_de_semana, faixa_horaria |
| distancia_km | Não utilizada diretamente no modelo atual                |


---

## 📌 Features esperadas pelo modelo

O modelo serializado espera um DataFrame com as seguintes colunas:

icao_empresa_aerea
icao_aerodromo_origem
icao_aerodromo_destino
faixa_horaria
hora_prevista_frac
voos_no_slot
tempo_voo_estimado
mes
eh_fim_de_semana


## 📤 Saída da API (JSON)

{
  "previsao": "Atrasado",
  "probabilidade": 0.78
}


```

## 🚀 Próximos Passos (Trabalhos Futuros)

* Ajuste fino do threshold conforme estratégia operacional

* Calibração de probabilidades

* Incorporação de dados externos (ex.: clima, restrições operacionais, distância)

* Monitoramento de performance em produção


## 👥 Autores

Projeto desenvolvido no contexto de hackathon educacional desenvolvido pela Oracle com foco em Ciência de Dados aplicada.


