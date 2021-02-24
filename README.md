# Задание 1. Генерация лиц.

Генерация лиц с настраиваемыми параметрами была сделана с помощью модели TL-GAN https://github.com/SummitKwan/transparent_latent_gan.git

Ноутбук запускала в Google Colab, предварительно загрузив все файлы c репозитория командой `<!git clone https://github.com/SummitKwan/transparent_latent_gan.git /root>`

В директорию с проектом нужно загрузить папки 'asset_model', 'asset_results' из https://www.dropbox.com/sh/y1ryg8iq1erfcsr/AAB--PO5qAapwp8ILcgxE2I6a?dl=0


Т.к. проект написан на tensorflow 1 версии, в Google Colab нужно работь на ней же, чтобы успешно загрузить модель GAN `<%tensorflow_version 1.x>`

После выполнения кода должно появиться окно с элементами управления, где можно настраивать параметры лица.  Чтобы не было корреляции признаков, нужно заблокировать ненужные параметры.
