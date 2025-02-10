# Classificação de Gatos vs Cães usando Transfer Learning 🐱🐶

![TensorFlow](https://img.shields.io/badge/TensorFlow-2.18.0-orange)
![Licença](https://img.shields.io/badge/Licen%C3%A7a-MIT-blue)
![DIO](https://img.shields.io/badge/Parceiro-DIO-000?style=flat&logo=data:image/png;base64,...)

Projeto de deep learning para classificação binária de imagens de gatos e cães usando **Transfer Learning** com MobileNetV2, alcançando mais de **98% de acurácia na validação**.

**Projeto desenvolvido como parte do bootcamp BairesDev - Machine Learning Practitioner da DIO.**

## 📌 Visão Geral
Este projeto demonstra como aproveitar modelos pré-treinados (MobileNetV2) para tarefas de classificação de imagens. Combinando transfer learning e fine-tuning, treinamos um modelo de alta precisão com recursos computacionais mínimos.

## ✨ Principais Recursos
- **Transfer Learning**: Utiliza o MobileNetV2 pré-treinado no ImageNet.
- **Fine-Tuning**: Descongela camadas profundas para adaptação à tarefa específica.
- **Pipeline Otimizado**: TensorFlow Datasets + Prefetching para carregamento eficiente de dados.
- **Visualização**: Métricas de treinamento/validação (curvas de acurácia e perda).
- **Exportação do Modelo**: Modelo salvo para deploy (`meu_modelo.keras`).

## 📦 Instalação
1. Clone o repositório:
   git clone https://github.com/gguedes00/Transfer-Learning
   
   ou acesse o link do colab:
   https://colab.research.google.com/drive/1EyUpSQ93c_Dbytf9h64hJQ9ItbDs9jm7?usp=sharing

   
Instale as dependências:

   pip install tensorflow tensorflow_datasets matplotlib numpy

🚀 Como Usar

1. Preparação do Dataset

Carrega o dataset cats_vs_dogs do TensorFlow Datasets.

Divide em 80% para treino e 20% para validação.

Pré-processa as imagens (redimensiona para 224x224, normaliza para o MobileNetV2).

3. Arquitetura do Modelo

base_model = tf.keras.applications.MobileNetV2(
    input_shape=(224, 224, 3),
    include_top=False,
    weights='imagenet'
)
base_model.trainable = False  # Congela camadas base

model = tf.keras.Sequential([
    base_model,
    layers.GlobalAveragePooling2D(),
    layers.Dense(1, activation='sigmoid')
])  


3. Treinamento
   
Fase 1 (Camadas Congeladas):

Treina o classificador sobre o MobileNetV2.

2 épocas, otimizador Adam, loss de entropia cruzada binária.

Resultado: ~98.8% de acurácia na validação.

Fase 2 (Fine-Tuning):

Descongela as últimas 54 camadas do MobileNetV2.

Treina com taxa de aprendizado reduzida (1e-5).

Resultado: ~98.5% de acurácia na validação.

4. Avaliação   

## Métricas de Desempenho
| Época | Acurácia (Treino) | Acurácia (Validação) |
|-------|-------------------|-----------------------|
| 1     | 95.93%            | 98.90%                |
| 2     | 98.81%            | 98.99%                |


📊 Resultados
Fase	Acurácia na Validação	Perda na Validação

Treino Inicial	98.88%	0.0341

Fine-Tuning	98.56%	0.0425

🔧 Melhorias Futuras

Aumentar o número de épocas no fine-tuning.

Adicionar aumento de dados (data augmentation: rotação, flip).

Testar outras arquiteturas (EfficientNet, ResNet).

Fazer deploy como API web usando Flask/TensorFlow Serving.

🤝 Contribuição

Contribuições são bem-vindas! Abra uma issue ou envie um pull request para:

Correções de bugs

Otimizações de desempenho

Novos recursos


📜 Licença

Licença MIT. Veja LICENSE para detalhes.

🙏 Agradecimentos

Equipes do TensorFlow e Keras pelo framework.

Google Research pelo MobileNetV2.

TensorFlow Datasets pelo dataset cats_vs_dogs.

**Equipe DIO pelo bootcamp.**

Contato: ggguedes00@gmail.com
GitHub: github.com/gguedes00

