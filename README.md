# ResumeUpdater

Данная программа позволяет автоматически обновлять резюме на сайте hh.ru  
Сама идея взята здесь:   
http://habrahabr.ru/sandbox/72648/

Подробное описание:

ResumeUpdater обновляет резюме на сайте hh.ru. Для этого посылается POST запрос, настройки которого берутся из кэша браузера. Эти данные считываются из файла с форматом .properties, и отображаются в виде таблицы. При изменении значений таблицы, также перезаписывается этот файл. Более того при внесении изменений в данный файл, таблица программы будет создана уже с новой информацией. Программа умеет обновлять несколько резюме одновременно. Для этого используются ExecutorService, Executors которые запускают несколько потоков на выполнение. В программе можно установить автоматическое обновление при следующем запуске. Запуск таймера и его отключение зависит от вкл/выкл соответствующего флажка. Для отслеживания изменения значений этого флажка используется паттерен Observer.

Для обновления резюме необходимо:    
1) добавить id Вашего резюме  
2) узнать данные POST запроса (более подробно по ссылке выше)  
Пример для Mozilla Firefox:  

![requestsetting](https://cloud.githubusercontent.com/assets/13558216/11936990/f69993c2-a82a-11e5-8b2a-ce79ca8b3cf4.PNG)

3) добавить их в таблицу, либо в файл PostRequest.properties

![resumeupdater](https://cloud.githubusercontent.com/assets/13558216/11936992/f9d3ee02-a82a-11e5-8277-e21fd92609cd.PNG)