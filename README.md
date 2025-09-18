# Treinamento_e_Detec-o_com_Rede_Yolo

Detecção de Objetos Personalizada com YOLOv5
Este projeto demonstra como treinar um modelo YOLOv5 para detecção de objetos personalizada usando o conjunto de dados COCO. O código baixa um subconjunto do conjunto de dados COCO, prepara-o para treinamento e treina um modelo YOLOv5 para detectar objetos específicos (neste caso, "plant" e "food-other"). Ele também inclui código para testar o modelo treinado em uma nova imagem.

Pré-requisitos
Para executar este código, você precisa ter um ambiente Google Colab com acesso a GPU. As seguintes bibliotecas são usadas e instaladas no notebook:

torch

os

json

requests

cv2

numpy

matplotlib

PIL

google.colab

pycocotools

O projeto também utiliza o repositório YOLOv5 e suas dependências, que são clonados e instalados no início do notebook.

Configuração e Instalação
Clone o repositório YOLOv5:

!pip install -r requirements.txt

!wget http://images.cocodataset.org/annotations/annotations_trainval2017.zip

!unzip -q annotations_trainval2017.zip

!wget -O yolov5s.pt https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5s.pt

!python train.py --img 640 --batch 16 --epochs 100 --data dataset.yaml --weights yolov5s.pt

!python detect.py --weights runs/train/exp/weights/best.pt --source caminho/para/imagem.jpg
