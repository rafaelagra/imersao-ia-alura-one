# 🤖 Aula 2 — Agente Comercial de Propostas (`ARI Deal`)

Este repositório contém a implementação completa do **Agente Comercial ARI Deal**, desenvolvido durante a **Aula 2 da Imersão IA (ONE + Alura)**. O projeto combina engenharia de prompt, definição de *Skills* personalizadas no ambiente **Claude Desktop / Cowork** e automação de documentos corporativos no formato `.docx`.

---

## 🎯 Objetivo do Projeto

Automatizar o fluxo da equipe de vendas da **ARI CONSULTING** (consultoria especializada em soluções Oracle Cloud), cobrindo de ponta a ponta:

1. **Validação Estruturada de Briefings:** leitura e auditoria dos dados de entrada fornecidos pelos executivos de vendas.
2. **Checagem de Regras de Negócio e Catálogo:** validação contra o catálogo oficial de serviços (módulos, prazos, limites financeiros e faixas de desconto).
3. **Gestão de Alertas e Governança:** trava automática e obrigatoriedade de *Estudo de Caso* para propostas com investimento superior a R$ 200.000.
4. **Geração Automatizada de Propostas:** exportação do documento final `.docx` formatado de acordo com o *Brand Book* e o template institucional da empresa.

---

## 📁 Estrutura do Diretório

```text
aula-2-agente-de-propostas/
├── Base-Conhecimento/              # Contexto global carregado no Claude / Cowork
│   ├── Catalogo-Servicos-2026-ARI-CONSULTING.pdf  # Tabela oficial de serviços e regras
│   ├── Proposta-Comercial-ARI-CONSULTING.docx     # Template institucional de 5 seções
│   └── brand-book.json                            # Diretrizes visuais (paleta dark/mono, fontes Arial)
├── briefings/                      # Entradas brutas dos clientes
│   └── briefing-teste-vetria-embalagens.txt      # Briefing de teste recebido (Vetria)
├── Docs-Ref/                       # Documentos e diretrizes de apoio da imersão
├── outputs/                        # Propostas comerciais finais validadas e geradas (.docx)
│   ├── Proposta-196-2026-Banco-Central-do-Sul-ARI-CONSULTING.docx
│   └── Proposta-197-2026-Vetria-Embalagens-ARI-CONSULTING.docx
└── skills/                         # Skill reutilizável do agente
    └── ari-consulting-propostas-SKILL.md
```

---

## 🛠️ Regras de Negócio & Lógica do Agente

O agente foi instruído com base em regras rígidas de governança comercial da ARI CONSULTING.

### 1. Auditoria dos 10 Campos Obrigatórios do Briefing

Para qualquer briefing recebido, o agente faz o *parsing* e valida a presença de:

| Bloco | Campos |
|-------|--------|
| **A** | A1: Razão Social · A2: Setor · A3: Contato Principal |
| **B** | B1: Cenário Atual e Dor · B2: Dimensão da Operação |
| **C** | C1: Serviços do Catálogo Correspondentes · C2: Data Prevista de Início |
| **D** | D1: Número da Proposta · D2: Consultor Responsável (`@ariconsulting.com.br`) |
| **E** | E1: Investimento Estimado |

### 2. Tabela de Serviços & Descontos por Combinação

- **Catálogo Fechado:** apenas serviços válidos do portfólio oficial (Serviços 01 a 08).
- **Desconto de Pacote:** desconto automático de 10% a 15% para contratação combinada de 2 ou mais serviços.
- **Condições Padrão de Pagamento:**
  - `30%` na Assinatura do Contrato
  - `40%` na Conclusão da Fase de Build
  - `30%` no Go-Live

### 3. Trava de Alerta e Governança (> R$ 200.000)

Toda proposta cujo valor final consolidado ultrapassar a trava de **R$ 200.000** aciona obrigatoriamente um **Alerta de Governança**, exigindo:

- a inclusão de um **Estudo de Caso de Referência da Indústria**; e
- a revisão do **Gerente de Contas (Account Manager)** antes do envio final.

---

## 📄 Estudo de Caso de Teste: Vetria Embalagens Industriais S.A.

Durante a aula, validamos e geramos a **Proposta 197/2026**.

- **Cliente:** Vetria Embalagens Industriais S.A. (1.450 colaboradores, 5 plantas em SC/PR/RS, R$ 680 mi/ano).
- **Dores:** fechamento contábil lento (14 dias úteis), 3 ERPs legados heterogêneos (Protheus, Sankhya, Delphi) e exposição a pagamentos duplicados.

### Serviços Selecionados

| Serviço | Descrição | Valor |
|---------|-----------|------:|
| **02** | Implementação Oracle ERP Cloud Financials (General Ledger, Accounts Payable, Cash Management) | `R$ 180.000` |
| **05** | Integração Oracle com Sistemas Legados via OIC | `R$ 60.000` |

### Financeiro Consolidado

| Item | Valor |
|------|------:|
| Subtotal | `R$ 240.000` |
| Desconto de Combinação (10%) | `-R$ 24.000` |
| **Valor Total** | **`R$ 216.000`** |

> ⚠️ **Acionou a Trava de Governança (> R$ 200k).**

**Resultado Gerado:** documento `Proposta-197-2026-Vetria-Embalagens-ARI-CONSULTING.docx` salvo na pasta `outputs/`.

---

## 🚀 Como Replicar no Claude Desktop (Cowork)

1. **Configuração do Projeto**
   - Crie um novo *Project* no Claude chamado **ARI DEAL - Imersão**.
   - Vincule a pasta local `Base-Conhecimento/` como diretório de contexto do projeto.

2. **Carregamento da Skill**
   - Adicione o conteúdo do arquivo `skills/ari-consulting-propostas-SKILL.md` às instruções ou aos arquivos do projeto.

3. **Execução**
   - Forneça um arquivo de briefing em `.txt` ou cole o texto diretamente no chat.
   - O agente emitirá o **Relatório de Validação de Briefing** com o status de cada campo obrigatório e os alertas de negócio.
   - Solicite a geração e o salvamento do arquivo `.docx` final no diretório configurado.

---

## 💻 Autor & Contexto

- **Desenvolvido por:** Rafael Agra
- **Evento:** Imersão IA (Oracle Next Education — ONE + Alura)
- **Ambiente de Execução:** Claude Desktop / Cowork
