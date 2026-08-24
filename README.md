# 🚀 Bidding Opportunities Monitor (Pipeline n8n)

![Status](https://img.shields.io/badge/Status-Em%20andamento-orange)
![Plataforma](https://img.shields.io/badge/Plataforma-n8n-blue)
![Linguagem](https://img.shields.io/badge/Linguagem-JavaScript-yellow)

## 📌 Sobre o Projeto
Este projeto é um fluxo automatizado construído em **n8n** para monitorar, extrair e classificar oportunidades de licitações públicas e privadas no setor de gás e energia. O objetivo principal é eliminar o tempo gasto com buscas manuais diárias em múltiplos portais, entregando apenas os editais que possuem real aderência técnica e viabilidade de negócio.

A automação varre portais de compras de diversas companhias (como SCGAS, CEGAS, GASMIG, BAHIAGAS, MSGAS, CIGAS, etc.)[cite: 2], cruzando os editais com palavras-chave específicas de engenharia e automação.

## 🛠️ Tecnologias e Ferramentas Utilizadas
* **n8n (Workflow Automation):** Orquestração de todo o fluxo de extração e tratamento de dados[cite: 2].
* **JavaScript:** Lógica de filtragem, normalização de strings e estruturação de dados em nós de código (Code Nodes)[cite: 2].
* **REST APIs & HTTP Requests:** Consultas automatizadas no Portal Nacional de Contratações Públicas (PNCP) e Petronect, utilizando tokens de autenticação (Bearer)[cite: 2].
* **Web Scraping:** Extração de tabelas HTML diretamente de portais próprios de licitação[cite: 2].
* **Manipulação de Dados:** Conversão de arrays JSON brutos para planilhas formatadas (.xlsx)[cite: 2].

## ⚙️ Arquitetura e Funcionalidades do Fluxo

1. **Roteamento Dinâmico (Switch/Split In Batches):** O fluxo organiza as requisições iterando sobre uma lista de empresas e modalidades (Pregão, Concorrência, Dispensa, etc.), direcionando a consulta para a fonte correta (PNCP, Petronect ou Portal Próprio)[cite: 2].
2. **Filtro de Palavras-Chave (Engenharia/Industrial):** Utiliza scripts em JavaScript para buscar termos técnicos nos objetos dos editais, como: *válvulas, medição de vazão, city gates, skid, transmissores de pressão e cromatógrafos*[cite: 2].
3. **Otimizador e Agregador de Resultados:** O sistema avalia as oportunidades atribuindo um *score* de relevância (filtrando apenas scores > 4) e remove duplicatas com base no número da licitação[cite: 2].
4. **Filtro de Prazo:** Verifica automaticamente se a data de encerramento (`Data_Encerramento`) da licitação está dentro de uma janela de tempo viável para participação[cite: 2].
5. **Geração de Relatório:** Ao final do processo, todos os dados validados são exportados e consolidados automaticamente em um arquivo Excel (.xlsx) para a tomada de decisão[cite: 2].


   
