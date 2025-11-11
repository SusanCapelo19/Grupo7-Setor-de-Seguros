# Grupo 7 – Setor de Seguros

### Projeto da Residência Tecnológica NTT Data – Porto Digital (2º semestre/2025)  
**Disciplina:** Residência Tecnológica 
**Instituição:** CESAR School

---

## 🎯 Objetivo Geral
Realizar uma análise exploratória e técnica sobre o **Setor de Seguros**, com ênfase em **seguros de vida**, utilizando ferramentas de **análise de dados no Databricks**.  
O objetivo é compreender padrões, tendências e desafios do setor, gerando insights que apoiem a modernização e digitalização do mercado de seguros no Brasil.

---

## 🧩 Contexto de Negócio
O setor de seguros passa por uma transformação digital acelerada, com novas insurtechs, personalização de produtos e foco em experiência do cliente.  
Nesta análise, buscamos responder perguntas como:
- Quais fatores influenciam a adesão a seguros de vida?
- Há padrões de idade, renda ou região na contratação?
- Quais produtos e serviços têm maior potencial de crescimento?

---

## ⚙️ Ferramentas Utilizadas
- **Databricks Community Edition**  
- **Linguagem:** Python (pyspark)  
- **Controle de versão:** GitHub  

---

## 📁 Estrutura do Projeto

| Pasta | Descrição |
|-------|------------|
| Pasta | Descrição |
|-------|------------|
| `/data/raw` | Dados originais recebidos da NTTData |
| `/data/processed/bronze` | Dados brutos importados e armazenados no formato interno do Databricks |
| `/data/processed/prata` | Dados tratados e limpos, prontos para análise |
| `/data/processed/ouro` | Dados finais e agregados (indicadores, relatórios, features de modelagem) |
| `/notebooks` | Notebooks Databricks (.dbc ou .ipynb) com o código de análise |
| `/src` | Scripts auxiliares em Python |
| `/docs` | Apresentação final e documentação do projeto |

---

## 👥 Integrantes do Projeto
| Nome | Função |
|------|---------|
|1. **Susan Capelo** | Coordenação geral, integração das entregas e documentação final  
|2. **Jardel Simplício** | Ingestão e limpeza de dados (base Sinistros)  
|3. **Manoel Nascimento** | Ingestão e limpeza de dados (base Seguros de vida)
|4. **Arthur Cavalcanti** | Análise exploratória e visualizações (Camada Ouro)
|5. **Ramón Taffarel** | Modelagem estatística e geração de indicadores
|6. **Paulo Nery** | Automação, integração e testes no Databricks   

---

## 🧠 Etapas Realizadas
1. Carregamento e inspeção inicial dos dados ✅ 
2. Limpeza e tratamento de valores nulos  
3. Análise exploratória  
4. Correlação entre variáveis relevantes  
5. Identificação de padrões e tendências  
6. Construção de modelo preditivo

---

## 🧾 Dados Utilizados
Os dados foram disponibilizados pela NTTData e simulam informações reais do **setor de seguros**.  
Os arquivos originais estão armazenados em `/data/raw`.  

---

## 💬 Resultados e Insights

---

## 🚀 Desenho da Solução Técnica


---

## ✅ O que deu certo


## ⚠️ O que deu ruim


## 💡 O que faríamos diferente

---

## 🔗 Integração com GitHub e Databricks
Para editar colaborativamente:
1. Cada membro conecta seu Databricks à sua conta GitHub:  
   **User Settings → Git Integration → Link your GitHub account**
2. Todos usam o mesmo repositório do grupo.
**ATENÇÃO**
3. Antes de editar: **File → Revision History → Pull from Git**
4. Após editar: **Commit & Push**

---

## 🧰 Como Executar o Projeto
1. Abra o notebook no Databricks
2. Conecte a um cluster ativo   
3. Execute célula por célula ou rode todo o notebook  
4. Verifique as saídas e gráficos gerados

---

## 📄 Licença
Este projeto é de uso acadêmico, desenvolvido para fins educacionais na Residência NTT Data – Porto Digital / CESAR School.
