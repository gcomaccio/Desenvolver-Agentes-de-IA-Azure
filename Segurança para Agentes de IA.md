# Segurança para Agentes de IA

À medida que os agentes de IA se tornam mais autônomos e integrados aos sistemas, eles introduzem considerações de segurança além de ameaças tradicionais do aplicativo.

Os principais riscos de segurança incluem:

| Área de Risco | Descrição | Impacto de exemplo |
| :--- | :--- | :--- |
| **Vazamento de dados e exposição à privacidade** | Os agentes geralmente acessam dados comerciais ou de usuário confidenciais. Sem controles adequados, eles podem expor informações confidenciais sem querer. | Um agente que resume arquivos internos acidentalmente inclui dados privados em respostas voltadas para o cliente. |
| **Ataques de injeção e manipulação de comandos** | Usuários mal-intencionados criam entradas que substituem o comportamento pretendido de um agente, enganando-o para revelar dados ou executar ações não autorizadas. | Instruções ocultas em uma mensagem fazem com que o agente vaze as credenciais do sistema. |
| **Acesso não autorizado e escalonamento de privilégios** | Controles de autenticação ou de acesso fracos permitem que agentes ou maus atores acessem sistemas que não deveriam acessar. | Um agente conectado a uma ferramenta CRM executa ações no nível do administrador, como exportar ou excluir registros. |
| **Envenenamento por dados** | Os invasores corrompem o treinamento ou os dados contextuais, fazendo com que os agentes tomem decisões tendenciosas, incorretas ou não seguras. | Um conjunto de dados envenenado faz com que um agente de suporte ao cliente recomende conteúdo prejudicial. |
| **Vulnerabilidades da cadeia de suprimentos** | Os agentes dependem de APIs externas, plugins ou endpoints de modelo, expandindo a superfície de ataques. | Um plug-in de terceiros comprometido injeta código mal-intencionado no fluxo de trabalho do agente. |
| **Dependência excessiva de ações autônomas** | Agentes altamente autônomos poderão executar ações não intencionais se não forem cuidadosamente restringidos ou validados. | Um agente envia pagamentos por engano ou publica conteúdo não verificado. |
| **Auditabilidade e registro em log inadequados** | Sem registro em log detalhado, é difícil rastrear ações ou detectar comportamento mal-intencionado antecipadamente. | As equipes de segurança não podem identificar o uso indevido de dados devido a logs de atividade ausentes. |
| **Inversão de modelo e vazamento de saída** | Os invasores podem explorar resultados do modelo para inferir dados confidenciais usados durante o treinamento ou indução. | Consultas repetidas extraem informações privadas de um conjunto de dados de ajuste fino. |

---

### Detalhamento dos Riscos e Recomendações de Mitigação

#### 1. Vazamento de dados e exposição à privacidade
* **Mitigação:** Implemente filtragem rigorosa de saídas, mascaramento de dados (DLP - Data Loss Prevention) e políticas de menor privilégio (Least Privilege) para os dados que o agente tem permissão de acessar.

#### 2. Ataques de injeção e manipulação de comandos (Prompt Injection)
* **Mitigação:** Trate todas as entradas de usuários e sistemas externos como não confiáveis. Utilize delimitadores rígidos, validadores de prompt e camadas de firewall de IA (como Azure AI Content Safety).

#### 3. Acesso não autorizado e escalonamento de privilégios
* **Mitigação:** Use autenticação robusta (OAuth 2.0 / Entra ID), controle de acesso baseado em função (RBAC) e limite o escopo de execução dos agentes nos sistemas integrados.

#### 4. Envenenamento por dados (Data Poisoning)
* **Mitigação:** Realize sanitização contínua de bases de dados de RAG e conjuntos de ajuste fino (fine-tuning), assegurando a integridade e proveniência dos dados.

#### 5. Vulnerabilidades da cadeia de suprimentos
* **Mitigação:** Audite e restrinja plugins, bibliotecas de terceiros e APIs externas utilizadas pelos agentes, mantendo dependências sempre verificadas e assinadas.

#### 6. Dependência excessiva de ações autônomas
* **Mitigação:** Implemente fluxos *Human-in-the-loop* (HITL) para ações de alto impacto (ex.: pagamentos, exclusões e publicações públicas) e limites de taxa de execução.

#### 7. Auditabilidade e registro em log inadequados
* **Mitigação:** Habilite telemetria centralizada, logs detalhados de prompt-resposta, rastreamento distribuído (tracing) e monitoramento contínuo de anomalias.

#### 8. Inversão de modelo e vazamento de saída
* **Mitigação:** Limite o número de requisições por usuário (rate limiting), evite expor logit/probabilidades brutas e utilize técnicas de privacidade diferencial quando aplicável.
