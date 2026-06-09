# MiniGuia
# Caderno Temático — Modelos de Linguagem e Engenharia de Prompts

## Contexto e Objetivos
Assunto escolhido: Modelos de Linguagem de Grande Escala (LLMs) e técnicas de engenharia de prompts.

Objetivos de estudo:
- Entender os fundamentos arquiteturais (Transformer) e evolução (BERT, GPT).
- Praticar engenharia de prompts para extrair respostas úteis e verificáveis.
- Documentar perguntas, variações de prompt, resultados e dificuldades ("cicatrizes").
- Produzir um miniguia com resumos, glossário e prompts reutilizáveis.

## Curadoria de Fontes (3–5)

As fontes abaixo foram selecionadas por serem abertas e relevantes. Substitua os placeholders pelos links/arquivos PDF que você carregou no NotebookLM, se aplicável.

1. Attention Is All You Need — Vaswani et al. (Transformer) (arXiv)
	 - Link: https://arxiv.org/abs/1706.03762
	 - Arquivo no NotebookLM (exemplo): NOTEBOOKLM_UPLOAD: attention_is_all_you_need.pdf
2. BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding (arXiv)
	 - Link: https://arxiv.org/abs/1810.04805
	 - Arquivo no NotebookLM (exemplo): NOTEBOOKLM_UPLOAD: bert.pdf
3. Language Models are Few-Shot Learners (GPT-3) — Brown et al. (arXiv)
	 - Link: https://arxiv.org/abs/2005.14165
	 - Arquivo no NotebookLM (exemplo): NOTEBOOKLM_UPLOAD: gpt3.pdf
4. The Illustrated Transformer — Jay Alammar (blog explicativo)
	 - Link: http://jalammar.github.io/illustrated-transformer/

5. Estudo no NotebookLM — coleção pessoal de anotações e uploads
	- Link (NotebookLM): https://notebooklm.google.com/notebook/0762ad7a-b42e-4a45-9403-ac2e532d2c81

Observação: Coloque aqui os links diretos aos arquivos PDF que você enviou ao NotebookLM (ou ao repositório), por exemplo: `https://notebooklm/.../meu_arquivo.pdf`.

## Engenharia de Prompts e "Cicatrizes"

Objetivo da sessão de prompts: formular perguntas que gerem resumos estruturados, exemplos práticos e referências.

Exemplos de perguntas estratégicas (prompt templates):

- Prompt base — Resumo estruturado:
	- "Resuma em até 8 pontos os conceitos principais do artigo {TÍTULO} e cite as referências usadas." 
- Prompt para comparação:
	- "Compare as principais diferenças entre {MODELO_A} e {MODELO_B} em termos de arquitetura, treino e limitações." 
- Prompt para aplicação prática:
	- "Dê 3 exemplos de prompts para extrair respostas concisas sobre {TEMA}, incluindo instruções de verificação de fontes." 

Variações testadas (exemplos):
- Instrução direta vs. instrução com contexto (adicionar 1-2 frases de background);
- Pedir etapas numeradas (para forçar estrutura) vs. parágrafo livre;
- Solicitar citações e URLs (para validar ser referência).

Registro de respostas e troubleshooting (cicatrizes):
- Observação: a IA tende a "alucinar" citações quando não solicitada especificamente. Estratégia: pedir explicitamente "cite as frases exatas e os links" ou peça para indicar "fontes primárias".
- Quando as respostas eram vagas, a variação que funcionou melhor foi: "Responda em 5 bullets; para cada bullet, inclua uma referência (autor, ano, link)".
- Dificuldades comuns: respostas muito longas; mitigação: limitar por tokens/char ou pedir resumo em N bullets.

## Miniguia de Estudo (Entrega Final)

1) Resumos estruturados (síntese):
- Transformer: arquitetura baseada em atenção, sem convoluções/recorrência; self-attention permite relacionar tokens globalmente.
- BERT: pré-treinamento bidirecional com masked language modeling; forte para tarefas de compreensão (classification, NER).
- GPT (família): modelos autoregressivos, fortes em geração e few-shot learning; dependem fortemente de instruções (prompts).

2) Glossário (principais conceitos):
- Transformer: arquitetura baseada em camadas de atenção e feed-forward.
- Self-Attention: mecanismo que calcula atenção entre todos os pares de tokens.
- Masked LM: tarefa de pré-treinamento que mascara tokens e treina o modelo para predição.
- Autoregressivo: geração de texto token-a-token condicionada no histórico.

3) Conjunto de prompts reutilizáveis
- Resumo curto e referenciado:
	- "Resuma o artigo {TÍTULO} em 6 bullets; para cada bullet, inclua uma referência (autor, ano, link)."
- Checklist de leitura crítica:
	- "Liste 5 pontos para avaliar a qualidade metodológica deste artigo e explique por que cada ponto importa." 
- Revisão rápida para revisão por pares:
	- "Avalie os pontos fortes e fracos deste trabalho, dando recomendações práticas para melhoria." 

Sugestão de uso: mantenha um arquivo `prompts.md` no repositório com suas versões e respostas coletadas.

---

## Como Entregar na Plataforma da DIO

1. Acesse o seu GitHub e crie um novo repositório para o projeto.
2. Estruture seu `README.md` com todos os passos solicitados acima (objetivos, fontes, testes de prompts e o miniguia).
3. Após finalizar a documentação, copie a URL principal do seu repositório.
4. Na página do Desafio de Projeto na DIO, clique em "Entregar projeto".
5. Cole o link do repositório no GitHub, adicione uma descrição sobre o tema estudado e confirme a entrega.

## Próximos passos recomendados
- Subir os PDFs usados para o NotebookLM (ou colocar links públicos) e substituir os placeholders em "Curadoria de Fontes".
- Executar as variações de prompt e salvar as respostas em `prompts.md`.
- Opcional: adicionar exemplos de respostas obtidas (trechos) em uma pasta `evidence/`.

---

## Guia de Qualidade de Software: Comportamento, Agilidade e Testes

Objetivo: fornecer um mini-guia prático para avaliar e melhorar a qualidade de software considerando comportamento (qualidade percebida e observável), práticas ágeis e estratégias de teste.

- **Princípios-chave**:
	- Entregar valor continuamente; validar com usuários cedo e frequentemente.
	- Qualidade embutida: descobrir defeitos o mais cedo possível (shift-left).
	- Medir comportamento do sistema em produção (observabilidade) e usar feedback para priorizar correções.

- **Práticas Ágeis Recomendadas**:
	- Iterações curtas (Sprints ou ciclo Kanban de 1–2 semanas).
	- Definition of Done que inclua testes automatizados e revisão de segurança básica.
	- Revisões de backlog com critérios de aceitação claros e testes de aceitação automatizados.

- **Estratégia de Testes**:
	- Testes unitários: alta cobertura de lógica crítica; rápidos e isolados.
	- Testes de integração: validar contratos entre módulos e dependências externas (DB, APIs).
	- Testes de aceitação/end-to-end: cenários de usuário prioritários; usar ambientes estáveis/infra de testes.
	- Testes de comportamento (BDD): usar cenários Gherkin para alinhar equipe técnica e negócio.
	- Testes exploratórios regulares para encontrar problemas não previstos por casos automatizados.

- **Checklist Rápido (pronto para entrega)**:
	- Código com cobertura mínima acordada e testes relevantes verdes.
	- Pipeline CI executando linters, testes e build automatizado.
	- Monitoramento e alertas configurados para erros críticos em produção.
	- Segurança básica: scanning de dependências e análise estática.

- **Métricas úteis**:
	- Lead time (commit → produção), MTTR (mean time to recovery), taxa de falhas em produção, cobertura de testes por área crítica.

- **Prompts recomendados para revisão automática com LLMs**:
	- "Revise este trecho de código e liste 5 possíveis riscos de qualidade e sugestões de melhoria." 
	- "Gere um checklist de testes de integração para um endpoint que faz {AÇÃO} com {DEPENDÊNCIAS}."

Referências e estudo base: veja a coleção no NotebookLM (link acima) para aprofundar artigos e exemplos práticos.

Se quiser, eu já atualizo os placeholders com os links dos PDFs se você me enviar os arquivos ou os URLs.
# miniguia-estudos-notebooklm
criar um Caderno Temático no NotebookLM
