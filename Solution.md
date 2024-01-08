# Автоматизированные Бизнес-Процессы

## Обработка Заказов
Автоматизация процесса обработки заказов от поступления до выполнения, включая управление запасами и логистику.

## Управление Клиентскими Данными
Синхронизация данных клиентов между CRM и 1C для обеспечения актуальности информации.

## Финансовый Учет
Автоматический обмен финансовой информацией между 1C и SAP для учета и отчетности.

# Использование RabbitMQ и Kafka

## Очереди RabbitMQ
- `order_processing_queue`: Для управления заказами.
- `customer_data_sync_queue`: Для синхронизации данных клиентов.
- `financial_info_queue`: Для обмена финансовой информацией.

## Топики Kafka
- `order_updates`: Отслеживание изменений статуса заказов.
- `customer_updates`: Изменения в данных клиентов.
- `financial_transactions`: Финансовые транзакции и обновления.

# Форматы Обмена Данными  


## XML от SAP   
  
```xml
<FinancialRecord>
  <TransactionId>54321</TransactionId>
  <Amount>1000</Amount>
  <Date>2024-01-08</Date>
  <Type>Invoice</Type>
</FinancialRecord>
```  
  

## JSON из 1C
```json
{
  "orderId": "12345",
  "customerID": "67890",
  "items": [{"productId": "987", "quantity": "3"}],
  "orderDate": "2024-01-08",
  "status": "processing"
}  
  
```
  
    
## Создание таблицы customer_orders
```SQL
CREATE TABLE customer_orders (
    order_id SERIAL PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    status VARCHAR(50),
    total_amount DECIMAL(10, 2)
);
```

