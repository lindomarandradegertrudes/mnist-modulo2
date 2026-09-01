# [NOME DO SOFTWARE]

> Mini-Projeto Avaliativo — Módulo 2: Desenvolvimento de IA para Análise Preditiva
> Classificação multiclasse de dígitos manuscritos (MNIST)

## 1. Qual problema resolve?

<!-- TODO: 2-4 frases. Ex: reconhecer automaticamente dígitos de 0 a 9 escritos à mão,
     comparando algoritmos clássicos de ML com redes neurais, e avaliando robustez
     do modelo diante de dados que ele nunca viu. -->

## 2. Técnicas e tecnologias utilizadas

- **Linguagem:** Python 3
- **Dataset:** MNIST (`mnist_784`, 70.000 imagens 28x28 em escala de cinza) via `sklearn.datasets.fetch_openml`
- **Bibliotecas:** scikit-learn, NumPy, pandas, matplotlib, seaborn, Pillow, OpenCV
- **Modelos:** <!-- TODO: os 3 que você escolheu, ex: Random Forest, KNN, MLPClassifier -->
- **Avaliação:** matriz de confusão, accuracy, precision/recall/F1 ponderados (`classification_report`)

<!-- TODO: opcional — inserir um diagrama do pipeline (EDA -> pré-processamento -> treino -> avaliação -> testes de robustez) -->

## 3. Como executar

```bash
# 1. Clonar o repositório
git clone <URL_DO_SEU_REPO>
cd mnist-modulo2

# 2. Criar e ativar o ambiente virtual
py -3 -m venv .venv
.venv\Scripts\activate        # Windows
# source .venv/bin/activate   # Linux/Mac

# 3. Instalar dependências
pip install -r requirements.txt

# 4. Abrir o notebook
jupyter notebook mnist_modulo2.ipynb
# ou abrir a pasta no VSCode e rodar mnist_modulo2.ipynb
```

> As imagens manuscritas próprias (Desafio C) estão na pasta `data/`.
> O dataset MNIST é baixado automaticamente na primeira execução (fica em cache, não vai para o repositório).

## 4. Estrutura do repositório

```
mnist-modulo2/
├── data/                 # imagens manuscritas próprias (Desafio C)
├── mnist_modulo2.ipynb   # notebook com todas as Fases e Desafios
├── requirements.txt
├── .gitignore
└── README.md
```

## 5. Melhorias futuras

<!-- TODO: ex: usar CNN (TensorFlow/Keras) para explorar a estrutura espacial da imagem;
     data augmentation; tuning de hiperparâmetros com GridSearchCV; deploy como API. -->

## 6. Vídeo de demonstração

<!-- TODO: link do Google Drive (modo leitor para qualquer pessoa com o link) -->

## Autor

<!-- TODO: seu nome -->
