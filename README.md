# mind-set OCR task
## Задача:
Построить базовый алгоритм распознавания текста из документов. Создать алгоритм распознования ФИО с паспорта.  
## Что сделал/получилось:
Мое решение можно посмотреть в ```main.ipynb```  
  
Попробовал две библиотеке для распознавания текста: ```pytesseract``` и ```easyocr```. В итоге, остановился на ```easyocr```, работает лучше.
Для распознавания ФИО использовал относительно простой алгоритм. Обрезал фото, так чтобы было видно только ФИО и потом прогонял через ```easyocr```.
Также пробовал использовать ```natasha``` и ```nltk```, результат был плохим.  
  
**update1:** собрал небольшой датасет из фотографий паспартов и в ручную разметил(с помощью сервиса [makesense.ai](https://www.makesense.ai/)). После обучил yolov5 на 200 эпох. Модель детектирует не мега хорошо, так как обучал на совсем маленьком количестве фотографий. Модель детектирует ФИО и после можно вырезать имя из фото и прогонять через easyocr. Решение этой части находится в ```FIO_detection.ipynb```
  
**update2:** создал свою OCR модель и обучил на этом [датасете](https://github.com/wlinna/russian-ocr). Код обучения можно посмотреть тут ```my-ocr-mind-set.ipynb```
## Что можно улучшить:
Стоит собрать датасет из снимков главной страницы паспорта и обучить собственную модель.  
Также стоит обучить отдельную модель для детекции ФИО и потом уже использовать алгоритмы ocr.
## Ссылки:
https://github.com/madmaze/pytesseract  
https://github.com/JaidedAI/EasyOCR  
https://github.com/natasha/natasha  
https://github.com/nltk/nltk
https://github.com/wlinna/russian-ocr
