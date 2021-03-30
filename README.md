# Лабораторная работа №4.
# Использование техник аугментации данных для улучшения сходимости процесса обучения нейронной сети на примере решения задачи классификации Oregon Wildlife  #
Аугментация - это процесс, при котором мы добавляем к исходным реальным фотографиям искусственные помехи и искажения, чем увеличиваем выборку для обучения нейронной сети. В данной работе, для решения задачи классификации данных, использовалась нейронная сеть EfficientNet-B0 предобученная на базе изображений ImageNet, с политикой изменения темпа обучения экспоненциального типа, который был выбран в качетсве оптимального в предыдущей лабораторной работе с параметром k = 0.4 - коэффициент наклона экспоненциальной кривой.


  **Теперь о нашей задаче**

  ***Случай поворота изображения на случайный угол***
  
 ![поворот](https://github.com/YurchenokMaxim/lab4/blob/main/1.png)
 
 В RandomRotation был использован один параметр factor, суть которого состоит в том, что 2 пи домнажаются на это значение и тем самым устанавливают границы. Немного на примере:
 значения factor = 0.1 - случайное вращение будет в диапазоне (-0.1 * 2pi, 0.1 * 2pi), а если 2 factor = (0, 0.1), то случайное вращение будет в диапазоне (0 * 2pi, 0.1 * 2pi).
  
  *Легенда*
  
  1. 0.7 тренировка
  2. 0.7 валидация
  3. 0.5 тренировка
  4. 0.5 валидация
  5. 0.3 тренировка
  6. 0.3 валидация
  
  ![легендаП](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0R.png)
  
  ***График точности***
  
  ![график 1.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyR.svg)
  
  ***График потерь***
  
  ![график 1.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossR.svg)
  
  ***Случай манипуляций с яркостью и контрастом***
  
  ![контраст](https://github.com/YurchenokMaxim/lab4/blob/main/2.png)
  ![]()
  
  *Легенда*
  
  1. 0.5 0.5 тренировка
  2. 0.5 0.5 валидация
  3. 0.3 0.7 тренировка
  4. 0.3 0.7 валидация
  5. 0.3 0.3тренировка
  6. 0.3 0.3валидация
  
  ![легендаЯК](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0CB.png)
  
  ***График точности***
  
  ![график 2.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyCB.svg)
  
  ***График потерь***
  
  ![график 2.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossCB.svg)
  
  ***Случай использования случайной части изображения***
  
  ![случайность](https://github.com/YurchenokMaxim/lab4/blob/main/4.png)
  
  *Легенда*
  
  1. 15х15  тренировка
  2. 15х15  валидация
  3. 50х50  тренировка
  4. 50х50  валидация
  5. 100х100  тренировка
  6. 100х100  валидация
  
  ![легендаИ](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0P.png)
  
  ***График точности***
  
  ![график 3.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyP.svg)
  
  ***График потерь***
  
  ![график 3.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossP.svg)
  
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
  
  ***Итог со всеми искажениями, но лучшими параметрами***
 
  ![реализация](https://github.com/YurchenokMaxim/lab4/blob/main/5.png)
  
  
  
  ***График точности***
  
  ![итог1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyAll.svg)
  
  ***График потерь***
  
  ![итог2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossAll.svg)
  
  
  ***Анализ данных.***
