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
|2. **Manoel Nascimento** | Ingestão e limpeza de dados e visualização
|3. **Paulo Nery** | Tratamento de Encoding e Normalização de Texto  
|4. **Jardel Simplício** |Qualidade de Dados e Padronização
|5.**Arthur Cavalcanti** | Inteligência de Negócio e KPIs
|6.**Ramón Taffarel** | Inteligência de Negócio e KPIs
 
---

## 🧠 Etapas Realizadas
1. Carregamento e inspeção inicial dos dados ✅ 
2. Limpeza e tratamento de valores nulos ✅ 
3. Análise exploratória  ✅  
4. Correlação entre variáveis relevantes  ✅   
5. Identificação de padrões e tendências  ✅ 
6. Construção de modelo preditivo  ✅ 

---

## 🧾 Dados Utilizados
Os dados foram disponibilizados pela NTTData e simulam informações reais do **setor de seguros**.  
Os arquivos originais estão armazenados em `/data/raw`.  

---

## 💬 Resultados e Insights
Através da implementação da **Arquitetura Medalhão (Bronze, Prata e Ouro)** no Databricks, transformamos dados brutos e não estruturados em inteligência estratégica. O projeto permitiu sair de uma gestão baseada em volume para uma gestão baseada em valor e risco.

### 🔍 Principais Descobertas (Key Findings)

1.  **O "Mapa do Lucro" (Rentabilidade):**
    * **Gênero:** O público feminino apresentou uma sinistralidade **4 p.p. menor** (34%) em comparação ao masculino (38%), indicando um segmento de maior margem.
    * **Geografia:** A região **Nordeste** demonstrou ser a mais rentável, enquanto o Centro-Oeste pressiona as margens com maior frequência de sinistros.

2.  **Segmentação de Carteira (Q1 vs Q3):**
    * Utilizando estatística descritiva (*approxQuantile*), segregamos clientes de **Alto Capital (Q3)** dos clientes de entrada **(Q1)**.
    * **Insight:** Embora a frequência de acidentes seja similar, o impacto financeiro é discrepante, exigindo esteiras de atendimento diferenciadas (Varejo vs. Prime).

3.  **Auditoria e Compliance:**
    * Detectamos inconsistências contratuais graves, como casos de **Autosseguro** (Contratante = Beneficiário), que foram mapeados para saneamento.
---

## 🚀 Desenho da Solução Técnica
1. **Fontes de Dados (Raw)**
* Arquivos CSV
- Dados Legados (Seguros & Sinistros) com formatação mista.
⬇ (Ingestão)
2. **Camada Bronze (Input)**
* Ingestão Bruta
- Leitura dos arquivos originais via Pandas/Spark. Manutenção do dado "como veio" para auditoria.
⬇ (Tratamento & Limpeza)
3. **Camada Prata (Trusted)**
* Saneamento e Qualidade
- Correção de Encoding (caracteres estranhos).
- Conversão de Tipos (Texto -> Float/Date).
- Integração de dados (segurosxsinistros).
⬇ (Regras de Negócio)
4. **Camada Ouro (Refined)**
* Inteligência e Agregação
- Feature Engineering (Criação de Região, Sexo).
- Segmentação (Quartis de Capital).
- Cálculo de KPIs (Sinistralidade).
⬇ (Consumo)
5. **Visualização (Output)**
* Insights de Negócio
- Tabelas analíticas, Gráficos de perfil de risco e Dashboards.

---

## ✅ O que deu certo
1. Nosso pipeline no Databricks, não só rodou, como gerou insights valiosos.
2. Conseguimos padronizar campos de datas e valores que vieram "sujos" da origem. 
3. O script processa 85.000 registros  em segundos, algo inviável de fazer em planilhas manuais.

## ⚠️ O que deu ruim
1. Tivemos que lutar contra erros de caracteres (encoding). 
2. Os arquivos CSV vieram com formatações monetárias mistas , o que exigiu um esforço extra de limpeza. 
3. Muitos sinistros não tinham correspondência direta clara na base de apólices pelo nome exato, dificultando o "match" perfeito.
4. Dificuldade de usar a ferramenta de criação de gráficos do Databricks.

## 💡 O que faríamos diferente
| O que fizemos  | O que faríamos |
|------|---------|
|Começamos limpando tudo para depois buscar perguntas | Definiríamos as Perguntas de Negócio (KPIs) no "Dia 0". Gastamos tempo limpando colunas que nem usamos
|Cruzamos tabelas por "Nome Exato". Se estava "Ana Maria Souza" na apólice e "Ana M. Souza" no sinistro, o código não achava |Aplicaríamos Fuzzy Matching (correspondência por similaridade de texto). Como não tínhamos ID, essa técnica teria recuperado mais sinistros
|Trabalhamos em esteira sequencial . (um esperava o outro terminar um passo para começar o outro)|Teríamos feito Pair Programming nas etapas iniciais de limpeza. A passagem da camada Bronze para a Prata gerou gargalos que poderiam ser resolvidos se a validação dos dados fosse conjunta desde o início

---

## 🔗 Integração com GitHub e Databricks
Para editar colaborativamente:
1. Cada membro conecta seu Databricks à sua conta GitHub:  
   **Users (clica nos 3 pontos) → Create → Git Folder → Link GitHub**
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
