# DevOpsHomeWorks
Домашнее задание по лекции "Введение в DevOps"

№1

https://yadi.sk/d/pv51z5u-KzZqjg

https://yadi.sk/d/Vey3sQFhP9S10w

https://yadi.sk/d/_410q6ZPibpe-Q

https://yadi.sk/d/sKBmTxD3JHt-xg

https://yadi.sk/d/0QYGOJ5_FGpgAg

№2

Будет описана ситуация близкая к идеальной. С небольшой командой работающей над своим сервисом. Без использования git flow, релизных веток,
с возможностью быстро деплоить на прод каждую фичу.

1 Бизнес/заказчик - формулирует задачу

2 Аналитик - описывает аналитику/создает задачу в трекере

3 Разработчик - получает задачу (после необходимых действий согласно существующей в команде методологии разработки)

4 DevOps - разворачивает инфраструктуру: 

- Систему контроля версий
- dev, prod, test стенды
- сборщик, анализатор кода
- Настраивает пайплайн для сборки
- Подключает проверку на % покрытия тестаии для каждого пуша фичи в систему контроля версий
- Автоматический деплой на прод из мастер ветки

5 DevOps - реализовал автоматическую сборку сервиса в докер контейнер для каждого пуша в системе контроля версий
(контейнер для каждого коммита новый, сохраняется где-нибудь в нексусе)

6 Разработчик - создает фича-ветку от мастера, пишет код, отправляет на ревью. 
Должен иметь возможность поставить свою сборку на dev стенд
(например взять собранный им контейнер и указать его (docker tag) в деплоймент конфиге нужного стенда, 
Либо DevOps может подготовить скрипт для этого - запускаемый по http запросу с параметрами..
Либо скрипт может стартовать автоматически после создания соответствующей задачи на сборку в jira + закрывать задачу после выполнения)

7 Разработчик назначает задачу на тестировщика. Тестировщик должен иметь возможность задеплоить фичу для проверки на выбранный им тестовый стенд.

8 Тестировщик после проверок закрывает задачу, это дает возможность влить ее в мастер.

9 После сливания фича-ветки с мастером новая фича автоматически деплоится на прод