#  Eixo 2: Desenvolvimento de Software e Engenharia de Sistemas

## Questões

Excelente! Vamos criar uma questão desafiadora no estilo da banca FGV sobre Eixo 2 para o CNU Bloco 3. A FGV costuma mesclar conceitos, apresentar cenários e focar em aspectos práticos, trade-offs e complexidades da engenharia de software.

**Questão:**

Uma grande corporação, buscando modernizar sua infraestrutura tecnológica e aumentar a agilidade no desenvolvimento e deployment, decidiu migrar um sistema legada monolítico crítico para uma arquitetura baseada em microsserviços. A nova arquitetura foi concebida para permitir a escalabilidade independente dos componentes, a diversidade tecnológica por serviço e a resiliência a falhas isoladas.

Entretanto, após a implantação dos primeiros serviços em produção, as equipes de Engenharia de Sistemas e Desenvolvimento começaram a enfrentar desafios operacionais e de gerenciamento significativamente distintos daqueles vivenciados com o monólito.

Considerando o contexto da migração para microsserviços e as características inerentes de um sistema distribuído, qual dos seguintes aspectos representa um aumento substancial na complexidade de engenharia e operação, comparado a um sistema monolítico bem arquitetado, e exige a adoção de práticas e ferramentas específicas?

A) A gestão centralizada de banco de dados para garantir consistência transacional global entre os serviços, simplificando as operações de leitura e escrita.
B) A redução da necessidade de automação de infraestrutura e processos de Continuous Integration/Continuous Deployment (CI/CD), dada a independência entre os serviços.
C) O aumento da complexidade na implementação da observabilidade (monitoramento agregado de logs, métricas e tracing distribuído) e na orquestração de testes de integração e de ponta a ponta em um ambiente heterogêneo e dinâmico.
D) A simplificação da segurança das comunicações inter-serviços, pois a falha de autenticação ou autorização em um serviço não compromete a segurança dos demais.

---

**Resposta Correta:** C

**Justificativa:**

A alternativa **C** descreve um dos maiores desafios inerentes à arquitetura de microsserviços: a complexidade operacional e de observabilidade. Em um sistema monolítico, logs, métricas e rastreamentos de execução geralmente residem em um único processo ou em um número limitado de instâncias. Em um ambiente de microsserviços distribuído, as requisições de usuários transitam por múltiplos serviços independentes, cada um gerando seus próprios logs e métricas. Correlacionar esses dados para entender o fluxo completo de uma transação (tracing distribuído), monitorar a saúde geral do sistema e diagnosticar falhas torna-se exponencialmente mais complexo, exigindo ferramentas e práticas avançadas de observabilidade (como ELK Stack, Prometheus/Grafana, Jaeger/Zipkin). Da mesma forma, testar as interações entre múltiplos serviços independentes (testes de integração e de ponta a ponta) é consideravelmente mais difícil do que testar um sistema monolítico.

Analisando as demais alternativas:

*   **A) Incorreta.** Microsserviços geralmente promovem bancos de dados por serviço ou gestão de dados descentralizada. A garantia de consistência transacional global (equivalente a transações ACID em um monólito) em um ambiente distribuído é um problema complexo, geralmente resolvido com padrões como Saga, e não é simplificada pela arquitetura.
*   **B) Incorreta.** A independência dos serviços na arquitetura de microsserviços, ao contrário, *aumenta* a necessidade de automação robusta de infraestrutura e processos de CI/CD. Gerenciar o deployment, escalabilidade e monitoramento de dezenas ou centenas de serviços pequenos requer um alto grau de automação para ser eficiente e viável.
*   **D) Incorreta.** A segurança das comunicações inter-serviços (autenticação, autorização, criptografia mútua) é uma preocupação *aumentada* em arquiteturas distribuídas. Há mais pontos de entrada/saída e interações de rede para proteger. A falha de segurança em um serviço pode, sim, ter efeitos cascata ou ser um vetor de ataque para outros serviços se as medidas de segurança entre eles não forem rigorosas.

Portanto, a complexidade da observabilidade e dos testes de integração em um sistema distribuído são desafios cruciais e inerentes aos microsserviços, que representam um aumento significativo na carga de engenharia e operação.