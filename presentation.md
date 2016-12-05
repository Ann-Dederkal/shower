# SOLID-ний JavaScript

Панує думка, що SOLID-принципи, патерни, та інші підходи, що були придумані для статично-типізованих мов не можна застосовувати для динамічно-типізованих мов. Будемо разом розбивати цей стереотип, та говорити про особливості імплементації SOLID-принципів у JavaScript.

## Plan

1. Мотивація
	1.1 - Популяризація серед JS
	1.2 - Особливості в динаміці
	1.3 - Ознаки поганого проекту
2. Що таке SOLID
	2.1 - Виначення
	2.2 - Автор
3. SRP - Single Responsibility Principle
4. OCP - Open-Closed Principle
5. LSP - Liskov Substitution Principle
6. ISP - Interface Segregation Principle
7. DIP - Dependency Inversion Principle


## 1. Мотивація

### 1.3 - Ознаки поганого проекту

Запахи коду https://uk.wikipedia.org/wiki/%D0%97%D0%B0%D0%BF%D0%B0%D1%85%D0%B8_%D0%BA%D0%BE%D0%B4%D1%83 

The symptoms are:
Rigidity. The design is difficult to change. -  Закрепощенность - Стійкість, жорсткість, незмінність - Сніговий ком
Fragility. The design is easy to break. - Неустойчивость - Крихкість
Immobility. The design is difficult to reuse. - Неподвижность - Неподвижність 
Viscosity. It is difficult to do the right thing. - Вязкость - В'язкість'
Needless complexity. Overdesign. - Невиправдана складність
Needless repetition. Mouse abuse. - Невиправдані повторення 
Opacity. Disorganized expression. - Неопределенность - Непрозорість

## 2. Що таке SOLID

### 2.1 - Виначення

In computer programming, SOLID (single responsibility, open-closed, Liskov substitution, interface segregation and dependency inversion) is a mnemonic acronym introduced by Michael Feathers for the "first five principles" named by Robert C. Martin[1][2] in the early 2000s[3] that stands for five basic principles of object-oriented programming and design. The intention is that these principles, when applied together, will make it more likely that a programmer will create a system that is easy to maintain and extend over time.[3] The principles of SOLID are guidelines that can be applied while working on software to remove code smells by providing a framework through which the programmer may refactor the software's source code until it is both legible and extensible. It is part of an overall strategy of agile and Adaptive Software Development.[3]

3. SRP

Клас повинен мати лише одну причину для змін.

Кожен обов'язок класу - це вісь змін.
Якщо в класу більше одного обов'язку - тоді буде більше однієї причини для зміни цього класу.
Якщо в класу більше одного обов'язку, тоді обов'язки стають зчеплені (зв'язані).
Тоді зміни в одному обов'язку можуть вплинути на можливіть класу відповідати на вимоги іншого обов'язку.


Приклад з прямокутником (площа, малювати)


Як розрізнити, коли клас має більше однієї причини для змін? Інколи це важко помітити.
Люди звикли групувати обов'язки, адже предмети навколо нас мають зазвичай більше одного обов'язку.
Комбайни, телевізори...

Як знати, коли обов'язки потрібно розділяти?
Вісь змін являється віссю змін тільки тоді, коли зміни дійсно відбуваються.