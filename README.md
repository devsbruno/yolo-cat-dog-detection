# YOLO Cat & Dog Detection

Este repositório contém um código para treinar um modelo YOLO (You Only Look Once) para detectar gatos e cachorros usando transferência de aprendizado no Google Colab.

## 📌 Requisitos

- Conta no Google Drive para armazenar os arquivos
- Google Colab
- Conexão com a internet

## 🔧 Configuração e Treinamento

1. Clone este repositório ou copie o código para seu ambiente Colab.
2. Monte o Google Drive para armazenar os arquivos de configuração e pesos do modelo.
3. Baixe e compile o Darknet, ativando GPU e OpenCV para melhor desempenho.
4. Configure o modelo YOLO para detectar duas classes: **gato** e **cachorro**.
5. Utilize o conjunto de dados COCO para treinamento.
6. Inicie o treinamento do modelo no Colab.

## 📂 Estrutura de Arquivos

```
📂 yolo-cat-dog-detection
 ├── darknet/                  # Repositório Darknet clonado
 ├── data/                      
 │   ├── train.txt              # Lista de imagens de treino
 │   ├── val.txt                # Lista de imagens de validação
 │   ├── custom.names           # Classes: gato e cachorro
 │   ├── custom.data            # Configuração dos dados
 ├── cfg/
 │   ├── yolov4_custom.cfg      # Configuração do modelo personalizado
 ├── backup/                    # Pesos do modelo treinado
 ├── yolo_cat_dog_training.ipynb # Notebook do Colab
 ├── README.md                  # Este arquivo
```

## 📸 Testando o Modelo

Após o treinamento, o usuário pode fazer upload de uma imagem para que o modelo detecte gatos e cachorros:

```python
from google.colab import files
uploaded = files.upload()
image_path = list(uploaded.keys())[0]

!./darknet detector test data/custom.data cfg/yolov4_custom.cfg backup/yolov4_custom_last.weights {image_path} -thresh 0.3
```

## 🚀 Executando no Google Colab

1. Abra o **Google Colab**.
2. Faça upload do arquivo `yolo_cat_dog_training.ipynb`.
3. Execute cada célula sequencialmente.

## 📌 Referências

- [YOLO - Darknet](https://pjreddie.com/darknet/yolo/)
- [COCO Dataset](https://cocodataset.org/#home)
- [Google Colab](https://colab.research.google.com/)

---

**Autor:** *Seu Nome*\
Se gostou, deixe uma ⭐ no repositório!

