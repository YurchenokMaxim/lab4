# Лабораторная работа №4.
# Использование техник аугментации данных для улучшения сходимости процесса обучения нейронной сети на примере решения задачи классификации Oregon Wildlife  #
Аугментация - это процесс, при котором мы добавляем к исходным реальным фотографиям искусственные помехи и искажения, чем увеличиваем выборку для обучения нейронной сети. В данной работе, для решения задачи классификации данных, использовалась нейронная сеть EfficientNet-B0 предобученная на базе изображений ImageNet, с политикой изменения темпа обучения экспоненциального типа, который был выбран в качетсве оптимального в предыдущей лабораторной работе с параметром k = 0.4 - коэффициент наклона экспоненциальной кривой.


  **Теперь о нашей задаче**

  ***Случай поворота изображения на случайный угол***
  
 ![поворот](https://github.com/YurchenokMaxim/lab4/blob/main/1.png)
 
 В RandomRotation был использован один параметр factor, суть которого состоит в том, что 2 пи домнажаются на это значение и тем самым устанавливают границы. Немного на примере:
 значения factor = 0.1 - случайное вращение будет в диапазоне (-0.1 * 2pi, 0.1 * 2pi), а если 2 factor = (0, 0.1), то случайное вращение будет в диапазоне (0 * 2pi, 0.1 * 2pi).
  
  *Легенда*
  
  1. factor =0.7 тренировка
  2. factor =0.7 валидация
  3. factor =0.5 тренировка
  4. factor =0.5 валидация
  5. factor =0.3 тренировка
  6. factor =0.3 валидация
  
  ![легендаП](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0R.png)
  
  ***График точности***
  
  ![график 1.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyR.svg)
  
  ***График потерь***
  
  ![график 1.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossR.svg)
  
  По итогам графикам лучшие результаты были при параметре factor=0.5, т.к. точность выросла на 0.2% при равной сходимости на 7ой эпохе.
  
  ***Случай манипуляций с яркостью и контрастом***
  
  Параметры: для яркости image - входное изображение и delta   - величина для добавления к значениям пикселей, для контрастности image - входное изображение, contrast_factor - множитель для регулировки контрастности.
  
  ![контраст](https://github.com/YurchenokMaxim/lab4/blob/main/2.png)
  
  ![яркость](https://github.com/YurchenokMaxim/lab4/blob/main/6.png)
  
  *Легенда*
  
  1. contrast_factor=0.5 и delta=0.5 тренировка
  2. contrast_factor=0.5 и delta=0.5 валидация
  3. contrast_factor=0.7 и delta=0.3 тренировка
  4. contrast_factor=0.7 и delta=0.3 валидация
  5. contrast_factor=0.3 и delta=0.3 тренировка
  6. contrast_factor=0.3 и delta=0.3 валидация
  
  ![легендаЯК](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0CB.png)
  
  ***График точности***
  
  ![график 2.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyCB.svg)
  
  ***График потерь***
  
  ![график 2.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossCB.svg)
  
  По итогам опыта наилучший результат показали параметры contrast_factor=0.7 и delta=0.3, т.к. точность на валидации оказалась выше на 0.2%, сходимость же на 4 эпохи была также лучше.
  
  ***Случай использования случайной части изображения***
  
  ![случайность](https://github.com/YurchenokMaxim/lab4/blob/main/crop.png)
  
  В данном случае, в качестве параметров мы используем размер для случайного куска изображения, по которому мы планируем обучать нашу нейронную сеть, соответственно первый параметр высота, второй- ширина.
  
  *Легенда*
  
  1. размер 270x270  тренировка
  2. размер 270x270  валидация
  3. размер 300x300 тренировка
  4. размер 300x300  валидация
  5. размер 500x500  тренировка
  6. размер 500x500  валидация
  
  ![легендаИ](https://github.com/YurchenokMaxim/lab4/blob/main/picture.png)
  
  ***График точности***
  
  ![график 3.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyP.svg)
  
  ***График потерь***
  
  ![график 3.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossP.svg)
  
  По итогам графиков лучший результат был у параметров размера 270x270, т.к., при равной точности в 86.7% на валидации, сходимость лучше в сравнении с 300х300 на 8 эпох, а параметры 500х500 уступают в точности на 11% и не имеют смысла рассматриваться дальше.
  
  ***Случай добавления случайного шума***
  
  ![шум](https://github.com/YurchenokMaxim/lab4/blob/main/3.png)
  
  *Легенда*
  
  stddev- значение среднеквадратичного отклонения добавляемого шума.
  
  1. stddev=0.5 тренировка
  2. stddev=0.5 валидация
  3. stddev=0.7 тренировка
  4. stddev=0.7 валидация
  5. stddev=0.3 тренировка
  6. stddev=0.3 валидация
  
  ![легендаГ](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0G.png)
  
  ***График точности***
  
  ![график 4.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyG.svg)
  
  ***График потерь***
  
  ![график 4.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossG.svg)
  
  По всем показателям наилучшим параметром оказался stddev=0.5, при котором точность оказалась выше на 0.3%, чем у параметра 0.3, а сходимость на одну эпоху выше. В сравнении с параметром 0.7 лучшая точность оказалась одинаковой, но потери меньше, поэтому лучший параметр stddev=0.5.
  
  ***Итог со всеми искажениями, но лучшими параметрами***
 
  ![реализация](https://github.com/YurchenokMaxim/lab4/blob/main/5.png)
  
  1. Оранжевый-тренировка из прошлой работы
  2. Синий-валидация из прошлой работы
  3. Красный-тренировка с аугментацией
  4. Голубой-валидация с аугментацией
  
  ***График точности***
  
  ![итог1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyFinish.svg)
  
  ***График потерь***
  
  ![итог2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossFinish.svg)
  
  ***Анализ данных.***

  В ходе изучения итоговых графиков, было выявлено, что при аугментации точность на валидации упала на 3.1%.
