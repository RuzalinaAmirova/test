# Задание 2. Реконструкция лица и эмоций

Проект выполнен с использованием модели [DECA](https://github.com/YadiraF/DECA.git). Фотография лица была получена с помощью TL-GAN

![в](https://user-images.githubusercontent.com/67918036/110302313-285ace00-800a-11eb-92a8-8468537d76ab.jpg)

Сначала я создала меш лица и эмоций в формате .obj. Затем отрендерила их с помощью PyTorch3d

Отрендеренный меш лица 

![загружено (3)](https://user-images.githubusercontent.com/67918036/110302709-97382700-800a-11eb-90f9-3ed5c3d61786.png)

Лицо в повороте 

![загружено (2)](https://user-images.githubusercontent.com/67918036/110302787-ad45e780-800a-11eb-8aa3-8ca4de44901a.png)

Лицо с выражением эмоций

![загружено (4)](https://user-images.githubusercontent.com/67918036/110302861-c64e9880-800a-11eb-9383-c738f1640f33.png)

## Что не получилось
 1. Добиться реалистичности. Текстура выглядит неестественно. Лицо получается глазуированным
 2. Сохранить результат в виде датасета из фотографий. При сохранение изображений рендера через цикл, не получается то же качество, что и при визуализации. Лица на этих изображениях, сохраненных через цикл, покрыты сеткой.
  
 ![file (1)](https://user-images.githubusercontent.com/67918036/110303693-bbe0ce80-800b-11eb-9801-78b85478c9a2.png)

## Инструкция по запуску проекта в Google Colab

1. Поключиться к Google диску
 
`from google.colab import drive`

`drive.mount('/content/drive')`

2. Клонировать репозиторий https://github.com/YadiraF/DECA.git в директорию

`%cd /content/drive/MyDrive/root`

`!git clone https://github.com/YadiraF/DECA.git`

3. Загрузить следующие файлы:
 1. [Flame model](https://flame.is.tue.mpg.de/downloads), выбрать Flame 2020, разархивировать и файл 'generic_model.pkl' поместить в root/data
 2. [DECA trained model](https://drive.google.com/file/d/1rp8kdyLPvErw2dTmqtjISRVvQLj6Yzje/view). Не распаковывать файл и поместить его в root/data
 3. Следовать инструкции в [Albedo mode](https://github.com/TimoBolkart/BFM_to_FLAME.git). Полученный файл 'FLAME_albedo_from_BFM.npz' поместить в root/data

4. Создать виртуальную среду

`! apt-get install python3.7-dev python3.7-venv`

`!echo "Creating virtual environment"`

`!python3.7 -m venv deca-env`

`!echo "Activating virtual environment"`

`!source /content/drive/MyDrive/test_2/deca-env/bin/activate`

5. Установить библиотеки

`!/content/drive/MyDrive/test_2/deca-env/bin/pip install -r requirements.txt`

`!pip install face_alignment`

`!pip install chumpy`

6. Установить PyTorch3d

`import sys`

`import torch`

`version_str="".join([
    f"py3{sys.version_info.minor}_cu",
    torch.version.cuda.replace(".",""),
    f"_pyt{torch.__version__[0:5:2]}"
])`

`!pip install pytorch3d -f https://dl.fbaipublicfiles.com/pytorch3d/packaging/wheels/{version_str}/download.html`

7. Запустить остальные ячейки кода, меняя путь на свою директорию. Либо, чтобы не менять пути, создайте папку 'test_2' на диске и работайте в нем. Фотографию лица, на котором выполнен проект, можно скачать [здесь](https://drive.google.com/file/d/1BUmIjjc8O_nVPgWPwG-w3sdmhgu4Hv2p/view?usp=sharing). Путь к ней должен быть таким: root/TestSamples/examples/2.png
