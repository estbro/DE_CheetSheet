# ✨ Шпаргалка по основам DE

## 💡 Что такое OLAP и OLTP?

### OLAP (Online Analytical Processing)
OLAP — технологии и системы, ориентированные на аналитическую обработку больших объемов данных.

**Пример:** Анализ продаж за последние 5 лет для выявления трендов.

**Характеристики:**
- 📊 Многомерные запросы
- 🔍 Фокус на анализ данных
- ⏱️ Медленные транзакции, но масштабируемость
- 🗄️ Пример: ClickHouse, Snowflake

### OLTP (Online Transaction Processing)
OLTP — системы, ориентированные на оперативную обработку транзакций.

**Пример:** Оформление заказа в интернет-магазине.

**Характеристики:**
- 💾 Быстрая обработка транзакций
- 🔒 Четкость и точность данных
- 🛠️ Пример: MySQL, PostgreSQL

## 🔐 Свойства ACID и транзакции

### Свойства ACID:
1. **Atomicity (Атомарность):**
   Все операции транзакции либо выполняются полностью, либо не выполняются вовсе.
   - Пример: Перевод денег между счетами. Если дебетование счета A прошло, но кредитование счета B не удалось, транзакция откатывается.

2. **Consistency (Согласованность):**
   После завершения транзакции база данных остается в корректном состоянии.
   - Пример: Нельзя записать данные, нарушающие уникальный ключ.

3. **Isolation (Изолированность):**
   Параллельные транзакции не влияют друг на друга.
   - Пример: Одновременные изменения одного аккаунта двумя пользователями.

4. **Durability (Долговечность):**
   Результаты транзакции сохраняются даже при сбое системы.
   - Пример: После подтверждения оплаты данные сохраняются, даже если произошел сбой.

## 🛠️ Движки ClickHouse

ClickHouse поддерживает множество движков для хранения данных, включая:

1. **MergeTree** (и его варианты):
   - Основной движок для аналитических запросов.
   - Поддерживает сортировку, сжатие и партиционирование.

2. **Log и TinyLog:**
   - Простые движки для отладки или хранения небольших объемов данных.

3. **Memory:**
   - Данные хранятся только в оперативной памяти.
   - Высокая скорость, но без долговечности.

4. **Kafka и RabbitMQ:**
   - Интеграция с потоковыми платформами для обработки данных в реальном времени.

5. **Join:**
   - Хранение данных для оптимизации джойнов.

## ✅ Плюсы и минусы ClickHouse

### Плюсы:
- ⚡ **Высокая производительность:** Оптимизирован для аналитических запросов.
- 📈 **Масштабируемость:** Подходит для больших объемов данных.
- 💾 **Сжатие данных:** Экономия места на диске.
- ⏱️ **Быстрые агрегаты:** Эффективная обработка запросов с группировками.

### Минусы:
- 📋 **Ограниченная поддержка ACID:** Не подходит для OLTP.
- 🛠️ **Сложность настройки:** Требует опыта и времени для оптимизации.
- 🔄 **Ограниченные возможности обновлений:** Медленная обработка частых изменений данных.
