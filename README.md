# Using Arguments to Assess Models’ Critical Thinking Skills

## Objective:

We propose different methods to classify, detect, and generate arguments using transformers. The project's main proposal is to evaluate the critical thinking skills of varied natural language processing models through a classification task on fallacy prediction and compare them. As a secondary task, we also analyze the models' capacity to generate counter-arguments by themselves, and detect fallacies within texts.

Demo: https://apps2.zuazo.org:4040/ (It can take some time to execute as inference is performed in CPU)

## Data
We have used two different datasets, which come from two papers:
-  Riposte! corpus (Reisert et al., 2019): Over 18,000 counter-arguments. It contains claims, premises, and counter-arguments for 4 different types of fallacies. Used in Tasks 1 and 3.
- Argument Mining CL2017 corpus (Habernal and Gurevych, 2017): 340 documents annotated with sequences of arguments. Used in task 2.

## Tasks

### Task 1

It categorizes the fallacy types found on a given claim and the premise. The Riposte dataset annotations have been converted to a multi-label corpus.

### Task 2

It detects arguments within the text by assigning to each token a tag. The available tags are O (other), B-ARG (beginning argument), and I-ARG (inside argument).

### Task 3
It gives one possible counter-argument using as information the claim, the fallacious premise, and the fallacy type.

## Results

| System                | Accuracy $\uparrow$ | Precision $\uparrow$ | Recall $\uparrow$ | F1-score $\uparrow$ | BLEU $\uparrow$ |
|-----------------------|---------------------|----------------------|------------------|-------------------|----------------|
| Glove¹ | 0.111              | 0.674               | 0.294            | 0.409            | -              |
| ELMo¹ | 0.104              | 0.667               | 0.290            | 0.405            | -              |
| Flair¹ | 0.111              | 0.674               | 0.294            | 0.409            | -              |
| bert-base-cased¹ | 0.629     | 0.642               | 0.629            | 0.633            | -              |
| bert-base-uncased¹ | 0.638    | 0.641               | 0.638            | 0.639            | -              |
| roberta-base¹ | 0.605         | 0.606               | 0.605            | 0.604            | -              |
| distilroberta-base¹ | 0.664  | 0.665               | 0.664            | 0.665            | -              |
| xlm-roberta-base¹| 0.605      | 0.606               | 0.605            | 0.604            | -              |
|-----------------------|---------|--------|---------|----------|--------|
| Glove² | 0.056             | 0.153               | 0.082            | 0.107            | -              |
| ELMo² | 0.600             | 0.719               | 0.783            | 0.750            | -              |
| Flair² | 0.517             | 0.664               | 0.701            | 0.682            | -              |
| bert-base-cased² | 0.914    | 0.634               | 0.761            | 0.692            | -              |
| bert-base-uncased² | 0.924   | 0.709               | 0.786            | 0.745            | -              |
| roberta-base²| 0.938        | 0.774               | 0.800            | 0.787            | -              |
| distilroberta-base²| 0.926  | 0.701               | 0.786            | 0.741            | -              |
| xlm-roberta-base² | 0.938     | 0.778               | 0.837            | 0.806            | -              |
|-----------------------|---------|--------|---------|----------|--------|
| T5³ | -                | -                   | -                | -                | 0.654           |


Note: ¹ means first task, ² means second task and ³ means third task
