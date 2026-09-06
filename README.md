# MNIST Digit Checker

> Mini-Projeto Avaliativo — Módulo 2: Desenvolvimento de IA para Análise Preditiva
> Pipeline de classificação multiclasse de dígitos manuscritos (MNIST)

## 1. Qual problema resolve?

Este projeto reconhece automaticamente dígitos manuscritos de 0 a 9. Ele treina e compara três modelos de aprendizado de máquina no dataset MNIST, avalia o desempenho de cada um com métricas multiclasse e, além disso, testa a **robustez** dos modelos em cenários adversos: classes ocultadas no treino, dados fora da distribuição (OOD) e imagens manuscritas digitalizadas pelo próprio autor.

## 2. Técnicas e tecnologias utilizadas

- **Linguagem:** Python 3.14;
- **Dataset:** MNIST (`mnist_784`, 70.000 imagens 28×28 em escala de cinza) via `sklearn.datasets.fetch_openml`;
- **Modelos:** Random Forest, KNN (K-Vizinhos Mais Próximos) e MLP (rede neural / Perceptron Multicamadas), todos do scikit-learn;
- **Pré-processamento:** divisão estratificada 70/10/20 (treino/validação/teste), normalização dos pixels para [0,1];
- **Avaliação:** matriz de confusão 10×10, acurácia, precisão, recall e F1 ponderados (`classification_report`);
- **Testes de robustez:** class masking, inferência OOD, pipeline de imagens reais com OpenCV/Pillow (Otsu, normalização de tamanho, centralização por centro de massa);
- **Bibliotecas:** scikit-learn, NumPy, pandas, matplotlib, seaborn, Pillow, OpenCV, SciPy.

## 3. Como executar

```bash
# 1. Clonar o repositório
git clone https://github.com/lindomarandradegertrudes/mnist-modulo2.git
cd mnist-modulo2

# 2. Criar e ativar o ambiente virtual
py -3 -m venv .venv
.venv\Scripts\activate          # Windows
# source .venv/bin/activate     # Linux/Mac

# 3. Instalar as dependências
pip install -r requirements.txt

# 4. Abrir o notebook
jupyter notebook mnist_modulo2.ipynb
# ou abrir a pasta no VSCode e executar mnist_modulo2.ipynb (kernel: .venv)
```

> O dataset MNIST é baixado automaticamente na primeira execução (fica em cache local, fora do repositório).
> As imagens manuscritas próprias usadas no Desafio C estão versionadas na pasta `data/`.

## 4. Estrutura do repositório

```
mnist-modulo2/
├── data/                 # imagens manuscritas próprias (Desafio C)
├── mnist_modulo2.ipynb   # notebook com todas as Fases e Desafios
├── requirements.txt
├── .gitignore
└── README.md
```

O notebook está segmentado em:

- **Fase 1** — Carregamento e Análise Exploratória (EDA);
- **Fase 2** — Pré-processamento e divisão dos dados;
- **Fase 3** — Treinamento dos 3 modelos (ajuste de 2 hiperparâmetros cada);
- **Fase 4** — Avaliação comparativa no conjunto de teste;
- **Fase 5** — Testes de robustez: (A) class masking, (B) inferência OOD, (C) dígitos manuscritos próprios.

## 5. Principais resultados

| Modelo        | Acurácia (teste MNIST) | Acertos em dígitos manuscritos próprios (9 amostras) |
|---------------|------------------------|------------------------------------------------------|
| MLP           |        ~97,8%          |                     8/9                              |
| Random Forest |        ~96,5%          |                     9/9                              |
| KNN           |        ~97,0%          |                     2/9                              |

A Random Forest, apesar da menor acurácia no teste MNIST, foi a mais robusta com dados reais.
O KNN, competitivo no teste, degradou fortemente fora da distribuição de treino.

## 6. Melhorias futuras

- Usar uma CNN (Rede Neural Convolucional) para aproveitar a estrutura espacial das imagens;
- Data augmentation (rotações, deslocamentos) para melhorar a generalização;
- Busca de hiperparâmetros mais ampla com `GridSearchCV` ou `RandomizedSearchCV`;
- Expor o melhor modelo como uma API para inferência.

## 7. Vídeo de demonstração

_(link do Google Drive — modo leitor para qualquer pessoa com o link — a ser incluído)_

## Autor

Lindomar Andrade Gertrudes
