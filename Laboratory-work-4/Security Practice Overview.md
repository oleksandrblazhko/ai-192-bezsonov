
## Огляд практики безпеки
Практика вимог безпеки (SR) зосереджується на вимогах безпеки, які є важливими в контексті безпечного програмного забезпечення. Перший тип стосується типового програмного забезпечення-відповідні вимоги, щоб визначити цілі та очікування щодо захисту, послуг та дані в основі програми. Другий тип стосується вимог щодо організацій-постачальників, які є частиною контексту розвитку застосування, зокрема для зовнішньої розробки. Важливо впорядкувати очікування з точки зору безпечного розвитку, оскільки
аутсорсинг розробки можуть мати значний вплив на безпеку програми. Безпека cторонніх (технічніх) бібліотек є частиною потоку ланцюгів постачання програмного забезпечення (див Secure Build), і це не включено в цю практику.

## Огляд потоків
### Потік A – Вимоги до програмного забезпечення
Вимоги до програмного забезпечення визначають цілі та очікування щодо захисту
сервіс і дані в основі програми.

### Потік B – Безпека постачальника
Безпека постачальника стосується вимог, які стосуються постачальника
організації в контексті розробки програми, зокрема
для аутсорсингової розробки.

## Огляд діяльності

| Потік А <br/> Вимоги до програмного забезпечення | Потік Б <br/> Безпека постачальника|
|:-----------:|:---------:|

<br/>
<br/>

<table>
    <thead>
        <tr>
            <th colspan=2 align="left">Рівень зрілості 1 <br/>
Розглянемо безпеку чітко під час процесу вимог до програмного забезпечення.</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">Цілі безпеки додатків високого рівня 
відповідають функціональним вимогам.</td>
            <td align="center">Оцініть постачальника на основі
організаційні вимоги безпеки.</td>
        </tr>
    </tbody>
</table>

<br/>
<br/>

<table>
    <thead>
        <tr>
            <th colspan=2 align="left">Рівень зрілості 2 <br/>
Підвищте деталізацію вимог безпеки, виходячи з бізнес-логіки та відомих ризиків.</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">Структуровані вимоги безпеки є
доступні та використовуються командами розробників.</td>
            <td align="center">Включіть безпеку в угоди з постачальниками
щоб забезпечити дотримання
організаційні вимоги.</td>
        </tr>
    </tbody>
</table>
<br/>
<br/>

<table>
    <thead>
        <tr>
            <th colspan=2 align="left">Рівень зрілості 3 <br/>
Обов’язковий процес вимог безпеки для всіх програмних проектів і залежностей третіх сторін.</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">Створіть структуру вимог до продукту
команд для використання.</td>
            <td align="center">Забезпечте належне покриття безпеки для зовнішніх
постачальників, поставивши чіткі цілі.</td>
        </tr>
    </tbody>
</table>

## Потік A – Вимоги до програмного забезпечення
Рівень зрілості 1
### Вигода
Розуміння основних вимог безпеки під час розробки
### Діяльність
Виконайте аналіз функціональних вимог проекту програмного забезпечення. Визначте відповідні вимоги безпеки (тобто очікування) для цієї функції, обґрунтувавши бажану конфіденційність, цілісність або доступність послуги або даних, які пропонує проект програмного забезпечення. Вимоги вказують на мету (наприклад, «персональні дані для процесу реєстрації мають передаватися та безпечно зберігатися»), але не на фактичний захід для досягнення мети (наприклад, «використовувати TLSv1.2 для безпечної передачі»).
Водночас перегляньте функціональність з точки зору зловмисника, щоб зрозуміти, як нею можна зловживати. Таким чином ви можете визначити додаткові захисні вимоги для поточного проекту програмного забезпечення.
Цілі безпеки можуть стосуватися певних функцій безпеки, які потрібно додати до програми (наприклад, «Постійно ідентифікувати користувача програми») або загальної якості та поведінки програми (наприклад, «Переконайтеся, що особисті дані належним чином захищено під час передачі ”), що не обов’язково призводить до нових функцій. Дотримуйтеся хороших практик для написання вимог безпеки. Зробіть їх конкретними, вимірними, дієвими, релевантними та обмеженими за часом (SMART). Стережіться додавання вимог надто загального призначення, які не стосуються конкретної програми (наприклад, програма повинна захищати від OWASP Top 10). Хоча вони можуть бути правдивими, вони не додають цінності дискусії.

<br/>

| Чи вказують команди проекту вимоги безпеки під час розробки? |
|-----------|

<br/>

| Критерії якості |
|-----------|
| • Команди виводять вимоги безпеки з функціональних вимог і клієнта або проблеми організації <br/> • Вимоги безпеки є конкретними, вимірними та обґрунтованими <br/> • Вимоги безпеки відповідають базовому рівню організації|

<br/>

| Відповіді |
|-----------|
|Немає |
|Так, для деяких програм |
|Так, принаймні на половину заявок |
|Так, для більшості або всіх програм |

<br/>

## Потік A – Вимоги до програмного забезпечення
Рівень зрілості 2
### Вигода
Узгодження вимог безпеки з іншими типами вимог
### Діяльність
Вимоги безпеки можуть виникати з інших джерел, зокрема політики та законодавства, відомих проблем у додатку, а також даних із показників і відгуків. На цьому рівні необхідно досягти більш систематичного виявлення вимог безпеки шляхом аналізу різних джерел таких вимог. Переконайтеся, що з цих джерел надходять відповідні дані, щоб допомогти визначити вимоги. Наприклад, організовуйте інтерв’ю або мозковий штурм (наприклад, у випадку політики та законодавства), аналізуйте історичні журнали чи системи вразливостей.
Використовуйте структуровану нотацію вимог безпеки для різних програм і відповідний формалізм, який добре інтегрується з тим, як ви визначаєте інші (функціональні) вимоги для проекту. Це може означати, наприклад, розширення аналітичних документів, написання історій користувачів тощо.
Коли вказуються вимоги, важливо забезпечити, щоб ці вимоги були враховані під час розробки продукту. Налаштуйте механізм, щоб стимулювати або змусити команди проекту відповідати цим вимогам у продукті. Наприклад, позначте вимоги пріоритетами або впливайте на обробку вимог, щоб забезпечити достатній рівень безпеки (при цьому балансуючи з іншими нефункціональними вимогами).
<br/>

| Ви визначаєте, структуруєте та включаєте пріоритети в артефакти процесу збору вимог безпеки? |
|-----------|

<br/>

| Критерії якості |
|-----------|
| • Вимоги безпеки враховують специфічні знання домену, коли застосування політики та вказівок для розробки продукту <br/> • До процесу визначення вимог залучені предметні експерти <br/> • У вас є узгоджена структурована нотація для вимог безпеки <br/> • Команди розробників мають чемпіона безпеки, присвяченого аналізу безпеки вимоги та результати|

<br/>

| Відповіді |
|-----------|
|Немає|
|Так, деякий час|
|Так, принаймні половину часу|
|Так, більшість або весь час|

<br/>

## Потік A – Вимоги до програмного забезпечення

Рівень зрілості 3

### Вигода
Ефективне та ефективне виконання вимог безпеки у вашій організації

### Діяльність
Налаштуйте структуру вимог безпеки, щоб допомогти проектам отримати відповідний і повний набір вимог для свого проекту. Ця основа розглядає різні типи вимог і джерела вимог. Він має бути адаптований до організаційних звичок і культури, а також забезпечувати ефективну методологію та керівництво для виявлення та формування вимог.
Структура допомагає проектним групам підвищити ефективність і результативність розробки вимог. Він може забезпечувати категоризацію загальних вимог і низку повторно використовуваних вимог. Пам’ятайте, що хоча бездумне копіювання неефективне, факт наявності потенційно відповідних вимог, про які можна міркувати, часто є продуктивним.
Структура також дає чіткі вказівки щодо якості вимог і формалізує їх опис. Для історій користувачів, наприклад, конкретні вказівки можуть пояснити, що описувати у визначенні готового, готового, описі історії та критеріях прийняття.
<br/>

| Чи використовуєте ви структуру стандартних вимог для оптимізації виявлення вимог безпеки? |
|-----------|

<br/>

| Критерії якості |
|-----------|
| • Для проектних груп доступна структура вимог безпеки <br/> • Структура класифікується за загальними вимогами та на основі стандартів вимоги <br/> •Структура містить чіткі вказівки щодо якості вимог і способів описати їх <br/> • Фреймворк адаптується до конкретних вимог бізнесу|

<br/>

| Відповіді |
|-----------|
|Немає|
|Так, для деяких програм|
|Так, принаймні на половину заявок|
|Так, для більшості або всіх програм|

<br/>

## Потік B – Безпека постачальника
Рівень зрілості 1

### Вигода
Прозорість практик безпеки ваших постачальників програмного забезпечення

### Діяльність
Компетентність у сфері безпеки та звички зовнішніх постачальників, які беруть участь у розробці вашого програмного забезпечення, можуть мати значний вплив на стан безпеки кінцевого продукту. Отже, важливо знати та оцінювати своїх постачальників на цьому фронті. 

Проведіть оцінку постачальників, щоб зрозуміти сильні та слабкі сторони ваших постачальників. Скористайтеся базовим контрольним списком або проведіть співбесіди, щоб переглянути їхні типові практики та результати. Це дає вам уявлення про те, як вони організовуються та елементи, щоб оцінити, чи потрібно вживати додаткових заходів для пом’якшення потенційних ризиків. В ідеалі поговоріть з представниками різних ролей в організації або навіть влаштуйте для цього невелику оцінку зрілості. Сильні постачальники запустять власну програму забезпечення програмного забезпечення та зможуть відповісти на більшість ваших запитань. Якщо постачальники мають слабкі компетенції у сфері безпеки програмного забезпечення, обговоріть з ними, як і в якому обсязі вони планують працювати над цим, і оцініть, чи достатньо цього для вашої організації. 

Постачальник програмного забезпечення може працювати над проектом із низьким ризиком, але це може змінитися.Важливо, щоб ваші постачальники розуміли і відповідали схильності до ризику, а також могли відповідати вашим вимогам у цій сфері. Чітко поясніть, чого ви очікуєте від них, і чітко обговоріть це.

<br/>

| Чи перевіряють зацікавлені сторони співробітництво постачальників на вимоги безпеки і методології? |
|-----------|

<br/>

| Критерії якості |
|-----------|
| • Ви розглядаєте можливість включити конкретні вимоги безпеки, дії та процеси під час створення сторонніх угод <br/> • Доступна анкета для постачальників, яка використовується для оцінки сильних і слабких сторін ваших постачальників|

<br/>

| Відповіді |
|-----------|
|Немає|
|Так, деякий час|
|Так, принаймні половину часу|
|Так, більшість або весь час|

<br/>

## Потік B – Безпека постачальника
Рівень зрілості 2

### Вигода
Чітко визначені обов’язки постачальників програмного забезпечення щодо безпеки

### Діяльність
Збільште вашу впевненість у спроможності ваших постачальників щодо безпеки програмного забезпечення. Обговоріть конкретні обов’язки та очікування від ваших постачальників і вашої власної організації та укладіть договір з постачальником. Відповідальністю можуть бути конкретні вимоги до якості або конкретні завдання, а мінімальні послуги можуть бути детально описані в Угоді про рівень обслуговування (SLA). Прикладом вимог до якості є те, що вони постачатимуть програмне забезпечення, захищене від OWASP Top 10, і якщо будуть виявлені проблеми, їх буде виправлено. Приклад завдання полягає в тому, що вони повинні виконувати безперервний статичний аналіз коду або виконувати незалежний тест на проникнення перед основним випуском. Угода передбачає зобов’язання та обмеження на випадок виникнення важливої ​​проблеми.

Після того, як ви запровадили це для кількох постачальників, працюйте над стандартною угодою для постачальників, яка ляже в основу ваших переговорів. Ви можете відхилятися від цієї стандартної угоди в кожному конкретному випадку, але це допоможе вам переконатися, що ви не пропустите важливі теми.
<br/>

| Чи виконують постачальники обов’язки щодо безпеки та показники якості угод про рівень обслуговування, визначених організацією? |
|-----------|

<br/>

| Критерії якості |
|-----------|
| • Ви обговорюєте вимоги безпеки з постачальником під час створення угод з постачальником <br/> • Угоди з постачальниками містять конкретні вказівки щодо усунення дефектів безпеки протягом узгодженого періоду часу <br/> • Організація має шаблонну угоду про обов’язки та рівні обслуговування для ключових процесів безпеки постачальника <br/> • Ви вимірюєте ключові показники ефективності|

<br/>

| Відповіді |
|-----------|
|Немає|
|Так, деякий час|
|Так, принаймні половину часу|
|Так, більшість або весь час|

<br/>

## Потік B – Безпека постачальника
Рівень зрілості 3

### Вигода
Узгодження практики розробки програмного забезпечення з постачальниками для обмеження безпеки ризики

### Діяльність
Найкращий спосіб звести до мінімуму ризик проблем із програмним забезпеченням — це максимально узгодити та тісно інтегрувати різні сторони. З точки зору процесу, це означає використання подібних парадигм розвитку та впровадження регулярних етапів для забезпечення належного узгодження та якісного прогресу. З точки зору інструментів, це може означати використання схожих середовищ збірки, перевірки та розгортання, а також спільний доступ до інших допоміжних інструментів (наприклад, вимог, інструментів архітектури або сховищ коду).

Якщо постачальники не можуть досягти цілей, які ви поставили, запровадьте компенсаційні засоби контролю, щоб загалом ви досягли своїх цілей. Виконуйте додаткові дії (наприклад, моделюйте загрози перед початком фактичного циклу впровадження) або запроваджуйте додаткові інструменти (наприклад, аналіз бібліотеки третьої сторони під час прийняття рішення). Чим більше постачальники відхиляються від ваших вимог, тим більше роботи потрібно буде компенсувати.
<br/>

| Чи дотримуються постачальники стандартних заходів безпеки та інструментів і процесів розробки програмного забезпечення, які використовує організація? |
|-----------|

<br/>

| Критерії якості |
|-----------|
| • Постачальник має захищений SDLC, який включає безпечну збірку, безпечне розгортання, дефект управління та управління інцидентами, які відповідають тим, які використовуються у вашій організації <br/> • Перед кожним великим випуском ви перевіряєте, чи рішення відповідає цілям якості та безпеки <br/> • Якщо стандартні процеси перевірки недоступні, ви використовуєте компенсаційні елементи керування, такі як аналіз складу програмного забезпечення та незалежне тестування на проникнення|

<br/>

| Відповіді |
|-----------|
|Немає|
|Так, деякий час|
|Так, принаймні половину часу|
|Так, більшість або весь час|

<br/>
