# Лабораторная работа №4.
# Использование техник аугментации данных для улучшения сходимости процесса обучения нейронной сети на примере решения задачи классификации Oregon Wildlife  #
Аугментация - это процесс, при котором мы добавляем к исходным реальным фотографиям искусственные помехи и искажения, чем увеличиваем выборку для обучения нейронной сети. В данной работе, для решения задачи классификации данных, использовалась нейронная сеть EfficientNet-B0 предобученная на базе изображений ImageNet, с политикой изменения темпа обучения экспоненциального типа, который был выбран в качетсве оптимального в предыдущей лабораторной работе с параметром k = 0.4 - коэффициент наклона экспоненциальной кривой.


  **Теперь о нашей задаче**

  ***Случай поворота изображения на случайный угол***
  
  *Легенда*
  
  ![легендаП](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0R.png)
  
  ***График точности***
  
  ![график 1.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyR.svg)
  
  ***График потерь***
  
  ![график 1.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossR.svg)
  
  ***Случай манипуляций с яркостью и контрастом***
  
  *Легенда*
  
  ![легендаЯК](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0CB.png)
  
  ***График точности***
  
  ![график 2.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyCB.svg)
  
  ***График потерь***
  
  ![график 2.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossCB.svg)
  
  ***Случай использования случайной части изображения***
  
  *Легенда*
  
  ![легендаИ](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0P.png)
  
  ***График точности***
  
  ![график 3.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyP.svg)
  
  ***График потерь***
  
  ![график 3.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossP.svg)
  
  ***Случай добавления случайного шума***
  
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
 
   
  ![график 5.1]()
  
  
  ***Анализ данных.***
