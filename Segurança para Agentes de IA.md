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

### Estratégias de mitigação

Para reduzir esses riscos, adote uma abordagem de segurança por design que inclua:

* **Impondo controles de acesso baseados em função (RBAC)** e permissões de mínimos privilégios
* **Adicionando camadas de filtragem e validação de prompt** para evitar ataques de injeção
* **Isolamento ou bloqueio de operações sensíveis** atrás de aprovações com intervenção humana
* **Manter registro abrangente e rastreabilidade** para todas as ações do agente
* **Auditoria regular** de dependências e integrações de terceiros
* **Treinar e validar modelos continuamente** para detectar desvio de dados ou tentativas de envenenamento.

Ao inserir essas práticas no início do desenvolvimento, você pode implantar agentes de IA com segurança e confiança em ambientes do mundo real.
