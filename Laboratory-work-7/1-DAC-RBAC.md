## Крок 1

### Встановіть СКБД PostgreSQL

PostgreSQL вже було встановлено.



## Крок 2

### Створіть термінальну консоль psql через утиліту командного рядка вашої ОС та встановіть з’єднання з БД postgres від імені користувача-адміністратора postgres

Було встановлено з’єднання з БД postgres від імені користувача-адміністратора postgres



## Крок 3

### Зареєструйте нового користувача в СКБД PostgreSQL, назва якого співпадає з вашим прізвищем, наприклад blazhko, і довільним паролем.

Було створено користувача bezsonov з паролем '1234' командою CREATE USER bezsonov WITH PASSWORD '1234'. Командою \du перевірено наявність створеного користувача

![3](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/af6d3736-ae63-4b26-ba0e-2cd1a0d4c8b1)



## Крок 4

### Створіть роль в СКБД PostgreSQL (назва співпадає з вашим прізвищем латинськими літерами) і надайте новому користувачеві можливість наслідувати цю роль.

Роль bezsonov було створено автоматично після створення користувача

![s](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/372ebb19-f6c0-4eaa-9848-1f37e48a65dd)

## Крок 5

### Створіть реляційну таблицю з урахуванням варіанту з таблиці 2.1 від імені користувача-адміністратора.

Було створено таблицю lecturer командою Create table lecturer (l_id integer, name varchar, lecture_name varchar); . За допомогою \dt було перевірено наявність таблиці

![5](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/36ac7a74-c0e5-413f-b154-f2a40cbacd43)

## Крок 6

### Внесіть один рядок в таблицю, використовуючи команду insert into ..., відповідно до варіанту.
![6](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/cb66b8b2-db4f-400f-afdc-7aa568d38964)

## Крок 7

### Додатково створіть ще одну термінальну консоль psql та встановіть з’єднання з БД postgres від імені нового користувача.

Було створено ще одну термінальну консоль psql та  встановлено з’єднання з БД postgres від імені користувача bezsonov

![7](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/7f5a4bd5-3bbf-4eff-96bd-3b51e3376118)

## Крок 8

### Від імені нового користувача виконайте запит на отримання даних з таблиці (select * from таблиця). Запротоколюйте результат виконання команди.

Командою SELECT * FROM lecturer; виконано запит на отримання даних з таблиці. Як бачимо, користувач bezsonov не має доступу до таблиці.

![8](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/3dd661c1-8cd5-47ac-9e98-5ad0ab9755cc)

## Крок 9

### Встановіть повноваження на читання таблиці новому користувачеві.

Командою GRANT SELECT ON lecturer TO bezsonov; було надано повноваження.

![9](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/cc54a477-0965-4750-b2e2-d74fbc8fc4b9)

## Крок 10

### Повторіть крок 8.

Оскільки тепер користувач bezsonov має доступ, то командою SELECT * FROM lecturer; було отримано дані з таблиці lecturer

![10](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/7ba3c7e9-0b74-4167-83fd-fc6bd9e1f874)

## Крок 11

### Зніміть повноваження на читання таблиці для нового користувача.

Командою REVOKE SELECT ON lecturer FROM bezsonov; для користувача bezsonov знято повноваження на читання таблиці lecturer.

![11](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/acb47bb5-9b93-44d8-88a8-ffefd2c34b4e)

## Крок 12

### Повторіть крок 8.

Як бачимо, доступу до читання таблиці немає

![12](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/40ca594f-cc74-41c5-b460-e3ced02a3dc9)


## Крок 13

### Створіть команду оновлення даних таблиці (UPDATE) і виконайте її від імені нового користувача. Проаналізуйте результат виконання команди.

![13](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/2c5898ea-7c7b-47e1-95c5-a47d2fa2b6c7)

## Крок 14

### Встановіть повноваження на оновлення таблиці новому користувачу.

![14](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/d9a47662-f2bf-40fa-82cd-dd6d56836b6e)


## Крок 15

### Повторіть крок 13.

![15](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/428d2c18-4c38-47fc-bc74-1d5c6a994def)


## Крок 16

### Створіть команду видалення запису таблиці (DELETE) і виконайте її від імені нового користувача. Проаналізуйте результат виконання команди.

Повноваження для видалення даних з таблиці відсутні.

![16](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/537d4bdb-a6a8-4db1-a331-4d9bc8fdec54)

## Крок 17

### Встановіть повноваження на видалення таблиці новому користувачеві.

![17](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/6d5adc16-908c-40a0-89c7-97f7a1b80eb2)


## Крок 18

### Повторіть крок 16.

Успішне видалення

![18](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/96a611f4-82a3-420d-991a-b1a590be0714)


## Крок 19

### Зніміть всі повноваження з таблиці для нового користувача.

![19](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/16134403-20d8-4b1c-ac87-db40f07e2f87)

## Крок 20

### Створіть команду внесення запису в таблицю (INSERT) і виконайте її від імені нового користувача. Проаналізуйте результат виконання команди.

Повноваження для додавання даних у таблицю відсутні.

![20](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/8e67fc63-1907-4b58-8fa0-8aa740ab5601)


## Крок 21

### Встановіть повноваження на внесення даних до таблиці для ролі.

![21](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/5ae06ce4-34f7-4cb6-8643-192516085ada)


## Крок 22

### Повторіть крок 20.

Успішне додавання даних

![22](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/80cb4e49-871c-43c6-b4f8-e6a69449ae26)

Перевірка за допомогою SELECT * FROM

![23](https://github.com/oleksandrblazhko/ai-192-bezsonov/assets/79146520/0ba43e33-85ab-4862-8ef1-9495ebec6fb8)

