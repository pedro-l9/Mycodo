Mycodo - это система мониторинга и регулирования окружающей среды с открытым исходным кодом, созданная для работы на одноплатных компьютерах, в частности [Raspberry Pi](https://en.wikipedia.org/wiki/Raspberry_Pi).

Первоначально разработанная для выращивания съедобных грибов, Mycodo стала делать гораздо больше. Система состоит из двух частей: бэкэнд (демон) и фронтэнд (веб-сервер). Бэкэнд выполняет такие задачи, как получение измерений от датчиков и устройств и координация различных реакций на эти измерения, включая возможность модулировать выходы (переключать реле, генерировать ШИМ-сигналы, управлять насосами, переключать беспроводные розетки, публиковать/подписываться на MQTT и т.д.), регулировать условия окружающей среды с помощью ПИД-регулирования, планировать таймеры, делать фотографии и транслировать видео, запускать действия, когда измерения соответствуют определенным условиям, и многое другое. На передней панели расположен веб-интерфейс, который позволяет просматривать и настраивать систему с любого устройства, поддерживающего браузер.

Mycodo можно использовать по-разному. Некоторые пользователи просто хранят результаты измерений датчиков для удаленного мониторинга условий, другие регулируют условия окружающей среды в физическом пространстве, третьи делают фотографии, активированные движением, или фотографии с временной задержкой.

Входные контроллеры получают измерения и сохраняют их в базе данных временных рядов InfluxDB. Измерения обычно поступают от датчиков, но также могут быть настроены на использование возвращаемых значений команд Linux Bash или Python, или математических уравнений, что делает эту систему очень динамичной для получения и генерации данных.

Контроллеры выходов производят изменения на общих контактах ввода/вывода (GPIO) или могут быть настроены на выполнение команд Linux Bash или Python, что позволяет использовать их в самых разных целях. Существует несколько различных типов выходов: простое переключение контактов GPIO (HIGH/LOW), генерация сигналов с широтно-импульсной модуляцией (PWM), управление перистальтическими насосами, публикация MQTT и многое другое.

Когда входы и выходы объединены, функциональные контроллеры могут использоваться для создания контуров обратной связи, которые используют выходное устройство для изменения условий окружающей среды, измеряемых входом. Определенные входы могут быть соединены с определенными выходами для создания множества различных приложений управления и регулирования. Помимо простого регулирования, методы могут быть использованы для создания изменяющегося во времени заданного значения, что позволяет использовать их в термоциклерах, печах доводки, моделировании окружающей среды для террариумов, ферментации продуктов питания и напитков, приготовления пищи ([sous-vide](https://en.wikipedia.org/wiki/Sous-vide)) и т.д., и т.п.

Триггеры могут быть установлены для активации событий на основе определенных дат и времени, в соответствии с продолжительностью времени или восходом/закатом солнца на определенной широте и долготе.

Mycodo переведен на несколько языков. По умолчанию язык браузера определяет, какой язык будет использоваться, но его можно переопределить в Общих настройках, на странице `[Значок шестеренки] -> Настроить -> Общие`. Если вы обнаружили проблему и хотите исправить перевод или добавить другой язык, это можно сделать по адресу [https://translate.kylegabriel.com](http://translate.kylegabriel.com:8080/engage/mycodo/).