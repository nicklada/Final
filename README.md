# Тестирование сервиса оплаты путешествий через пользовательский интерфейс
Тестирование сервиса оплаты через вэб-интерфейс на базе готовой симулятора банковских сервисов (внутренней БД) с СУБД postgreSQL

### Prerequisites

Перед началом работы убедитесь, что на вашем ПК установлены:

1.Git

2.IntelliJ IDEA CE с поддержкой Java

3.Docker Desktop

4.Браузер Google Chrome


Окружение:
OS Version: Mac OS High Sierra
Java version: Openjdk version "11.0.6" 2020-01-14


## Инструкция по запуску приложения и тестов##
1. Скачайте в локальный репозиторий все файлы с данного репозитория (можно воспользоваться командой `git pull`
2. Создайте контейнер Docker для работы с БД командой `docker-compose up`
3. Запустите работу базы postgreSQL в контейнере командой `docker exec -it app_db psql -U app -W app app`
В открывшееся поле ввода пароля введите пароль: `pass`
4. Запустите работу приложения командой `java -jar aqa-shop.jar`
5. Запустите симулятор банковских серверов (для имитации ответа на запросы) командой ` npm start`
В логах отобразится информация об имеющихся в БД картах:

```
  { number: '4444 4444 4444 4441', status: 'APPROVED' },
  { number: '4444 4444 4444 4442', status: 'DECLINED' }
```

6. Запустите тестовые методы командой `./gradlew clean test`
7. Запустите команду `./gradlew allureReport для генерации отчета о тестировании в Allure`

## Лицензия

Copyright [Альфа-Банк] 
Лицензия Альфа-Банка на разработку информационных систем:
https://alfabank.ru/f/3/about/licence_and_certificate/lic.pdf
