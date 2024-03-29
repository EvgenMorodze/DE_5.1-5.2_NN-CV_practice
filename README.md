# DE_5.1-5.2_NN-CV_practice
Репозиторий с практическими работами по теме "Искусственный интеллект. Введение в нейронные сети." Работы по соотв. темам разложены по файлам:  
- **CV_5-1_morozov.ipynb**  
- **CV_5-2_morozov.ipynb**  


## 5.1. Искусственный интеллект. Введение в нейронные сети.  

### 1. Постановка задачи.

Изменить простую нейронную сеть, построенную в ходе практического занятия с помощью фреймворка pytorch. Итоговая нейронная сеть должна решать задачу многоклассовой (не бинарной) классификации. Для чего нужно использовать функцию потерь (loss-function) и функцию активации (activation-function), отличные от применённых в примере.

Источник данных: keras MNIST dataset


### 2. Ход работы.

1. Подключение библиотек, загрузка данных. Первичный анализ задачи и представление об архитектуре сети.
2. Изменение нейросети, построенной в ходе разбора учебной задачи:
    - увеличение количества скрытых слоев (увеличить с 2 до 3)
    - количество нейронов подставлять через массив, подаваемый при инициализации класса модели
    - добавить dropout=0.3 (вероятность выпадения нейрона в слое путём зануления его веса) до первого скрытого слоя
3. Показать, как изменения сети влияют на результат работы модели на тестовой выборке.
4. Посчитать метрики классификации через classification report (sklearn) для каждого класса.
5. Составление выводов.


### 3. Исследование.

Учебный пример был построен на библиотеке PyTorch, однако в целях самообразования и сравнения была предпринята поптка ознакомления с библиотекой Tensorflow и фреймворка-надстройки над ней - Keras, которая приводится в тексте ниже.

Разбор начальной задачи вылился в увлекательное исследование темы нейронных сетей как универсальных классификаторов, которое будёт продолжено автором в порядке личной инициативы в виду потрясающего потенциала и действительной универсальности последних. В ходе решения я, видимо, подошёл к теме работы 5_2 и остановился в ожидании комментариев, совет был дан дельный, ошибки удалось исправить.


## 5.2. Работа с изображениями в ИИ.  

### 1. Постановка задачи.

В ходе занятия рассматривалось устройство сверточных нейронные сетей и слои пуллинга, методы оптимизации моделей для работы с gpu и реализация собственной сверточной нейронной сети. Практическая задача состоит в следующем:

    - Изменить нейронную сеть из лекции
    
    - Вычислить средние и дисперсии по выборке обучающего датасета и применить их для того, чтобы производить более качественную предобработку данных.
    
    - Используя библиотеку albumentations, добавить дополнительные аугментации на обучающий датасет (изменение контрастности, блюр и т.д).
    
    - Импортировать предобученную нейронную сеть vgg16 из pytorch, дообучить ее для решения той же задачи, что была в данном ноутбуке. (Необходимо заморозить протекание градиента по нейронной сети, после чего заменить последний линейный слой и менять веса только в нем). В случае, если модель дает качество хуже, чем наша рукописная нейронная сеть необходимо объяснить причины.
    
    - Сохранить нейронную сеть в отдельный файл и в следующей ячейке загрузить ее в новый экземпляр. После чего получить метрики на тестовом множестве изображений уже загруженной нейронной сетью.

### 2.  Ход работы.

Ход работы вытекает напрямую из поставленной задачи: подключив библиотеки и загрузив данные, выполним задания практического занятия и составим выводы.

### 3.  Исследование.

Автор честно пытался пройти оба модуля с тщанием и внимательностью, но успел охватить лишь часть диапазона. В результате составилось мнение, что Keras по сути годится для ознакомления с темой нейросетей, но для профессионального использования в уме стоит держать именно использование PyTorch. По всей видимости она позвоялет очень точно контролировать поведение и выстраивать желаемую архитектуру сетей и не даром всё-таки всё болшее количество работ производится в этой библиотеке.
