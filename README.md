# 🤖 Imersão IA — Alura + ONE (Oracle Next Education)

Bem-vindo ao repositório dedicado aos projetos, pipelines de Agentes de IA e automações desenvolvidos durante a **Imersão IA**, promovida pela **ONE** em parceria com a **Alura AI for Business**.

🔗 **Repositório:** [github.com/rafaelagra/imersao-ia-alura-one](https://github.com/rafaelagra/imersao-ia-alura-one)

---

## 🗂️ Visão Geral

| Aula | Projeto | Plataforma | Tipo de Agente |
|:----:|---------|------------|----------------|
| 01 | [📰 ARI News](./aula-01-ari-news) | Google Opal | Pipeline de pesquisa e dashboard |
| 02 | [🤝 ARI Deal](./aula-2-agente-de-propostas) | Claude Desktop / Cowork | Agente comercial de propostas |
| 03 | [📬 ARI Flow](./aula-3-ARI-Flow) | Make.com + Gemini AI | Agente autônomo de atendimento com RAG |

---

## 📅 Projetos Desenvolvidos

### 📰 [Aula 01 — ARI News: Dashboard de Inteligência Estratégica](./aula-01-ari-news)

- **Tecnologias:** Google Opal (Visual Pipeline / No-Code)
- **Conceitos:** Nós, Skills, Ancoragem Temporal, Guardrails contra Alucinações de URLs e Renderização HTML/CSS personalizada.
- **Descrição:** Pipeline autônomo que pesquisa notícias em tempo real, valida os links dinâmicos, gera uma imagem conceitual e entrega um painel de inteligência de negócios formatado em menos de 2 minutos.

### 🤝 [Aula 02 — ARI Deal: Agente Comercial de Propostas](./aula-2-agente-de-propostas)

- **Tecnologias:** Claude Desktop / Cowork, Skills personalizadas e geração de documentos `.docx`
- **Conceitos:** Base de Conhecimento, Skills reutilizáveis, Validação de Briefings, Regras de Negócio, Travas de Governança e Brand Book.
- **Descrição:** Agente que audita os 10 campos obrigatórios do briefing comercial, valida os serviços contra o catálogo oficial da ARI CONSULTING, aplica descontos por combinação, aciona alertas de governança para propostas acima de R$ 200.000 e gera a proposta final em `.docx` seguindo o template institucional.

### 📬 [Aula 03 — ARI Flow: Agente de Atendimento e Triagem Autônoma com IA e RAG](./aula-3-ARI-Flow)

- **Tecnologias:** Make.com (iPaaS / No-Code), Google Gemini AI, Gmail e Google Drive
- **Conceitos:** RAG Autônomo, Classificação Binária, Roteamento Inteligente, Base de Conhecimento Viva e Agendamento 24/7.
- **Descrição:** Help Desk autônomo que monitora a caixa do Gmail, classifica cada e-mail com o Gemini, responde dúvidas sobre Oracle Cloud Applications consultando manuais no Google Drive (resposta em HTML) e encaminha os demais assuntos para atendimento humano, rodando automaticamente a cada 15 minutos.

---

## 🛠️ Habilidades e Conceitos Aplicados

- **Arquitetura de Agentes:** Orquestração de múltiplos modelos de linguagem rodando em sequência e em paralelo.
- **Engenharia de Prompts:** Mapeamento de variáveis, instruções de sistema (*System Instructions*) e regras de design.
- **Guardrails de Segurança:** Mecanismos automáticos de validação e prevenção de URLs inexistentes.
- **Prototipagem No-Code:** Construção de fluxos visuais complexos usando o Google Opal e o Make.com.
- **Skills Personalizadas:** Criação de instruções reutilizáveis que encapsulam o fluxo comercial completo em Claude Desktop / Cowork.
- **Governança Comercial:** Validação de dados de entrada, catálogo fechado de serviços, regras de desconto e travas de aprovação.
- **Automação de Documentos:** Geração de propostas `.docx` padronizadas conforme template e identidade visual da empresa.
- **RAG (Retrieval-Augmented Generation):** Evolução do RAG assistido (chat) para o RAG autônomo, com respostas fundamentadas em uma base de conhecimento viva.
- **Roteamento e Triagem:** Classificação automática de requisições e separação entre resposta por IA e atendimento humano.
- **Integração de Serviços (iPaaS):** Conexão entre Gmail, Google Drive e a API do Gemini em uma esteira de automação agendada.

---

## 📁 Estrutura do Repositório

```text
imersao-ia-alura-one/
├── README.md
├── aula-01-ari-news/               # Aula 01 — Dashboard de Inteligência Estratégica (Google Opal)
├── aula-2-agente-de-propostas/     # Aula 02 — Agente Comercial de Propostas (Claude Desktop / Cowork)
└── aula-3-ARI-Flow/                # Aula 03 — Agente de Atendimento com RAG (Make.com + Gemini)
```

---

## 🚀 Como Explorar

```bash
git clone https://github.com/rafaelagra/imersao-ia-alura-one.git
cd imersao-ia-alura-one
```

Cada pasta de aula possui seu próprio `README.md` com a arquitetura, os prompts utilizados, os resultados dos testes e o passo a passo para replicar o projeto.

---

## 💻 Autor

- **Desenvolvido por:** Rafael Agra
- **GitHub:** [@rafaelagra](https://github.com/rafaelagra)
- **Evento:** Imersão IA (Oracle Next Education — ONE + Alura)
