#   Eixo 3: Infraestrutura, Redes e Segurança da Informação

## Questões

Com certeza! Como um especialista na banca FGV, vou elaborar uma questão desafiadora sobre Infraestrutura, Redes e Segurança da Informação, focada no Bloco 3 - Tecnologia do CNU.

---

**Questão:**

Um Órgão Público Federal modernizou sua infraestrutura de TI, migrando serviços críticos, incluindo uma aplicação web que lida com dados sensíveis dos cidadãos, para um ambiente de nuvem pública. Nos últimos meses, o Órgão tem observado um aumento significativo em tentativas de ataques cibernéticos direcionados a essa aplicação, incluindo injeção de código SQL (SQL Injection), Cross-Site Scripting (XSS), ataques de força bruta contra credenciais e negação de serviço distribuída (DDoS).

Diante desse cenário e considerando as melhores práticas de segurança da informação em ambientes de nuvem para mitigar esses tipos de ameaças específicas, qual combinação de controles de segurança deve ser priorizada e implementada para proteger eficazmente a aplicação web pública?

A) Implementação de um IDS (Intrusion Detection System) baseado em rede e criptografia de dados em repouso nos bancos de dados.
B) Configuração de filtros de pacotes stateless na camada de rede e uso intensivo de VPNs para todos os acessos à aplicação.
C) Implantação de um WAF (Web Application Firewall) e contratação de serviço de mitigação de DDoS na nuvem, complementados por políticas rigorosas de controle de acesso e monitoramento contínuo.
D) Adoção de criptografia ponta-a-ponta em todas as comunicações externas e segmentação de rede por meio de VLANs no datacenter local.

---

**Resposta:** C

**Justificativa:**

A alternativa (C) apresenta a combinação de controles de segurança mais adequada e eficaz para mitigar os tipos de ataques mencionados no cenário, que são específicos de aplicações web e infraestrutura de nuvem:

*   **WAF (Web Application Firewall):** É fundamental para proteger contra ataques na camada de aplicação, como SQL Injection e XSS, inspecionando e filtrando o tráfego HTTP/HTTPS antes que ele chegue à aplicação web. Também pode ajudar a mitigar ataques de força bruta contra formulários de login.
*   **Serviço de Mitigação de DDoS:** Essencial para combater ataques de negação de serviço distribuída, que visam esgotar os recursos da aplicação ou da infraestrutura, impedindo o acesso de usuários legítimos. Em ambientes de nuvem, esses serviços geralmente são oferecidos pelo provedor de nuvem ou por CDNs especializados.
*   **Políticas rigorosas de controle de acesso e monitoramento contínuo:** Complementam as medidas de proteção perimetral e de aplicação. O controle de acesso limita quem pode acessar o quê, enquanto o monitoramento (via logs, SIEM, etc.) permite detectar atividades suspeitas, identificar falhas de segurança e responder rapidamente a incidentes.

As demais alternativas são menos eficazes ou inadequadas para o contexto e os ataques específicos descritos:

*   **(A)** IDS baseado em rede detecta intrusões, mas não necessariamente as impede ativamente (a menos que seja um IPS). A criptografia de dados em repouso protege os dados armazenados, mas não mitiga ataques contra a aplicação em execução (SQLi, XSS, DDoS) ou contra o acesso.
*   **(B)** Filtros de pacotes stateless são muito básicos e insuficientes para ataques na camada de aplicação (SQLi, XSS). O uso intensivo de VPNs é adequado para acesso remoto seguro ou comunicação entre redes privadas, mas não para tornar uma aplicação *pública* acessível de forma segura para cidadãos em geral.
*   **(D)** Criptografia ponta-a-ponta é importante para a confidencialidade da comunicação, mas não impede ataques de injeção de código, DDoS ou força bruta. A segmentação de rede por VLANs é uma boa prática, mas a alternativa a limita ao "datacenter local", o que é inconsistente com a migração para "ambiente de nuvem pública" mencionada no cenário como o alvo principal dos ataques.