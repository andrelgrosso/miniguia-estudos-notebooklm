# 🧠 Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

> Esta seção documenta o processo de extração de conhecimento do repositório, detalhando as perguntas estratégicas elaboradas, variações de prompts testadas, referências extraídas dos documentos oficiais e as dificuldades técnicas superadas (*troubleshooting*).

---

## 📋 Histórico de Perguntas Estratégicas e Engenharia de Contexto

<details>
<summary><b>1. Qual é a principal mudança de paradigma no papel do Analista Financeiro moderno?</b></summary>

* **Prompt Inicial (Fraco):** O que faz um analista financeiro de acordo com o curso?
* **Prompt Otimizado (Engenharia de Prompt):** `[Contexto]` Você é um especialista em desenvolvimento de carreiras e finanças corporativas. `[Instrução]` Com base no arquivo "Conheça o Curso ProdCast360", identifique qual é a principal mensagem sobre a mudança de comportamento esperada de um analista financeiro moderno. Evite respostas genéricas e foque no contraste entre operacional e estratégico.
* **Resposta Obtida:** Ser analista financeiro vai além de dominar planilhas e fórmulas. O mercado exige transformar dados brutos em informação relevante, atuando como um "detetive" das finanças para encontrar as causas por trás dos números, prever riscos e propor recomendações viáveis.
* **Referência:** *Conheça o Curso ProdCast360 - Analista Financeiro.docx (Seções: Introdução e Resumo do mergulho)*.
* **Cicatrizes / Troubleshooting:** O prompt inicial gerava tarefas padrão de descrição de cargo do Google. Foi necessário aplicar a técnica de *Contexto e Restrição* para forçar a IA a extrair a metáfora do "médico/detetive" contida especificamente no documento fornecido.

</details>

<details>
<summary><b>2. Quais as competências exigidas para que um profissional de finanças se destaque em um processo seletivo?</b></summary>

* **Prompt Inicial (Fraco):** Como se destacar no mercado?
* **Prompt Otimizado (Engenharia de Prompt):** `[Instruções Claras]` Usando o documento "Conheça o Curso ProdCast360", liste em tópicos curtos e objetivos as três ações que um analista deve tomar em uma entrevista ou processo seletivo para demonstrar valor além dos números.
* **Resposta Obtida:** 1. Explicar o significado real dos números apresentados; 2. Apontar causas prováveis e seus impactos no negócio; 3. Apresentar recomendações viáveis para a melhoria de resultados.
* **Referência:** *Conheça o Curso ProdCast360 - Analista Financeiro.docx (Seção: Como se destacar no mercado)*.
* **Cicatrizes / Troubleshooting:** A IA tentava criar dicas de comportamento corporativo gerais (ex: vestimenta, oratória). A adição da restrição `[Usando o documento...]` corrigiu o desvio (*guardrails* de escopo).

</details>

<details>
<summary><b>3. O que define o conceito e o objetivo da "Negociação Transformacional" ensinada no Módulo 3?</b></summary>

* **Prompt Inicial (Fraco):** O que é negociação transformacional?
* **Prompt Otimizado (Engenharia de Prompt):** `[Especificar Estrutura de Saída]` Com base nas interações do Quiz e no Módulo 3, defina "Negociação Transformacional" em formato JSON com as chaves: "caracteristica_principal", "foco_01", "foco_02" e "objetivo_longo_prazo".
* **Resposta Obtida:**
  ```json
  {
    "caracteristica_principal": "Transformação da relação de negócios através da criação de valor mútuo",
    "foco_01": "Soluções Ganha-Ganha",
    "foco_02": "Colaboração e Criatividade para atender interesses de todos",
    "objetivo_longo_prazo": "Fortalecimento de vínculos e parcerias estratégicas baseadas em confiança"
  }
  ```
* **Referência:** *Quiz: Análise Financeira Produtividade 360 e Apostila Mod. 3*.
* **Cicatrizes / Troubleshooting:** O modelo inicialmente ignorava o formato JSON e respondia em texto corrido. Foi aplicada a técnica de *Preparar a Saída* adicionando "{" no final do prompt para guiar a sintaxe da inteligência artificial.

</details>

<details>
<summary><b>4. Como a Inteligência Artificial e a automação transformam o Módulo 5, e quais são seus desafios éticos?</b></summary>

* **Prompt Inicial (Fraco):** O que o módulo 5 fala de IA?
* **Prompt Otimizado (Engenharia de Prompt):** `[Dividir a Tarefa]` Analise o Módulo 5 (Tecnologia e Inovação). Primeiro, descreva o benefício do Machine Learning nas previsões financeiras. Segundo, liste os quatro pilares éticos exigidos na adoção dessa tecnologia.
* **Resposta Obtida:** O Machine Learning traz previsões de precisão para antecipar cenários. Contudo, exige atenção a 4 pilares: Transparência dos algoritmos, Privacidade dos dados, Mitigação de viés algorítmico e Definição clara de Responsabilidade (governança).
* **Referência:** *Apostila+Mod.+5.pdf (Módulo 5: Seções 4. Inteligência Artificial e Automação)*.
* **Cicatrizes / Troubleshooting:** Ao pedir tudo junto, a IA esquecia de listar os pilares éticos detalhados. A quebra em etapas (*Chain of Thought / Dividir a Tarefa*) garantiu que os dois aspectos fossem respondidos com profundidade.

</details>

<details>
<summary><b>5. Quais as principais ferramentas tecnológicas recomendadas para a Gestão de Fluxo de Caixa no início do treinamento?</b></summary>

* **Prompt Inicial (Fraco):** Quais softwares usar em finanças?
* **Prompt Otimizado (Engenharia de Prompt):** `[Restrições]` Restrinja sua resposta estritamente ao Módulo 1. Quais são as quatro categorias de softwares/tecnologias recomendadas para a otimização e controle das entradas e saídas de caixa?
* **Resposta Obtida:** 1. Softwares de contabilidade; 2. Sistemas de gestão financeira integrados (ERP); 3. Aplicativos de previsão de fluxo de caixa; 4. Ferramentas de análise de dados (processamento de grandes volumes).
* **Referência:** *Apostila+Mod.+1.pdf (Seção 4: Ferramentas e Softwares para Gestão de Fluxo de Caixa)*.
* **Cicatrizes / Troubleshooting:** Sem a restrição de contexto, a IA sugeria ferramentas de mercado modernas que não constavam na ementa do curso (como Tableau, PowerBI, Python). A imposição do escopo blindou o conteúdo.

</details>

<details>
<summary><b>6. Qual é a estratégia recomendada no Módulo 4 para reduzir custos sem destruir o valor da empresa?</b></summary>

* **Prompt Inicial (Fraco):** Como reduzir custos na apostila 4?
* **Prompt Otimizado (Engenharia de Prompt):** `[Contexto]` Atue como um consultor sênior de eficiência operacional. `[Instrução]` Extraia do Módulo 4 a filosofia básica por trás do corte de despesas. O que nunca deve ser sacrificado segundo o texto?
* **Resposta Obtida:** O desafio constante é reduzir custos operacionais e desperdícios através de métodos de otimização e benchmarking, mas **sem comprometer ou sacrificar a qualidade** dos produtos ou serviços da organização.
* **Referência:** *Apostila+Mod.+4.pdf (Módulo 4: Seção 1. Estratégias de Redução de Custos)*.
* **Cicatrizes / Troubleshooting:** Respostas iniciais divagavam sobre demissões e corte de pessoal. A atribuição de papel (*Persona/Contexto*) focou a IA no viés técnico-institucional do módulo (qualidade e processos).

</details>

<details>
<summary><b>7. Quais os quatro pilares da Governança Corporativa explicados no Módulo 2 e reforçados no Módulo 6?</b></summary>

* **Prompt Inicial (Fraco):** O que é governança corporativa no curso?
* **Prompt Otimizado (Engenharia de Prompt):** `[Adicionar Sintaxe Clara]` Pesquise nos Módulos 2 e 6 os fundamentos da governança corporativa e monte uma tabela Markdown contendo o nome do princípio e a sua respectiva definição oficial fornecida no material.
* **Resposta Obtida:**
  | Princípio | Definição Oficial do Curso |
  | :--- | :--- |
  | **Princípios Éticos** | Conjunto de valores e normas que promovem integridade, justiça e responsabilidade. |
  | **Transparência** | Prática de divulgar informações claras, precisas e completas aos stakeholders. |
  | **Responsabilidade** | Obrigação de prestar contas e assumir a responsabilidade pelas ações e decisões empresariais. |
  | **Equidade** | Princípio de tratar todos os stakeholders de maneira justa e imparcial. |
* **Referência:** *Apostila+Mod.+2.pdf e Apostila+Mod.+6.pdf (Seções de Compliance, Ética e Governança)*.
* **Cicatrizes / Troubleshooting:** Alucinava definições do IBGC (Instituto Brasileiro de Governança Corporativa). Foi necessário realizar uma engenharia de prompt agressiva repetindo `[Use apenas as definições exatas do texto]` no final do comando para forçar a fidelidade bibliográfica.

</details>

<details>
<summary><b>8. Qual é o papel da auditoria interna e o processo recomendado pós-auditoria?</b></summary>

* **Prompt Inicial (Fraco):** O que fazer depois de uma auditoria?
* **Prompt Otimizado (Engenharia de Prompt):** `[Dividir a Tarefa]` Com base no Módulo 6, explique a importância das melhorias pós-auditoria. Em seguida, liste os 4 passos sequenciais para garantir sua implementação.
* **Resposta Obtida:** A pós-auditoria serve para sanar problemas identificados e prevenir futuras deficiências. O processo exige: 1. Comunicação clara das recomendações; 2. Definição de planos de ação (prazos, responsáveis e recursos necessários); 3. Acompanhamento contínuo das implementações; 4. Prevenção ativa de novas falhas através das lições aprendidas.
* **Referência:** *Apostila+Mod.+6.pdf (Módulo 6: Seção 4. Auditoria Interna - Melhorias e Recomendações)*.
* **Cicatrizes / Troubleshooting:** O modelo pulava o detalhamento do plano de ação (prazos/recursos). Ajustou-se o prompt solicitando explicitamente o desdobramento de cada etapa.

</details>

<details>
<summary><b>9. Quem são os desenvolvedores/professores do curso e quais são as suas credenciais de mercado?</b></summary>

* **Prompt Inicial (Fraco):** Quem criou o curso?
* **Prompt Otimizado (Engenharia de Prompt):** `[Instruções]` Reúna as informações contidas nos arquivos "Introdução.docx" e "Quem somos.docx" e faça um resumo estruturado contendo o nome da instituição, o idealizador do projeto e a formação técnica da professora responsável.
* **Resposta Obtida:** O treinamento corporativo é desenvolvido pelo Centro de Educação Empresarial **Produtividade 360**, idealizado pelo Engenheiro **Paulo Ribeiro**. As aulas e mentorias são ministradas pela professora **Pâmela Cavalcanti**, graduada em Administração de Empresas e formada em Tecnologia da Administração, especialista em gestão financeira para empresários.
* **Referência:** *Introdução.docx e Quem somos.docx*.
* **Cicatrizes / Troubleshooting:** A IA ignorava as credenciais da professora Pâmela por estarem divididas entre dois arquivos separados. O cruzamento manual de fontes locais exigiu a técnica de *Few-Shot ou Agrupamento de Conteúdo Principal*.

</details>

<details>
<summary><b>10. Quais ferramentas ágeis e de diagnóstico de mercado o analista aprende a dominar além das finanças puras?</b></summary>

* **Prompt Inicial (Fraco):** O curso ensina outras coisas além de finanças?
* **Prompt Otimizado (Engenharia de Prompt):** `[Repetir Instruções no Final]` Localize no arquivo "Quem somos.docx" a lista de ferramentas de gestão que o estudante irá dominar ao longo do ecossistema da Produtividade 360. Forneça apenas a listagem nominal com a aplicação prática indicada no texto. `[Atenção: Não invente ferramentas fora do arquivo de texto]`.
* **Resposta Obtida:**
  * **5W2H:** Para organização prática de atividades;
  * **Análise Pessoal:** Para aprender a antecipar mudanças de mercado;
  * **Os 5 Porquês:** Método essencial para resolver problemas na raiz;
  * **Scrum:** Metodologia ágil para gestão eficaz de projetos;
  * **Análise SWOT:** Para diagnóstico e melhoria contínua do desempenho.
* **Referência:** *Quem somos.docx (Seção: Ferramentas de gestão que você vai dominar)*.
* **Cicatrizes / Troubleshooting:** O modelo insistia em adicionar o método *Kaizen* e as *5 Forças de Porter* devido ao seu treinamento prévio sobre administração. O uso do *Guardrail de Limitação* no final do prompt eliminou a alucinação.

</details>

---

[⬅️ Voltar ao README principal](../README.md)
