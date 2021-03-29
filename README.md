# Лабораторная работа №4.
# Использование техник аугментации данных для улучшения сходимости процесса обучения нейронной сети на примере решения задачи классификации Oregon Wildlife  #
Аугментация - это процесс, при котором мы добавляем к исходным реальным фотографиям искусственные помехи и искажения, чем увеличиваем выборку для обучения нейронной сети. В данной работе, для решения задачи классификации данных, использовалась нейронная сеть EfficientNet-B0 предобученная на базе изображений ImageNet, с политикой изменения темпа обучения экспоненциального типа, который был выбран в качетсве оптимального в предыдущей лабораторной работе с параметром k = 0.4 - коэффициент наклона экспоненциальной кривой.


  **Теперь о нашей задаче**

  ***Случай поворота изображения на случайный угол***
  
  *Легенда*
  
  ![легендаП](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0R.png)
  
  ![график 1.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyR.svg)
  
  ![график 1.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossR.svg)
  
  ***Случай манипуляций с яркостью и контрастом***
  
  *Легенда*
  
  ![легендаЯК](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0CB.png)
  
  ![график 2.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyCB.svg)
  
  ![график 2.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossCB.svg)
  
  ***Случай использования случайной части изображения***
  
  *Легенда*
  
  ![легендаИ](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0P.png)
  
  ![график 3.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyP.svg)
  
  ![график 3.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossP.svg)
  
  ***Случай добавления случайного шума***
  
  *Легенда*
  
  ![легендаГ](https://github.com/YurchenokMaxim/lab4/blob/main/%D0%BB%D0%B5%D0%B3%D0%B5%D0%BD%D0%B4%D0%B0G.png)
  
  ![график 4.1](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_categorical_accuracyG.svg)
  
  ![график 4.2](https://github.com/YurchenokMaxim/lab4/blob/main/epoch_lossG.svg)
  
  ***Итог со всеми искажениями, но лучшими параметрами***
 
   
  ![график 5.1]()
  
  
  ***Анализ данных.***
