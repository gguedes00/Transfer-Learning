# Projeto de Transfer Learning para Classificação de Gatos vs Cachorros

## Descrição do Projeto
Este projeto aplica **Transfer Learning** usando o modelo MobileNetV2 para classificar imagens de gatos e cachorros. O objetivo é demonstrar como redes neurais pré-treinadas podem ser adaptadas para tarefas específicas com alto desempenho.

## Tecnologias Utilizadas
- **Linguagem**: Python
- **Bibliotecas**: TensorFlow, TensorFlow Datasets, Keras
- **Modelo Base**: MobileNetV2 (pré-treinado no ImageNet)
- **Ambiente**: Google Colab

## Dataset
- **Nome**: Microsoft Cats vs Dogs
- **Origem**: [Download via TensorFlow Datasets](https://www.tensorflow.org/datasets/catalog/cats_vs_dogs)
- **Detalhes**:
  - 23,262 imagens (11,631 de gatos e 11,631 de cachorros)
  - Split: 80% treino (18,610 imagens), 20% validação (4,652 imagens)

## Métricas de Desempenho
| Época | Acurácia (Treino) | Acurácia (Validação) |
|-------|-------------------|-----------------------|
| 1     | 95.93%            | 98.90%                |
| 2     | 98.81%            | 98.99%                |

## Como Executar
1. **Acesse o Notebook no Colab**:  
   [Clique aqui para abrir o notebook]([[https://colab.research.google.com/...](https://colab.research.google.com/github/gguedes00/Transfer-Learning/blob/main/desafio_Transfer_Learning.ipynb](https://colab.research.google.com/drive/1EyUpSQ93c_Dbytf9h64hJQ9ItbDs9jm7?usp=sharing)))

2. **Execute todas as células**:
   ```python
   Runtime > Run all
