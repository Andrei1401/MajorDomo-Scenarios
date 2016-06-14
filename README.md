# SoundWeather
Сценарий для "Majordomo" (majordomo.smartliving.ru) на основе данных из плагина получения информации о погоде openweather. Перед применением скрипта установить плагин "openweather". Код добавить либо в раздел "Сценарии" либо "Шаблоны поведения" без символов "<? php" и "?>". Так же для успешного озвучивания у вас должен быть установлен плагин" Windows TTS" для ОС Windows. А в настройках Windows 
Control Panel\Ease of Access\Speech Recognition\Text to Speech 
необходимо выбрать русский синтез речи. Если у вас нерусская ОС, то вам необходимо установить дополнительно русский синтез речи, готовый не идёт по--умолчанию в нерусской ОС Windows.

#ExchangeRates
Сценарий для "Majordomo" (majordomo.smartliving.ru) Получает курсы валют покупки\продажи евро и доллар от API PrivatBank.
Необходимо создать класс "ExchangeRates" в разделе "Объекты", внутри класса создать объект "Rate" и выполнить сценарий. После это у объекта класса будет автоматически создано и инициализировано 4 свойства:
Rate.eurobuy
Rate.eurosale
Rate.usdbuy
Rate.usdsale
Для того что бы данные обновлялись автоматически, необходимо в классе "Timer" открыть метод "onNewHour" и добавить в конец:
//проверяем изменение курса валют, вызываем сценарий
runScript("ExchangeRates");
Название сценария должно совпадать с вызываемым в методе "onNewHour".
Для хранения статистики изменения курса и построения графиков в класс "ExchangeRates" необходимо добавить свойства:
eurobuy
eurosale
usdbuy
usdsale
Указать коллличество дней для хранения значений курса.