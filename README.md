# Leningrad-2-128k-SRAM

Leningrad-2. Russian ZX Spectrum clone. Schematics and PCB.



После успешного запуска \[Leningrad-2-48k](https://github.com/Alex-2-Graf/LENINGRAD-2-48k) и предложений сообщества,  

было принято решение использовать в проекте статическую память вместо динамической.  

Пришлось существенно переделать узел обращения к памяти.  

А заодно реализовать расширение 128к без использования внешних плат.  
Так же, на освободившееся место удалось поставить два чипа YM2149F.  

Тем самым получив на борту Turbo Sound от NedoPC.  
Так же был добавлен арбитр IORQ. 

&#x20; 

В результате чего на свет появился Ленинград 2 NEXT 128k + TS 2025  

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Foto/L2\_Rev2.00.png)  

&#x20; 

После сборки и отладки, были устранены мелкие недостатки. 

А также, по настойчивым просьбам друзей, проект получил новое название.  

Свет увидела новая версия \[2.01](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Export/Leningrad%202%20128k%20SRAM%202.01%202025.html) \[Схема](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Export/Leningrad%202%20128k%20SRAM%202.01%202025.pdf) \[Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Gerber/Leningrad%202%20128k%20SRAM%202.01%202025%20gerber%20made%20in%20Italy.zip)  

&#x20; 

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Foto/L2\_Rev2.01.png)  

&#x20; 

Не обошлось без курьёза.  
По настойчивой просьбе производителя плат,  

пришлось изменить надпись с "Made in" на "Designed in" ;)  

&#x20; 

После сборки всё заработало без нареканий.  



!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Foto/L2\_2.01.jpg)  

&#x20; 


Перед выпуском следующей версии был добавлен индикатор питания и подправлен порт джойстика.  

И в производство отправилась версия \[2.02](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Export/Leningrad%202%20128k%20SRAM%202.02%202025.html) \[Схема](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Export/Leningrad%202%20128k%20SRAM%202.02%202025.pdf) \[Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Gerber/Leningrad%202%20128k%20SRAM%202.02%202025%20Gerber.zip)  

&#x20; 

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Foto/L2\_Rev2.02.png)  

&#x20; 

Так же был выпущен переходник на Немо и ZX-bus \[Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Gerber/L2\_NS\_Rev\_1\_1\_Gerber.zip)  

&#x20; 

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Foto/Back\_L2\_Nemo\_Spec\_PCB.png)  

&#x20; 

Его отличие от предыдущего заключается в использование сигнала /IORQ-GE по прямому назначению.   

Если раньше /IORQ-GE приходил на А19 (+beta).

То теперь приходит на А17.

То есть в переходнике первой ревизии необходимо отрезать дорожку от А19 и припаять её на А17.  

Всё! Вы стали обладателем второй ревизии.  



!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Jumpers/L2\_Nemo\_1\_0.jpg)

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Jumpers/L2\_Nemo\_1\_1.jpg)  

&#x20; 

Ну и связи с тем, что у нас теперь есть полноценный арбитр появилась возможность  

добавить и плату расширения слотов до 3-х Немо и одного ZX-bus \[Ёлка](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Export/Back\_L2\_Nemo\_x3\_Spec\_Ver2.1.html) \[Схема](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Export/Back\_L2\_Nemo\_x3\_Spec\_Ver2.1.pdf) \[Gerber](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Gerber/Back\_L2\_Nemo\_x3\_Spec\_Ver2.1\_gerber.zip)  

&#x20; 

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Foto/Back\_L2\_Nemo\_x3\_Spec\_Ver2.1\_PCB.png)

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Foto/Back\_L2\_Nemo\_x3\_Spec\_Ver2.1.jpg)  

&#x20; 

Результат оправдал своё ожидание.  

&#x20; 

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Foto/L2\_2.00.jpg)  

&#x20; 

\## Сборка



Как правило сборка и наладка проблем не вызывает.  

Хотя всё же проясним назначени перемычек.  

&#x20; 

JP1, JP2 и JP3 замыкаются в случае установки VGA разъёма.  

При установки HDMI их замыкать не надо.  

Но при этом все резисторы R24-31 заменяются на 270 Ом.  

Джампер J9 необходим для снятия питания с RP4040-Zero при перепрошивке.  

&#x20; 

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Jumpers/J9.jpg)  

&#x20; 

Джампер J12 необходим для выбора прошивки БДИ  

в случае установки 27256 с двумя версиями TR-DOS.  

&#x20; 

!\[](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/blob/main/Jumpers/J12.jpg)  

&#x20; 

\## ПЗУ



ПЗУ для проекта находятся \[тут](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/tree/main/ROM)  

&#x20; 

\## VGA

&#x20; 

Прохивка для RP2040-zero находится \[тут](https://github.com/Alex-2-Graf/Leningrad-2-128k-SRAM/tree/main/VGA)  

&#x20; 

\## Авторы и благодарности



Alex Ekb за RGB2VGA конвертор  

Сообществу \[Scorpion ZS \& Ленинград](https://t.me/zs\_scorpion) и моим друзьям.

Отдельная благодарность за советы и техпомощь HRDY \[Дмитрий](https://github.com/demyanenko-d)

