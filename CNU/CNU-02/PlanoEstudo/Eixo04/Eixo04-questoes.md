#  EIXO 4: CIÊNCIA DE DADOS E INTELIGÊNCIA ARTIFICIAL

## Questões

Okay, vamos criar uma questão desafiadora no estilo da banca FGV sobre Ciência de Dados e Inteligência Artificial para o Bloco 3 - Tecnologia do CNU. A FGV gosta de cenários práticos, com múltiplos elementos e que exijam a aplicação de conceitos, não apenas a memorização de definições. Vamos focar em métricas de avaliação de modelos em dados desbalanceados, um tema comum e crucial.

---

**Especialista FGV On:** Entendido. Vamos elaborar uma questão que force o candidato a pensar na aplicabilidade das métricas de avaliação de modelos de Machine Learning em um contexto real com características desafiadoras, como dados assimétricos. A questão explorará a compreensão da relação entre objetivos de negócio e a escolha das métricas mais adequadas, algo típico das provas de tecnologia da FGV.

---

**Questão:**

Uma agência reguladora federal está avaliando dois modelos de aprendizado de máquina supervisionado desenvolvidos para identificar transações financeiras potencialmente fraudulentas em um vasto conjunto de dados históricos. O conjunto de dados apresenta uma severa assimetria, com casos de fraude (classe positiva) sendo significativamente menos frequentes (menos de 1%) que transações legítimas (classe negativa).

Após o treinamento e validação em conjuntos de teste independentes e representativos, as equipes de modelagem apresentaram as seguintes observações e métricas de desempenho para um limiar de classificação padrão (0.5):

*   **Modelo A:** Identifica a vasta maioria dos casos de fraude (alto Recall/Cobertura), mas gera um número considerável de alertas falsos (baixa Precisão).
    *   Métricas (aproximadas): Recall = 0.90; Precisão = 0.30; Acurácia = 0.98; F1-Score ≈ 0.45; AUC-ROC = 0.92.
*   **Modelo B:** Quando identifica um caso como fraude, é muito provável que seja realmente fraude (alta Precisão), mas deixa passar uma parte significativa dos casos reais (baixo Recall/Cobertura).
    *   Métricas (aproximadas): Recall = 0.50; Precisão = 0.70; Acurácia = 0.99; F1-Score ≈ 0.58; AUC-ROC = 0.91.

A agência estabeleceu como objetivo principal minimizar a perda financeira decorrente de *não identificar* casos de fraude, mesmo que isso implique em investigar um número maior de alertas que se revelem falsos positivos.

Considerando o objetivo estratégico da agência, as características do conjunto de dados e as métricas apresentadas, qual modelo seria o mais adequado para implementação inicial e qual a justificativa principal para essa escolha?

A) Modelo A, pois sua alta Acurácia e AUC-ROC superior indicam um desempenho geral mais confiável, especialmente em dados desbalanceados.
B) Modelo B, pois sua alta Precisão minimiza a quantidade de falsos positivos, otimizando os recursos de investigação da agência ao reduzir alertas desnecessários.
C) Modelo A, pois seu alto Recall (Cobertura) está alinhado com o objetivo de identificar a maior quantidade possível de casos de fraude, prioritário para minimizar as perdas por fraudes não detectadas.
D) Modelo B, pois seu F1-Score mais elevado e Acurácia ligeiramente superior demonstram um melhor equilíbrio entre Precisão e Recall, sendo mais robusto para a tarefa de detecção de fraude.

---

**Resposta Correta:** C

**Justificação:**

A questão apresenta um cenário clássico de trade-off entre Precisão e Recall em dados altamente desbalanceados. A Acurácia é uma métrica enganosa nesse contexto, pois um modelo que prevê majoritariamente a classe majoritária (não fraude) pode alcançar alta acurácia (ex: 99% se a fraude for 1% dos dados), mas ser inútil para detectar a classe minoritária. O F1-Score é útil por ser uma média harmônica que equilibra Precisão e Recall, mas a AUC-ROC mede a capacidade discriminatória do modelo em diferentes limiares.

No entanto, o fator decisivo é o *objetivo estratégico* da agência: "minimizar a perda financeira decorrente de *não identificar* casos de fraude". Este objetivo prioriza a detecção da classe positiva (fraude) sobre a precisão dos alertas, mesmo que isso gere mais falsos positivos. A métrica que reflete a capacidade de identificar corretamente a maior proporção possível dos casos positivos reais é o **Recall (ou Cobertura)**.

*   O **Modelo A** tem um Recall significativamente maior (0.90 vs 0.50), indicando que ele consegue detectar 90% dos casos de fraude, enquanto o Modelo B detecta apenas 50%.
*   Embora o Modelo A tenha menor Precisão (0.30 vs 0.70), o que significa que 70% de seus alertas são falsos positivos (1 - 0.30), isso está alinhado com a aceitação de "investigar um número maior de alertas" em prol do objetivo principal.

Portanto, o Modelo A é o mais adequado para o objetivo declarado, pois sua alta capacidade de detectar fraudes (alto Recall) é a prioridade estratégica, superando as desvantagens de sua menor Precisão. As opções que focam em Acurácia, F1-Score ou Prioridade da Precisão (minimizando falsos positivos) não se alinham com a prioridade explícita definida pela agência.