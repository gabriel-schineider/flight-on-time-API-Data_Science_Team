## ✈️ Modelo de previsão de atraso de voos para API — Hackathon

### > Projeto PontUau desenvolvido pelo Time de Ciência de Dados da Equipe Araras Selvagens

Este projeto, divido em quatro repositórios - Ciência de Dados, Back-End, Front-End, Final-, tem como objetivo desenvolver um modelo capaz de prever se um voo **nacional** será **Pontual** ou **Atrasado**, bem como a probabilidade de tal ocorrência. Iniciativa, esta, realizada utilizando técnicas de Ciência de Dados, Machine Learning, com posterior integração a uma API REST desenvolvida em Java (Spring Boot) e contenerizada com Docker para padronização do ambiente de produção.



## Objetivo deste repositório de Data Science

Esse repositório teve como objetivo criar um dataset próprio, a partir de uma base de dados nacional e oficial, para, então, utilizá-lo na criação de um modelo de **classificação binária** que, a partir das informações básicas de um voo, retorne tanto a previsão de atraso (`Pontual` ou `Atrasado`) quanto a probabilidade associada à tal previsão.

Vale ressaltar que esse projeto foi desenvolvido no contexto de um hackathon educacional - organizado pela Oracle em parceria com a Alura e a NoCountry - com foco em aplicar os conhecimentos e habilidades deselvolvidos ao longo do Programa Oracle Next Education em um cenário real.


## Descrição do repositório - A abordagem do Time de Data Science

O trabalho de Data Science contemplou:

- Pesquisa de uma base de dados relevante e com qualidade ;

> Para esse projeto, fizemos uma extensa pesquisa internacional nas mais variadas bases de voos aéreos.
> Decidimos utilizar a base de dados da Agência Nacional de Aviação Civil (ANAC), pois, assim, pôde-se garantir maior integridade das informações. Além disso, esse conjunto de dados foi excepcional, uma vez que nossa aplicação é exclusivamente voltada para o mercado nacional e a ANAC é um Orgão Oficial do Brasil.  

- Extração desses dados para o ambiente de desenvolvimento da equipe ;
- Exploração, limpeza e manipulação dos dados ;
- Criação de variáveis temporais e operacionais relevantes para o modelo ;

> Aqui, nessa altura, conseguimos criar o dataset próprio da Equipe Araras Selvagens para utilizá-lo no modelo preditivo do Projeto PontUau
  
- Tratamento de variáveis categóricas com **Target Encoding** e **One Hot Encoder** ;
- Treinamento de diferentes modelos de classificação binária:
  - Logistic Regression (baseline)
  - Random Forest
  - XGBoost
- Avaliação desses modelos treinados com métricas adequadas para dados desbalanceados:
  - ROC-AUC
  - Recall
  - Precision
  - Log Loss
- Serialização do modelo final escolhido com `joblib`
- Suporte ao time de Back-End para integração do modelo com a API

---

## 📊 Modelo final

- Modelo: XGBoost
- Tipo: Classificação Binária
- Target: `voo_com_atraso` ( 1 : 'Atrasado' , 0 : 'Pontual' )
- Threshold padrão: 0.45 (ajustável conforme estratégia operacional)
- Serialização: `joblib`

Arquivo gerado: modelo_preditivo.pkl 

---

## 👥 Contribuidores

| Nome | Função | GitHub | LinkedIn |
|------|--------|--------|----------|
| **Gabriel Schineider** | Data Scientist | [gabriel-schineider](https://github.com/gabriel-schineider/) | [gabriel-schineider](https://www.linkedin.com/in/gabriel-schineider/) |
| **Gleice Araújo** | Data Scientist | [GleiceAraujo22](https://github.com/GleiceAraujo22) | [gleicearaujo](https://www.linkedin.com/in/gleicearaujo/) |
| **Wellington Gabriel** | Data Scientist | [WellingtonGabriel20](https://github.com/WellingtonGabriel20) | [wellingtongabriel20](https://www.linkedin.com/in/wellingtongabriel20) |
| **Cristiano Silveira** | Data Scientist | [realcsilveira](https://github.com/realcsilveira) | [realcsilveira](https://www.linkedin.com/in/realcsilveira) |
| **Arley Ribeiro** | Data Scientist | [ribeiroarley](https://github.com/ribeiroarley) | [ribeiroarley](https://www.linkedin.com/in/ribeiroarley) |

---

## Outros repositórios utilizados no projeto

[Back-End do Projeto](https://github.com/Bruno-BandeiraH/flight-on-time-api)

[Integração API](https://github.com/Bruno-BandeiraH/flight-prediction-model/)

[Front-End do Projeto](https://github.com/WellingtonGabriel20/Projeto-3-FlightOnTime-Previs-o-de-Atrasos-de-Voos)

[Repositório Final do Projeto](https://github.com/Bruno-BandeiraH/PontUau/tree/main)
