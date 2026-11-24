# FEP → AGI — Plano de curso (formato-curso-v5)

> **Tese do curso:** o prompt não morreu. Ele deixou de ser o programa inteiro e virou o briefing.
> **Frase-âncora do curso:** *Antes você promptava a tarefa. Agora você orienta o agente.*

**Status (2026-09-07):** curso escrito, publicado em https://linnoff88-dev.github.io/ e catalogado no portal. O usuário aprovou a intenção e as 9 aulas e pediu para seguir sem responder o Passo 0; as respostas de descoberta foram **derivadas** deste plano e registradas no comentário do `<head>` do `curso.html` (público, quatro profissões, tempo, plataforma neutra), onde podem ser vetadas ou ajustadas. Os itens marcados `[pendente]` na §3 e as decisões da §7 foram resolvidos dessa forma.

---

## 1. O que este curso é (e o que ele não é)

É a **trilha-mapa** que amarra cinco cursos ARCKHÉ já publicados numa única linha de evolução, com uma aula por degrau, e aponta para cada curso como aprofundamento:

| Era (espinha) | Curso-fonte já publicado | O que este curso pega de lá |
|---|---|---|
| Era 1 · Prompt Engineering — "como pedir melhor" | **FEP** (Iniciante → Técnico → Masterclass) | anatomia do prompt, clareza, papéis, exemplos, iteração |
| Era 2 · Context Engineering — "que informação entregar" | **FEP2** (trilha 1: janela de contexto, lost-in-the-middle, chunking) + **Arq. Intenção** Pilar 1 | contexto como matéria-prima; onde a IA "esquece" |
| Era 2½ · Técnicas avançadas de raciocínio | **FEP2** (trilha 2: CoT, scaffolding, self-consistency; trilha 3: meta prompting, workflow) | o auge do micro-prompting: por que funcionou e por que cansou |
| Era 3 · Skill Engineering — "que capacidades reutilizáveis" | **lacuna no catálogo** (só FEP Masterclass 2 cobre, e para devs) | manual operacional reutilizável |
| Intenção acima do prompt | **Arquitetura de Intenção** (4 dias: Pirâmide, 5 Pilares, Sistema, Virada) + versão JARVIS | intenção → objetivo → prompt; Ficha de Intenção |
| Era 4 · Agent Engineering — "como fazer o agente trabalhar" | **agi-pratica** (Super-Agentes, 8 aulas) | tools, memória, permissões, evals |
| Era 5 · Orchestration — "coordenar agentes, ferramentas e humanos" | **agi-pratica** aula 8 (empresa agêntica) + **aiosagi** | o humano no ponto de decisão |
| AGI · a virada de set/2026 | **agi-ready** (6 aulas) + **Arq. Intenção Dia 4** (Fable 5.1 / GPT-6 Astra) | modelos que operam na intenção; engenharia por subtração |

Não é: uma reescrita do FEP, nem um curso de agentes (isso é agi-pratica), nem um curso de Arquitetura de Intenção (já existe). É o **fio** entre eles.

## 2. As duas figuras recorrentes (registro diagrama-de-mecanismo, trilho)

1. **A escada das 5 eras** — Prompt → Contexto → Skill → Agente → Orquestração. Aparece em todas as aulas com o degrau atual aceso. É o "onde estou" do aluno.
2. **A pilha do agente** — Intenção → Objetivo → Prompt → Skill → Contexto + Memória → Agente → Ferramentas → Ações → Evals/Supervisão → Resultado. Cresce camada a camada da aula 2 à aula 7.

Cold-open de cada aula usa **metáfora do mundo real** distinta (lista na §4), nunca a escada nem a pilha.

## 3. Público e metadados (a preencher no Passo 0)

| Campo | Valor |
|---|---|
| Público específico | **[pendente]** — hipótese: profissional 40+, não-programador, já usa IA de chat no trabalho |
| Profissões-alvo (≥2) | **[pendente]** |
| Familiaridade com tecnologia | **[pendente]** |
| Resultado prático esperado | **[pendente]** — hipótese: sair sabendo escrever um briefing de intenção e um esboço de skill para uma responsabilidade real do próprio setor |
| Tempo por sessão | **[pendente]** — hipótese: 20 min |
| Plataforma dos exemplos | neutra: ChatGPT (`/skills`) e Claude (Skills/Projects) lado a lado — **confirmar** |

## 4. Trilha — 9 aulas

Legenda: **tipo** = `data-kind` · **prática** = `data-mode` (nunca `codigo`) · **tempo** = `data-tempo` estimado, arredondado para cima.

### Aula 1 — Não é o fim do prompt. É o fim do micro-prompting.
- **Kicker:** Bloco 1 · A tese
- **Promessa:** Ao fim desta aula você consegue pegar um pedido seu real à IA, escrito passo a passo, e reescrevê-lo como destino (o que quero que aconteça, o que importa, o que não pode acontecer, o que é um bom resultado).
- **Tipo:** FUNDAMENTO · **Prática:** `prompt` (12 min) · **Tempo:** 22 min
- **Núcleo:** 2023–2025 programávamos a IA em linguagem natural · o que morre é o A→B→C→D · o prompt sobe de nível: de "como fazer" para "o que quero que aconteça" · o humano continua dono de objetivo, restrições, recursos e critério de bom · prompt é briefing, não programa.
- **Metáfora (cold-open):** o bilhete na porta da geladeira que virou lista de instruções de três páginas para quem ficou cuidando da casa.
- **Fonte de aprofundamento:** FEP nível Iniciante (anatomia, clareza) e FEP2 (o auge do micro-prompting).
- **Artefato da prática:** "tradução" de um micro-prompt do próprio aluno em orientação de 5 linhas, comparada à resposta da IA nas duas versões.
- **Gancho:** na aula 2 você vê por que o micro-prompting funcionou tão bem por dois anos, e onde ele quebra.

### Aula 2 — Era 1: quando pedir melhor era o trabalho inteiro
- **Kicker:** Era 1 · Prompt Engineering
- **Promessa:** Ao fim desta aula você consegue reconhecer, num prompt qualquer, as quatro peças que o FEP ensinou (papel, contexto, tarefa, formato) e dizer qual delas ainda vale e qual o agente já cobre sozinho.
- **Tipo:** FUNDAMENTO · **Prática:** `analise` (10 min, com gabarito em `<details>`) · **Tempo:** 20 min
- **Núcleo:** o que o FEP resolveu (ambiguidade, tom, formato, exemplos) · o que continua valendo (clareza, restrições, critério) · o que virou trabalho do agente (sequência de passos, pesquisa, formatação) · o custo escondido: prompts gigantes que ninguém mantinha.
- **Metáfora:** a receita de bolo da avó, escrita para quem nunca entrou numa cozinha, ao lado da receita para quem já cozinha.
- **Fonte:** FEP Iniciante e Técnico (Zero/Few-shot, Role Prompting, Templates, Refinamento Iterativo).
- **Artefato:** dois prompts do banco do FEP marcados com "ainda vale / o agente cobre".
- **Gancho:** aula 3 mostra que, quando o prompt ficou bom, o problema mudou de lugar: para o que a IA sabia ou não sabia.

### Aula 3 — Era 2: a informação certa vale mais que a instrução perfeita
- **Kicker:** Era 2 · Context Engineering
- **Promessa:** Ao fim desta aula você consegue listar, para uma tarefa do seu setor, o que a IA precisa saber antes de começar (empresa, cliente, histórico, políticas, decisões anteriores) e separar o que ela já tem do que você precisa entregar.
- **Tipo:** FUNDAMENTO · **Prática:** `tarefa` (12 min) · **Tempo:** 22 min
- **Núcleo:** contexto é matéria-prima, não decoração · a janela de contexto tem tamanho (analogia: a mesa de trabalho) · a IA esquece o meio (lost in the middle) · contexto que cansa a IA · o que muda quando o contexto passa a viver fora do prompt (projetos, arquivos, memória).
- **Metáfora:** o novo funcionário no primeiro dia: ninguém dá a ele um roteiro de fala, dá a pasta do cliente.
- **Fonte:** FEP2 trilha 1 (Context Windows, Lost in the Middle, Chunking) e Arq. Intenção Pilar 1 (Contexto).
- **Artefato:** ficha "o que a IA precisa saber" de uma responsabilidade real, em 5 linhas (empresa, produto, cliente, regra, decisão anterior).
- **Gancho:** aula 4 responde à pergunta que fica: "e eu vou digitar isso toda vez?". Não. É aí que nasce a skill.

### Aula 4 — Era 3: skill é o manual da casa, prompt é o pedido do dia
- **Kicker:** Era 3 · Skill Engineering
- **Promessa:** Ao fim desta aula você consegue distinguir prompt de skill em qualquer pedido e esboçar, numa página, a primeira skill do seu setor (quando usar, passos, modelo, checklist final).
- **Tipo:** FUNDAMENTO · **Prática:** `prompt` (15 min) · **Tempo:** 25 min
- **Núcleo:** prompt = orientação da situação; skill = procedimento reutilizável · o exemplo da proposta para o cliente: o pedido é uma frase, o manual comercial é a skill · prompt e skill não competem, se somam · anatomia de uma skill (instruções, referências, modelos, checklist) · onde isso mora hoje: ChatGPT `/skills`, Claude Skills e Projects, ou simplesmente um documento que você cola.
- **Metáfora:** o caderno de procedimentos do balcão da farmácia: quem chega novo lê e atende igual ao dono.
- **Fonte:** FEP Masterclass 2 (Claude Skills, arquitetura modular), traduzido para leigo.
- **Artefato:** skill de uma página para uma classe de trabalho repetida (ex.: "responder orçamento", "relatório semanal"), testada num chat de IA junto com um pedido curto.
- **Gancho:** aula 5 sobe um degrau: antes do prompt e da skill existe a intenção, e é ela que decide se tudo o resto faz sentido.

### Aula 5 — Acima do prompt: intenção, objetivo, e só então o pedido
- **Kicker:** A hierarquia · Intenção → Objetivo → Prompt → Skill
- **Promessa:** Ao fim desta aula você consegue escrever, para um problema real do seu setor, os quatro níveis (por quê, o quê, orientação da execução, skill) em quatro frases e apontar qual dos quatro estava faltando nos seus pedidos até hoje.
- **Tipo:** FUNDAMENTO · **Prática:** `tarefa` (12 min) · **Tempo:** 22 min
- **Núcleo:** os 4 níveis com o exemplo da conversão do curso · por que a maioria começa no nível 3 e se frustra · os 5 pilares da Arquitetura de Intenção como checagem (contexto, objetivos, regras, memória, validação) · "quanto melhor o agente, menos você ensina o caminho e mais explica o destino".
- **Metáfora:** o arquiteto e o mestre de obras: o dono da casa não diz onde vai cada tijolo, diz como quer viver.
- **Fonte:** Arquitetura de Intenção Dias 1–3 (Pirâmide, 5 Pilares, Ficha de Intenção v1) e versão JARVIS Dia 3.
- **Artefato:** os 4 níveis escritos para uma dor real, com o nível ausente marcado.
- **Gancho:** aula 6 dá mãos, memória e limites a essa intenção: o agente.

### Aula 6 — Era 4: o agente junta tudo e sai para trabalhar
- **Kicker:** Era 4 · Agent Engineering
- **Promessa:** Ao fim desta aula você consegue nomear, para uma responsabilidade do seu setor, as quatro camadas que o agente precisa além do prompt (ferramentas, memória, permissões, critério de avaliação) e dizer qual delas você ainda não confiaria a ele.
- **Tipo:** FERRAMENTA · **Prática:** `analise` (10 min) · **Tempo:** 20 min
- **Núcleo:** PROMPT + SKILLS + CONTEXTO + TOOLS + MEMÓRIA · tools são as mãos (navegador, e-mail, agenda, planilha) · memória é a experiência acumulada · permissões e aprovação humana: poderoso não basta, tem que ser controlável · evals são o controle de qualidade · o exemplo "faça o lançamento do meu curso" e as cinco skills que ele dispara.
- **Metáfora:** o diretor de marketing recém-contratado: você não diz "abra o Chrome", diz "quero 30% a mais de matrículas".
- **Fonte:** agi-pratica aulas 2–6 (ficha do agente, mãos, matriz de autonomia, ficha de confiança). **Esta aula aponta, não reensina.**
- **Artefato:** análise da pilha completa de um caso pronto (o lançamento do curso), marcando onde o aluno colocaria aprovação humana.
- **Gancho:** aula 7 mostra o que acontece quando não é um agente, são cinco, e você vira o ponto de decisão.

### Aula 7 — Era 5: quando o trabalho vira coordenar, não executar
- **Kicker:** Era 5 · Orchestration
- **Promessa:** Ao fim desta aula você consegue desenhar, numa página, quem faz o quê quando várias IAs, ferramentas e pessoas dividem uma responsabilidade do seu setor, e marcar os dois pontos em que um humano decide.
- **Tipo:** PRÁTICA/INTEGRAÇÃO · **Prática:** `tarefa` (15 min) · **Tempo:** 25 min
- **Núcleo:** a arquitetura completa Humano → Intenção → Prompt → Skills → Contexto + Memória → Agente → Ferramentas → Ações → Evals → Resultado · o que sobe de valor no humano (definir destino, julgar resultado, corrigir o agente) · o que desce · orquestrar não é automatizar tudo, é decidir onde a pessoa fica.
- **Metáfora:** a cozinha de restaurante no sábado à noite: o chef não frita nada, prova e devolve o prato.
- **Fonte:** agi-pratica aulas 7–8 (dirigir cinco agentes, empresa agêntica) e aiosagi (sistema operacional de agentes).
- **Artefato:** mapa de orquestração de uma página com dois pontos de decisão humana marcados.
- **Gancho:** aula 8 explica por que tudo isso ficou possível de uma vez só em setembro de 2026.

### Aula 8 — A virada: modelos que operam na intenção, não no passo
- **Kicker:** AGI · O que mudou em setembro de 2026
- **Promessa:** Ao fim desta aula você consegue explicar a um colega, em três frases e sem exagero, o que os modelos de setembro de 2026 fazem de diferente, e aplicar a "engenharia por subtração" num prompt seu, cortando as muletas que hoje atrapalham.
- **Tipo:** FUNDAMENTO · **Prática:** `prompt` (12 min) · **Tempo:** 22 min
- **Núcleo:** mesma tarefa, duas gerações (antes e depois) · o modelo passou a pedir menos caminho e mais fronteira · engenharia por subtração: o que tirar do prompt · fronteiras, não passos · definição de pronto e evidência · **limites reais**: onde o modelo ainda erra com confiança, o que não delegar (sem hype de "AGI resolve tudo").
- **Metáfora:** o estagiário que virou sócio: as mesmas instruções que o ajudavam no primeiro mês hoje o atrapalham.
- **Fonte:** Arq. Intenção Dia 4 (Fable 5.1 / GPT-6 Astra, subtração, Ficha de Intenção v2) e agi-ready aulas 1–2.
- **Artefato:** um prompt antigo do aluno auditado por subtração, com as linhas cortadas justificadas.
- **Gancho:** aula 9 fecha com a pergunta prática: em que era você e o seu setor estão, e qual é o próximo degrau.

### Aula 9 — Em que era você está, e qual é o próximo degrau
- **Kicker:** Fecho · Autodiagnóstico e plano de 30 dias
- **Promessa:** Ao fim desta aula você consegue situar você e o seu setor na escada das 5 eras, escolher um único degrau a subir nos próximos 30 dias e escrever o briefing de intenção que abre esse degrau.
- **Tipo:** PRÁTICA/INTEGRAÇÃO · **Prática:** `tarefa` (15 min) · **Tempo:** 25 min
- **Núcleo:** os sinais de cada era no dia a dia (como reconhecer em que degrau alguém trabalha) · os erros de pular degrau (querer orquestrar sem contexto) · o que continua humano em qualquer era · o mapa de aprofundamento: qual curso ARCKHÉ cobre o degrau que você escolheu.
- **Metáfora:** o check-up anual: não muda a idade, muda o que você faz no próximo ano.
- **Fonte:** costura de todos os anteriores; envio para FEP, FEP2, Arq. Intenção, agi-ready, agi-pratica conforme o degrau escolhido.
- **Artefato:** "escada aplicada ao meu setor" com o degrau atual, o próximo, e o briefing de intenção de 5 linhas para os 30 dias.
- **Gancho de trilha:** o painel de jornada mostra as nove promessas cumpridas e o curso-destino do próximo degrau.

## 5. Dosagem e cobertura (resumo para o portão v5)

| Aula | Tipo | Teste-se | Quadros previstos (pool ≤5) | Prática |
|---|---|---|---|---|
| 1 | FUNDAMENTO | obrigatório | `.qanchor` (frase do curso), `.qbefore-after` (micro-prompt vs orientação), cartões | prompt |
| 2 | FUNDAMENTO | obrigatório | `.qanchor`, `.qerr` (prompt gigante ninguém mantém), cartões | analise |
| 3 | FUNDAMENTO | obrigatório | `.qanchor`, `.qapply` (≥2 profissões), cartões | tarefa |
| 4 | FUNDAMENTO | obrigatório | `.qanchor`, `.qsteps` (anatomia da skill), `.qerr` (skill que é só prompt longo), cartões | prompt |
| 5 | FUNDAMENTO | obrigatório | `.qanchor`, `.qbefore-after` (nível 3 só vs 4 níveis), cartões | tarefa |
| 6 | FERRAMENTA | N/A | `.qerr` (agente poderoso sem freio), `.qsteps` (as 4 camadas), `.qapply` | analise |
| 7 | PRÁTICA/INTEGRAÇÃO | N/A | `.qsteps` (mapa de orquestração), mini-caso integrador, `.qbefore-after` | tarefa |
| 8 | FUNDAMENTO | obrigatório | `.qanchor`, `.qerr` (muleta que virou obstáculo), `.qbefore-after` (duas gerações), cartões | prompt |
| 9 | PRÁTICA/INTEGRAÇÃO | N/A | `.qsteps` (plano de 30 dias), mini-caso integrador, `.qapply` | tarefa |

Tempo total estimado: 203 min (3h23) em 9 sessões de 20 a 25 min. Nenhuma prática usa terminal, arquivo de configuração ou código. Todo termo da lista-sentinela (API, servidor, script, instalar…) que aparecer na aula 6 e 7 entra com analogia ou é eliminado.

## 6. Anti-clone (contra agi-ready e agi-pratica, gerados hoje)

Os dois cursos de hoje já entregaram: carta de delegação, ficha do agente em 5 blocos, matriz de autonomia em 4 faixas, ficha de confiança, simulação com cinco agentes, empresa agêntica. Este curso **não repete nenhum desses artefatos** e aponta para eles nas aulas 6 e 7.

O que este curso entrega de novo: tradução micro-prompt → orientação (aula 1), marcação "ainda vale / o agente cobre" (aula 2), ficha "o que a IA precisa saber" (aula 3), **skill de uma página** (aula 4, único artefato do catálogo sobre skills para leigo), os 4 níveis em 4 frases (aula 5), auditoria por subtração (aula 8), escada aplicada ao setor com plano de 30 dias (aula 9).

Metáforas de cold-open deste plano (bilhete na geladeira, receita da avó, pasta do cliente, caderno do balcão, arquiteto e mestre de obras, diretor recém-contratado, cozinha de sábado, estagiário que virou sócio, check-up) não coincidem com as dos dois cursos de hoje. Ordem dos quadros opcionais varia aula a aula (tabela §5).

## 7. Decisões em aberto (respondidas pelo usuário antes de escrever)

1. As cinco perguntas do protocolo de descoberta (§3).
2. Plataforma dos exemplos: neutra (ChatGPT e Claude lado a lado) ou só uma.
3. Manter 9 aulas ou cortar para 7 (candidatas a fusão: 2+3 numa só "Eras 1 e 2"; 6+7 numa só "agente e orquestração").
4. Nome do curso e do repo: pasta é `FEP-AGI`, logo o repo seria `linnoff88-dev/FEP-AGI`. Título provisório: **"FEP → AGI: do prompt à intenção"**.
