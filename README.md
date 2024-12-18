# Задание L0

Необходимо разработать демонстрационный сервис с простейшим интерфейсом, отображающий данные о заказе. Модель данных можно найти в конца задания.

Что нужно сделать:
## 1. Развернуть локально PostgreSQL
1. Создать свою БД
2. Настроить своего пользователя
3. Создать таблицы для хранения полученных данных
## 2. Разработать сервис
1. Реализовать подключение к брокерам и подписку на топик orders в Kafka
2. Полученные данные записывать в БД
3. Реализовать кэширование полученных данных в сервисе (сохранять in memory)
4. В случае прекращения работы сервиса необходимо восстанавливать кэш из БД
5. Запустить http-сервер и выдавать данные по id из кэша
## 3. Разработать простейший интерфейс отображения полученных данных по id заказа

### Советы

1. Данные статичны, исходя из этого подумайте насчет модели хранения в кэше и в PostgreSQL. Модель в файле model.json

2. Подумайте как избежать проблем, связанных с тем, что в канал могут закинуть что-угодно

3. Чтобы проверить работает ли подписка онлайн, сделайте себе отдельный скрипт, для публикации данных в топик

4. Подумайте как не терять данные в случае ошибок или проблем с сервисом

5. Apache Kafka разверните локально

6. Удобно разворачивать сервисы для тестирования можно через docker-compose

7. Для просмотра сообщений в Apache Kafka можно пользоваться Redpanda Console

### Бонус-задание

1. Покройте сервис автотестами — будет плюсик вам в карму

2. Устройте вашему сервису стресс-тест: выясните на что он способен

3. Логи в JSON-формате делают их более удобными для машинной обработки

4. Воспользуйтесь утилитами WRK и Vegeta, попробуйте оптимизировать код.
