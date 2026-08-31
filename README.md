# Detecção de Fraturas Ósseas com YOLO11

Projeto acadêmico desenvolvido no Google Colab para experimentação com **detecção de fraturas ósseas em imagens de raios X** utilizando o modelo **YOLO11**.

O trabalho envolveu preparação e análise do dataset, conversão de anotações, treinamento de diferentes configurações do modelo e avaliação dos resultados.

## Tecnologias

* **Python**
* **YOLO11 / Ultralytics**
* **OpenCV**
* **PyTorch**
* **NumPy**
* **Matplotlib**
* **PyYAML**
* **Google Colab**

## Etapas do projeto

### Preparação dos dados

* Download e organização do dataset.
* Conversão de anotações poligonais para **bounding boxes no formato YOLO**.
* Verificação visual das anotações.
* Análise da quantidade de imagens anotadas e imagens de background.
* Análise da distribuição das classes.
* Remoção de uma classe com quantidade insuficiente de exemplos e remapeamento das classes restantes.

### Treinamento

O modelo utilizado como base foi o **YOLO11n**, treinado com diferentes configurações e estratégias de data augmentation.

Entre os experimentos realizados estão variações envolvendo quantidade de épocas, parâmetros de otimização e técnicas de augmentation, além de testes com e sem imagens de background.

### Avaliação

Os modelos foram avaliados no conjunto de teste utilizando as métricas disponibilizadas pelo Ultralytics, além de:

* análise da matriz de confusão;
* comparação entre resultados de diferentes experimentos;
* visualização das predições do modelo;
* análise de falsos positivos e falsos negativos;
* análise de overfitting durante o treinamento.

## Resultados e observações

Os experimentos indicaram que a redução da loss no conjunto de treinamento não foi acompanhada pela mesma evolução na validação, sugerindo **overfitting** nos modelos testados.

Também foram observadas maiores dificuldades de classificação em determinadas regiões anatômicas e confusões entre classes, especialmente relacionadas à região das mãos.

As conclusões completas e os resultados experimentais podem ser consultados no material acadêmico incluído no repositório.

## Estrutura

```text
.
├── Bone_Fracture_Detection.py
├── README.md
└── ...
```

## Como executar

O projeto foi desenvolvido originalmente no **Google Colab**. O código disponível no repositório é uma exportação do notebook para Python.

Para reproduzir os experimentos, é necessário disponibilizar o dataset utilizado e adaptar os caminhos dos arquivos, que originalmente apontavam para o ambiente `/content` do Google Colab.

As principais dependências podem ser instaladas com:

```bash
pip install ultralytics opencv-python matplotlib torch numpy pyyaml
```

O dataset utilizado está disponível no Kaggle:

https://www.kaggle.com/datasets/pkdarabi/bone-fracture-detection-computer-vision-project

## Contexto acadêmico

Projeto desenvolvido durante a graduação em **Ciência da Computação**, com foco na aplicação de técnicas de **visão computacional e detecção de objetos** utilizando redes da família YOLO.

O trabalho envolveu preparação de dados, experimentação com modelos de deep learning, avaliação quantitativa e análise dos resultados.

## Licença

Consulte o arquivo `LICENSE` para informações sobre a licença do projeto.
