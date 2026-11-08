# Session Handoff — dental-scheduling — 2026-11-08

> Última evidência de estado: terminal de 2026-10-30. Nada posterior foi verificado.

- **Phase / milestone:** Fase 1 (Descoberta), em andamento. Vision Document e ADR-001 feitos e na `develop`. Faltam casos de uso, regras de negócio, métrica de sucesso do MVP e os ADRs 002 a 005.

- **Completed (with evidence):**
  - Repositório público, `develop`, `.gitignore` Python (com `desktop.ini`), LICENSE MIT, README, About e topics → você reportou.
  - Ruleset `protect-main` ativo, sem bypass → JSON que você colou. Push direto na `main` recusado (`GH013`) → saída do terminal.
  - PR #1 (README e estrutura), PR #3 (ADR-001 e glossário), PR #8 (Vision), PR #9 (ajustes do Vision e ADR-001), todos mesclados com merge commit → links e `git log` que você mostrou.
  - Issue #2 (ADR-001) fechada → link que você enviou.
  - Diagnóstico de mudança acidental (quebra de linha no fim do arquivo) e `git restore` → diff que você colou.

- **Git state (last known):** branch `develop`, commit `61fc3f1` (merge do PR #9), igual ao `origin/develop`. Branch `docs/use-cases` e cartão em _In Progress_ só foram **sugeridos**, não confirmados.

- **Key decisions:**
  - ADR-001 (aceito, no repo): começar pelo domínio odontológico, modelo multi-tenant (`business_id`), repositório `dental-scheduling`.
  - Repositório público com MIT por ora. Reavaliar licença no ADR-003, **antes do primeiro código**.
  - n8n removido da stack (lembretes e e-mails via backend FastAPI).
  - Se o LLM cair: salvar a mensagem, avisar o dentista (e-mail sem dados sensíveis; painel depois) e só então confirmar ao paciente.
  - Cadastro progressivo: agenda com nome e telefone; depois, link seguro (token de uso único, com validade) para completar os dados. Aviso de privacidade já no primeiro contato.
  - A taxa de urgência é configurável por clínica e opcional.
  - Precificação fica para o final. Registrar consumo de tokens e de mensagens por clínica desde cedo.
  - A questão do Tribunal será tratada por você formalmente. Não é restrição do projeto.
  - LGPD: dentista ou clínica é controlador; você é operador; contrato e revisão jurídica necessários.
  - Atores: Patient, Prospective Patient, Dentist, Practice Owner, System Administrator; externos: WhatsApp e LLM.

- **Checks actually executed:** nenhum (ainda não há código). | **Pending on my side:** nenhum.

- **Open issues / blockers / questions:**
  - **Autenticação para cancelar ou remarcar:** minha recomendação é a opção C (só o telefone, com mitigações). **Você ainda não confirmou.**
  - **Métrica de impacto do MVP** (exigida na Fase 1) não está definida.
  - Issue #4 (Vision): fechamento não confirmado. Cartão no Project também.
  - README desatualizado: ainda lista o n8n e diz "web form on first contact".
  - ADRs 002 (conexão com o WhatsApp), 003 (licença), 004 (LGPD), 005 (resiliência do LLM) não escritos.
  - Glossário sem os termos: actor, use case, data minimization, threat model, graceful degradation, IDOR, upstream, controller/operator.
  - Automação com GitHub: **não funciona**. A extensão do Chrome não conectou e o push pela sessão foi recusado. Sua nova configuração de acesso não foi testada.

- **Impact question:** pendente. Que sinal indicaria que o MVP funcionou? (ex.: % de agendamentos fora do horário comercial, queda de faltas, tempo de resposta)

- **What I should be able to explain now:**
  1. Por que cada tarefa tem branch e PR, e a diferença entre merge commit, squash e fast-forward.
  2. Por que `Closes #N` não fecha a issue quando o PR vai para a `develop`.
  3. Controlador × operador na LGPD, e minimização de dados.
  4. Persistir primeiro e degradação graciosa.
  5. Threat model: por que SMS para o mesmo número não é segundo fator, e o que é IDOR e link com token.

- **Competency evidence earned (matrix):**
  - Git e GitHub (entrega): 4 ciclos completos branch, commits separados, PR, merge e sincronização; leu o diff e diagnosticou a mudança acidental.
  - Segurança: identificou sozinho o risco de exposição de localização pelo agendamento (nível júnior, incipiente).
  - Código, testes, operações, dados e IA: **sem evidência ainda**.

- **Authorship note:** README, ADR-001, Vision e glossário em inglês foram **escritos por mim (Tech Lead)** a partir das suas decisões, e **revisados e commitados por você**. As decisões e a lógica são suas.

- **Assumptions the next session must preserve:**
  - Preços de LLM e de WhatsApp, risco de banimento do Baileys e a restrição do n8n vêm de fontes secundárias ou da memória, **não foram verificados nas páginas oficiais**.
  - Pontos de LGPD precisam de revisão de especialista.
  - Regra de trabalho: textos em inglês, eu entrego pronto com tradução; lógica, você raciocina primeiro (socrático).

- **Next task + acceptance criteria:** rascunhar o **UC-01** (Prospective Patient agenda a primeira consulta), em português, pelo molde.
  - Fluxo principal numerado, com aviso de privacidade, nome e telefone, agendamento e envio do link.
  - Pelo menos 3 falhas ligadas ao número do passo (horário ocupado, dia sem atendimento, desistência) e a falha do LLM.

- **Current assistance mode (per topic):** Git/GitHub: Guided. Requisitos e casos de uso: Guided. Arquitetura e ADRs: Guided. LGPD e segurança: Guided. Sem evidências suficientes para subir de modo.
