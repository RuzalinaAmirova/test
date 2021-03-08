Проекты запускались в Google Colab

# Задание 1. Генерация лиц.

Проект выполнен с применением TL-GAN, которая позволяет менять параметры сгенерированного лица в интерактивном окне с элементами управления. 

![Снимок](https://user-images.githubusercontent.com/67918036/110290875-52a58f00-7ffc-11eb-8107-133e358b9003.PNG)

Лицо после изненений 

![Снимок 2](https://user-images.githubusercontent.com/67918036/110297993-19bde800-8005-11eb-99b5-de501260abc2.PNG)


Признаки, которые не должны меняться, нужно заблокировать, чтобы изненение одного признака не приводило к изменению другого. Например, длина волос коррелирует с гендером: чем длиннее волосы, тем женственнее лицо. И, чтобы получить мужское лицо с длинными волосами, нужно заблокировать признак 'Male' и наоборот.

## Инструкция по запуску в Google Colab

 1. Поключиться к Google диску 
 
 `from google.colab import drive`
 
 `drive.mount('/content/drive')`
 
 2. Клонировать репозиторий https://github.com/SummitKwan/transparent_latent_gan.git в директорию 
 
 `%cd /content/drive/MyDrive/root`
 
 `!git clone https://github.com/SummitKwan/transparent_latent_gan.git `
 
 3. Установить библиотеки
 
 `!pip install -r requirements.txt`
 
 4. Перейти на первую версию tensorflow (TL-GAN работает на первой версии, а в Google Colab по умолчанию вторая)
 
 `%tensorflow_version 1.x`
 
 5. Запустить остальные ячейки с кодом в ноутбуке

