<!-- verified: agorbachev 03.05.2022 -->

<!-- 12.7.1 -->
## Стандартные групповые IPv6-адреса

Вы уже знаете, что существует несколько типов IPv6-адресов: одноадресные, многоадресные и произвольные. В этом разделе мы подробнее разберем многоадресные адресах.

Групповые IPv6-адреса аналогичны групповым IPv4-адресам. Их используют для отправки одного пакета по одному или нескольким адресам назначения (группе многоадресной рассылки). Групповые адреса IPv6 имеют префикс FF00::/8

**Примечание**: Групповые адреса могут быть только адресами назначения, а не адресами источника.

Типы групповых IPv6-адресов:

* стандартный многоадресный адрес,
* групповой адрес запрашиваемого узла.

<!-- 12.7.2 -->
## Стандартные адреса многоадресной рассылки IPv6

Стандартные адреса многоадресной рассылки в IPv6 зарезервированы для заданных групп устройств. Стандартный групповой адрес используют для осуществления связи с группой устройств на одном протоколе или сервисе. Стандартные групповые адреса используют вместе с конкретными протоколами, например с протоколом DHCPv6.

Есть две распространенные группы стандартных групповых IPv6-адресов:

* **ff02: Группа многоадресной рассылки для всех узлов FF02::1.**  В неё включены все устройства под управлением протокола IPv6. Пакет, отправленный этой группе, принимают и обрабатывают все IPv6-интерфейсы в канале или сети. Эта группа адресов работает так же, как широковещательный адрес в протоколе IPv4. На рисунке видно, как осуществляется связь с помощью групповых адресов для всех узлов. IPv6-маршрутизатор отправляет сообщения RA ICMPv6 группе многоадресной рассылки для всех узлов.
* **ff02::2 Группа глобальной конфигурации многоадресной группы.**  - К ней присоединяются все маршрутизаторы IPv6. Маршрутизатор становится членом этой группы, когда он включен как маршрутизатор IPv6 с параметром **ipv6 unicast-routing**. Пакет, отправленный этой группе, принимается и обрабатывается всеми IPv6-маршрутизаторами в канале или сети.

![](./assets/12.7.2.svg "Многоадресная рассылка всех узлов IPv6: сообщение RA")


Устройства под управлением протокола IPv6 отправляют сообщения RS ICMPv6 на групповой адрес для всех маршрутизаторов. Сообщение RS запрашивает сообщение RA у IPv6-маршрутизатора, которое поможет устройству в процессе адресной конфигурации. Маршрутизатор IPv6 отвечает сообщением RA, как показано на рисунке.

<!-- 12.7.3 -->
## Групповые IPv6-адреса запрашиваемых узлов

Групповой адрес запрашиваемых узлов аналогичен групповому адресу для всех узлов. Он соответствует специальному адресу многоадресной рассылки Ethernet. Это позволяет сетевой плате Ethernet отфильтровывать кадр, анализируя MAC-адрес назначения без его отправки в IPv6-процесс, чтобы убедиться, что устройство действительно является узлом назначения IPv6-пакета.

![](./assets/12.7.3.svg)


<!-- 12.7.4 -->
<!--## Исследовательская работа: определение IPv6-адресов [(описание в PDF)](./assets/12.7.4-lab---identify-ipv6-addresses_ru-RU.pdf)

В этой работе вам необходимо выполнить следующие задачи:

* Часть 1: Определение различных типов IPv6-адресов
* Часть 2: Изучение IPv6-адреса сетевого интерфейса и узла
* Часть 3: Отработка правил сокращения IPv6-адресов
-->


