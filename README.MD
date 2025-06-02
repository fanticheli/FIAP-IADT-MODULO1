# Previsão de Custos Médicos – Tech Challenge Fase 1

Olá! Seja bem-vindo(a) ao repositório do **Tech Challenge Fase 1**, onde embarcamos na jornada de criar um modelo de Machine Learning que **prevê custos médicos** para seguros de saúde. Aqui você vai encontrar tudo o que foi feito, desde a exploração dos dados até a avaliação final dos modelos. Vamos juntos nessa?

---

## 📖 Descrição do Projeto

- **O que estamos tentando fazer?**  
  Desenvolver um modelo que seja capaz de **prever o valor dos custos médicos** de uma pessoa, considerando características como idade, IMC, se fuma ou não, entre outras informações.

- **Por que isso é importante?**  
  Saber antecipadamente quanto alguém deve pagar ajuda seguradoras a precificar prêmios de forma justa, pacientes a planejar despesas e profissionais de saúde a entender perfis de risco.

- **Como fizemos isso?**  
  1. Geramos uma base sintética com 1.000 registros, incluindo colunas extras como “nível de atividade” e “nível de estresse” (para deixar o cenário mais realista).  
  2. Tratamos dados faltantes (caso houvesse) e transformamos variáveis de texto em números.  
  3. Escalonamos valores numéricos para manter tudo na mesma unidade de medida.  
  4. Testamos três modelos de regressão:
     - Regressão Linear (nossa “receita simples”)
     - Árvore de Decisão Regressora (regras de “perguntas” em árvore)
     - Random Forest Regressora (grupo de árvores trabalhando em conjunto)
  5. Comparamos métricas (MSE, RMSE e R²) para ver qual performou melhor.  
  6. Por fim, analisamos os resíduos.

Em resumo, nosso modelo final escolhido foi a **Regressão Linear**, pois apresentou R² de 0.91 e RMSE de 0.30, comprovando que é simples, estável e entrega ótimas previsões. 

---

## 📊 Resultados e Métricas

### 1. Resultados no Conjunto de Teste

| Modelo                     | MSE   | RMSE  | R²   |
|----------------------------|-------|-------|------|
| **Regressão Linear**       | 0.09  | 0.30  | 0.91 |
| **Árvore de Decisão**      | 0.18  | 0.42  | 0.82 |
| **Random Forest (básico)** | 0.14  | 0.37  | 0.86 |

- **Regressão Linear** foi a campeã, explicando 91% da variação dos custos e errando, em média, 0.30 no espaço normalizado.
- A **Árvore de Decisão** inicial ficou atrás (R² = 0.82), mostrando que uma única árvore rasa não capturou bem todas as nuances.
- O **Random Forest** melhou (R² = 0.86) mas não bateu a simplicidade e eficiência do modelo linear.

---

## 🧐 O Que Aprendemos e Nossas Conclusões

- **Regressão Linear** foi a escolha certa, pois foi **simples de entender**, **fácil de implementar** e **entregou alta precisão** (R² = 0.91).  
- Modelos de árvore tiveram desempenho inferior na configuração inicial, reforçando que, para esses dados, a relação é quase linear.  
- A análise de resíduos mostra que **nosso modelo não sofre overfitting** e generaliza bem para novos dados.  