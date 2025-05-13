[Английский](./README.md) | [简体中文](./README-CN.md) | Русский

# EMQX

[![GitHub Release](https://img.shields.io/github/release/emqx/emqx?color=brightgreen&label=Release)](https://github.com/emqx/emqx/releases)
[![Build Status](https://github.com/emqx/emqx/actions/workflows/_push-entrypoint.yaml/badge.svg)](https://github.com/emqx/emqx/actions/workflows/_push-entrypoint.yaml)
[![Slack](https://img.shields.io/badge/Slack-EMQ-39AE85?logo=slack)](https://slack-invite.emqx.io/)
[![Discord](https://img.shields.io/discord/931086341838622751?label=Discord&logo=discord)](https://discord.gg/xYGf3fQnES)
[![X](https://img.shields.io/badge/Follow-EMQ-1DA1F2?logo=x)](https://x.com/EMQTech)
[![YouTube](https://img.shields.io/badge/Subscribe-EMQ-FF0000?logo=youtube)](https://www.youtube.com/channel/UC5FjR77ErAxvZENEWzQaO5Q)

EMQX — это самая масштабируемая и надежная MQTT-платформа в мире, разработанная для высокопроизводительной, надежной и безопасной инфраструктуры данных IoT. Она поддерживает MQTT 5.0, 3.1.1 и 3.1, а также другие протоколы, такие как MQTT-SN, CoAP, LwM2M и MQTT через QUIC. EMQX позволяет подключать миллионы устройств IoT, обрабатывать и маршрутизировать сообщения в режиме реального времени, а также интегрироваться с широким спектром внутренних систем данных. Он идеально подходит для приложений в области искусственного интеллекта, IoT, промышленного IoT (IIoT), подключенных транспортных средств, умных городов и т. д.

**Начиная с версии 5.9.0, EMQX объединила все функции предыдущих версий Open Source и Enterprise в единое мощное предложение с лицензией Business Source License (BSL) 1.1.**

Если вы хотите понять, почему мы внесли это изменение, прочтите эту [запись в блоге](https://www.emqx.com/en/news/emqx-adopts-business-source-license).

Пожалуйста, перейдите в раздел [Лицензия](#License) для получения более подробной информации о BSL 1.1.

## Ключевые особенности

EMQX предоставляет мощный набор возможностей для современных подключенных систем:

### Комплексная поддержка протоколов

- Полная поддержка MQTT v5.0, v3.1.1 и v3.1.
- MQTT через QUIC: используйте преимущества QUIC для более быстрого установления соединения, уменьшения блокировки начала очереди и бесшовной миграции соединения.
- Поддержка других протоколов IoT, таких как LwM2M, CoAP, MQTT-SN и других, через шлюзы.

### Масштабируемость и высокая доступность

- Подключение более 100 миллионов одновременных MQTT-клиентов к одному кластеру.
- Обработка миллионов сообщений в секунду с задержкой менее миллисекунды.
- Кластеризация без ведущего узла для высокой доступности и отказоустойчивости.

### Мощный механизм правил и интеграция данных

- Механизм правил на основе SQL для обработки, преобразования, обогащения и фильтрации данных в реальном времени.
- Бесшовная передача данных и интеграция с более чем 50 облачными сервисами и корпоративными системами, включая:
  - **Очереди сообщений**: Kafka, RabbitMQ, Pulsar, RocketMQ и т. д.
  - **Базы данных**: PostgreSQL, MySQL, MongoDB, Redis, ClickHouse, InfluxDB и т. д.
  - **Облачные сервисы**: AWS Kinesis, GCP Pub/Sub, Azure Event, Confluent Cloud и другие.
- Поддержка веб-хуков для простой интеграции с пользовательскими сервисами.

### Надежная защита

- Безопасные соединения с использованием TLS/SSL и WSS.
- Гибкие механизмы аутентификации: имя пользователя/пароль, JWT, PSK, сертификаты X.509 и т. д.
- Гибкий контроль доступа с помощью ACL.
- Интеграция с внешними базами данных аутентификации (LDAP, SQL, NoSQL).

### Расширенные возможности наблюдаемости и управления:

- Комплексный мониторинг с помощью Prometheus, Grafana и OpenTelemetry.
- Подробные возможности ведения журналов и трассировки.
- Удобная панель управления для обзора и управления кластером.
- Богатый HTTP API для автоматизации и интеграции со сторонними системами.

### Расширяемость

- Возможность использования плагинов для расширения функциональности.
- Хуки для настройки поведения на различных этапах жизненного цикла сообщения.

### Полный функционал для всех:

- С лицензией BSL 1.1 (начиная с версии 5.9.0) все функции, включая те, которые ранее были эксклюзивными для корпоративной версии, доступны всем разработчикам.

## Начало работы

### Попробуйте EMQX Cloud

Самый простой способ настроить EMQX — это развернуть его с помощью EMQX Cloud. Вы можете [попробовать EMQX Cloud бесплатно](https://www.emqx.com/en/signup?utm_source=github.com&utm_medium=referral&utm_campaign=emqx-readme-to-cloud&continue=https://cloud-intl.emqx.com/console/deployments/0?oper=new).

- [EMQX Serverless](https://www.emqx.com/en/cloud/serverless-mqtt)
- [EMQX Dedicated](https://www.emqx.com/en/cloud/dedicated)
- [EMQX BYOC](https://www.emqx.com/en/cloud/byoc)

### Запуск EMQX с использованием Docker

```bash
docker run -d --name emqx \
  -p 1883:1883 -p 8083:8083 -p 8084:8084 \
  -p 8883:8883 -p 18083:18083 \
  emqx/emqx-enterprise:latest
```

Далее следуйте инструкциям в руководстве по [установке EMQX с помощью Docker](https://docs.emqx.com/en/emqx/latest/deploy/install-docker.html).

### Запуск кластера EMQX на Kubernetes

Пожалуйста, обратитесь к официальной документации [EMQX Operator](https://docs.emqx.com/en/emqx-operator/latest/getting-started/getting-started.html) для получения подробной информации.

### Скачать EMQX

Если вы предпочитаете устанавливать и управлять EMQX самостоятельно, вы можете загрузить последнюю версию с [официального сайта](https://www.emqx.com/en/downloads-and-install/enterprise).

Дополнительные варианты установки см. в [документации по установке EMQX](https://docs.emqx.com/en/emqx/latest/deploy/install.html).

## Документация

EMQX (развертывание на собственных серверах/ресурсах): [docs.emqx.com/en/emqx/latest](https://docs.emqx.com/en/emqx/latest/).

EMQX Cloud: [docs.emqx.com/en/cloud/latest](https://docs.emqx.com/en/cloud/latest/).

## Участие в разработке

Пожалуйста, ознакомьтесь с нашим [руководством по участию в разработке](./CONTRIBUTING.md).

Для более организованных предложений по улучшению вы можете отправлять пулл-реквесты в [EIP](https://github.com/emqx/eip).

## Сообщество

- Следите за нами в: [X](https://x.com/EMQTech), [YouTube](https://www.youtube.com/channel/UC5FjR77ErAxvZENEWzQaO5Q).
- Задавайте вопросы: [Обсуждения GitHub](https://github.com/emqx/emqx/discussions) или [Сообщество EMQX в Slack](https://slack-invite.emqx.io/).
- Сообщайте об ошибках: [Проблемы GitHub](https://github.com/emqx/emqx/issues).
- Discord: [Сервер EMQX в Discord](https://discord.gg/x55DZXE).

## Ресурсы

- Веб-сайт EMQX: [emqx.com](https://www.emqx.com/)
- Блог EMQX: [emqx.com/en/blog](https://www.emqx.com/en/blog)
- Программирование MQTT-клиентов: [Учебные пособия](https://www.emqx.com/en/blog/category/mqtt-programming)
- MQTT SDK: [Популярные SDK](https://www.emqx.com/en/mqtt-client-sdk)
- Кроссплатформенный клиент MQTT: [MQTTX](https://mqttx.app/)

## Сборка из исходного кода

Ветка master отслеживает последнюю версию 5.

- EMQX 5.4 и новее можно собрать с помощью OTP 25 или 26.
- EMQX 5.9+ можно собрать с помощью OTP 27.

```bash
git clone [https://github.com/emqx/emqx.git](https://github.com/emqx/emqx.git)
cd emqx
make
_build/emqx-enterprise/rel/emqx/bin/emqx console
```

Для версий 4.2 или более ранних релиз должен быть собран из другого репозитория.

```bash
git clone [https://github.com/emqx/emqx-rel.git](https://github.com/emqx/emqx-rel.git)
cd emqx-rel
make
_build/emqx/rel/emqx/bin/emqx console
```

## Пути последовательного обновления с версии 5.0

Ниже приведена матрица поддерживаемых путей последовательного обновления с версии 5.0.

- Номера версий, заканчивающиеся на `?`, например `6.0?`, являются будущими выпусками.
- ✅: Поддерживается или планируется поддержка.
- ⚠️: Возможны проблемы, требующие ручного решения.
- ❌: Не поддерживается.
- 🔄: Предварительная поддержка для будущих версий.

Подробную информацию см. в примечаниях к релизу.

| С \ На   | 5.1  | 5.2  | 5.3  | 5.4  | 5.5  | 5.6  | 5.7  | 5.8  | 5.9   | 5.10? | 6.0?  |
|----------|------|------|------|------|------|------|------|------|-------|-------|-------|
| 5.0      | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ⚠️[1]  | ❌[2] | ❌[2] |
| 5.1      | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ✅    | ❌[2] | ❌[2] |
| 5.2      |      | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ✅    | ❌[2] | ❌[2] |
| 5.3      |      |      | ✅   | ✅   | ✅   | ✅   | ✅   | ✅   | ✅    | ❌[2] | ❌[2] |
| 5.4      |      |      |      | ✅   | ✅   | ⚠️    | ✅   | ✅   | ✅    | ✅    | 🔄    |
| 5.5      |      |      |      |      | ✅   | ⚠️    | ✅   | ✅   | ✅    | ✅    | 🔄    |
| 5.6      |      |      |      |      |      | ✅   | ✅   | ✅   | ✅    | ✅    | 🔄    |
| 5.7      |      |      |      |      |      |      | ✅   | ✅   | ✅    | ✅    | 🔄    |
| 5.8      |      |      |      |      |      |      |      | ✅   | ✅    | ✅    | 🔄    |
| 5.9      |      |      |      |      |      |      |      |      | ✅    | ✅    | ✅    |
| 5.10?    |      |      |      |      |      |      |      |      |       | ✅    | ✅    |
| 6.0?     |      |      |      |      |      |      |      |      |       |       | ✅    |

- [1] Старые конфигурации ограничителя должны быть удалены из конфигурационных файлов (`etc/emqx.conf` и `data/configs/cluster-override.conf`) перед обновлением.
- [2] Таблица маршрутизации до версии 5.4 будет удалена. Сначала обновитесь до версии 5.9, затем выполните полный перезапуск кластера (не последовательный) перед обновлением до версии 5.10 или более поздней.

## Лицензия

### Важное обновление лицензии

Начиная с версии **5.9.0**, EMQX перешла с Apache 2.0 на Business Source License (BSL) 1.1.

### Требование лицензии для кластеризации (версия 5.9.0+)

Начиная с EMQX v5.9.0, из-за изменения лицензии и объединения всех функций, для развертывания кластера EMQX (более 1 узла) требуется загрузка файла лицензии.

Пожалуйста, обратитесь к следующим ресурсам для получения подробной информации о приобретении лицензии, ее применении и особенностях BSL 1.1.

- **Новости**: [EMQX принимает Business Source License](https://www.emqx.com/en/news/emqx-adopts-business-source-license)
- **Блог**: [Принятие Business Source License для ускорения инноваций в MQTT и ИИ](https://www.emqx.com/en/blog/adopting-business-source-license-to-accelerate-mqtt-and-ai-innovation)
- **FAQ**: [Часто задаваемые вопросы о лицензии EMQX](https://www.emqx.com/en/content/license-faq)
