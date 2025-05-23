# ToFLaC6
Шестая лабораторная работа по дисциплине Теория формальных языков и компиляторов  
Задание:  
Используя библиотечные реализации (например, класс Regex в C#), решите 3 задачи в соответствии с персональным вариантом (варианты заданий в файле “ТФЯиК Задание на ЛР 6 АВТ-113, АВТ-114”).  
Необходимо встроить разработанные алгоритмы в интерфейс текстового редактора, разработанного на первой лабораторной работе.  
Исходные данные – текст, содержащий данные заданного формата. Выходные данные – найденные выражения с указанием позиции начала. Возможно выделение подстрок в исходном тексте.  

Варианты:  
Построить РВ, описывающее шестнадцатеричный код (HEX) цвета (длиной 3)  
Построить РВ для валидации российских номеров мобильных телефонов (начинаются с цифры 8 символов +7, далее зоновый код в скобках или без и номер абонента, номер абонента может быть разделен пробелами или символами-)  
Построить РВ, описывающее время. Формат: ЧЧ:ММ:СС в 24-часовом формате с обязательным ведущим 0  

Решение:  
В первом случае нужна подстрока из 3 символов, которыми могут быть цифры и буквы от A до F и символ # перед ними: @"^#([0-9A-Fa-f]{3})$" 
Во втором - первый блок будет либо 8, либо +7, далее наборы по 3-3-2-2 цифры через пробел или - : @"^(8|\+7)[\- ]?(\(?[0-9]{3}\)?[\- ]?)?[0-9]{3}[\- ]?[0-9]{2}[\- ]?[0-9]{2}$"  
В третьем - три пары чисел с ограничениями (минуты и секунды не могут быть больше 59, часы - не больше 24) : @"^([01][0-9]|2[0-3]):[0-5][0-9]:[0-5][0-9]$"  

Примеры работы программы:  
![Снимок экрана (1887)](https://github.com/user-attachments/assets/23c7c734-7cca-4fca-bc9f-0b7f87d48ebe)  

![Снимок экрана (1888)](https://github.com/user-attachments/assets/79ca1691-a531-44d9-9a3a-080c955b374c)  

![Снимок экрана (1889)](https://github.com/user-attachments/assets/15d7d930-99de-4f10-b98f-35fc609459ee)  

![Снимок экрана (1891)](https://github.com/user-attachments/assets/a4e00e53-899c-486c-ba6e-4c85989f5e4b)  

![Снимок экрана (1892)](https://github.com/user-attachments/assets/41a93abd-8222-4c88-989c-a6b79967fd2a)  
