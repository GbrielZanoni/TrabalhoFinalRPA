# Invoice Generator Automation - UiPath

![UiPath](https://img.shields.io/badge/UiPath-RPA-blue?logo=uipath)
![Excel](https://img.shields.io/badge/Input-Excel-green?logo=microsoft-excel)
![Email](https://img.shields.io/badge/Email-Automated-blue)
![Currency](https://img.shields.io/badge/Currency-Converter-yellow)
![Platform](https://img.shields.io/badge/Platform-Windows%20Only-blue)
![License](https://img.shields.io/github/license/GbrielZanoni/TrabalhoFinalRPA)
![Discord](https://img.shields.io/badge/Chat-Discord-blue?logo=discord)
[![Jira](https://img.shields.io/badge/Jira-Project-blue?logo=jira)](https://edu-team-nwdewzza.atlassian.net/jira/software/projects/R12345/boards/36?atlOrigin=eyJpIjoiYjljMTI5OGM3YWEyNGIwMzg5Nzk4ZDA2ZDY5ODFhOGMiLCJwIjoiaiJ9)

---

# Sobre o Projeto

Este repositório contém uma automação desenvolvida em **UiPath** com o objetivo de processar e gerar **Invoices (faturas comerciais)** a partir de dados de uma planilha Excel. O robô realiza tratamento de dados, identifica inconsistências, gera documentos e envia os resultados automaticamente por e-mail.

---

# Visão Geral do Processo

1. **Entrada**:
   - Planilha `Purchase_plan.xlsx` contendo os dados das faturas.
2. **Tratamento dos Dados**:
   - Corrige campos incompletos ou inválidos.
   - Identifica registros com problemas e os salva separadamente.
3. **Geração de Invoices**:
   - Preenchimento automático no site [invoice-generator.com](https://invoice-generator.com/).
   - Download dos PDFs gerados.
4. **Exportação**:
   - Invoices com problema → `invoice_problem_data_[data].xlsx`
   - Invoices válidas → PDFs salvos na pasta `invoice_created/`
   - Consolidado financeiro → `total_invoices.txt`
5. **Conversão de Moedas**:
   - Conversão BRL → USD, EUR, GBP via site [x-rates.com](https://www.x-rates.com/)
6. **Envio de E-mail**:
   - Anexos: planilha de erros, consolidado `.txt`, e invoices `.zip`
   - Suporte para envio dividido caso os arquivos ultrapassem 5MB

---

# Regras de Negócio Aplicadas

- **Campos obrigatórios**:
  - Data, Termos de pagamento, Itens, etc.
  - Valores ausentes ou inválidos vão para a planilha de erros.
- **Entrega**:
  - Importado: prazo 90 dias
  - Nacional: prazo 30 dias
- **Tipo de envio conforme valor**:
  - ≤ R$10.000 → carro
  - R$10.001 a R$30.000 → barco
  - +R$30.000 → avião
- **Impostos por tipo de envio e nacionalidade**:
  - Nacional: 0% a 4%
  - Importado: 10% a 20%

---

# Arquivos Gerados

| Arquivo                          | Descrição                                                |
|----------------------------------|------------------------------------------------------------|
| `invoice_problem_data_[data].xlsx` | Planilha com faturas com erro e motivo detalhado          |
| `invoice_created/`               | Pasta contendo PDFs das faturas válidas                   |
| `total_invoices.txt`             | Texto com valor total consolidado em BRL, USD, EUR e GBP  |
| `Invoices_Criadas_[data].zip`    | Arquivo compactado com as faturas em PDF                  |

---

# Requisitos

- UiPath Studio instalado
- Microsoft Excel instalado ou compatível com o Excel Activities
- Acesso à internet para:
  - [invoice-generator.com](https://invoice-generator.com)
  - [x-rates.com](https://www.x-rates.com)
- Conta de e-mail configurada para envio automático (SMTP)
- Planilha de entrada com estrutura e cabeçalhos padronizados
- Sistema operacional Windows (compatível com automação via navegador)
--- 
#  Integrantes

|  Nome               |  GitHub                                                  |  Função        |
|-----------------------|------------------------------------------------------------|------------------|
| Gabriel Zanoni        | [@GbrielZanoni](https://github.com/GbrielZanoni)           | Tech Lead        |
| Maria Delmonaco       | [@mariadelmonaco](https://github.com/mariadelmonaco)       | Scrum Master     |
| Gabriel Moura         | [@gmoura0](https://github.com/gmoura0)                     | Product Owner    |
| Alexandre Santos      | [@AlexandreGSSantos](https://github.com/AlexandreGSSantos) | Developer        |

--- 

# Passo-a-Paso da Instalação
