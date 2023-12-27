# Коллективный проект команды 5.1-2 на тему "Спектры отражения углеродистых астероидов:"

Данный проект создан для того, чтобы создать базу данных в сфере оптических характеристик углеродистых астероидов.

## Описание проекта

CSV файл по данной теме - [Kaggle](https://www.kaggle.com/datasets/michaelbryantds/reflectance-spectra-of-carbonaceous-asteroids)

### Структура
>Эти данные взяты из представленной работы: "Космическое выветривание 3-мкм филлосиликатов, индуцированное импульсным лазерным
облучением".Данные были получены в ходе эксперимента, в котором лазер светил на два разных материала (CI и CM), и измерялось количество облученного света.

Количество лазерных импульсов варьировалось от 0 до 5 импульсов, а условия варьировались между окружающей средой и вакуумом.

### Реализация
>Для использования базы данных, созданной на основе датасета с данными по спектрам отражения углеродистых астероидов, вы можете проводить анализ спектральных характеристик, идентифицировать уникальные особенности углеродистых астероидов и использовать эти данные для классификации, 
>изучения химического состава или прогнозирования их поведения в космическом пространстве.
>Также, эта база данных может быть интегрирована в инструменты 

## Процесс создания коллективного проекта

### Создание базы данных
>На данном этапе выполнения коллективного проекта, была создана база данных, с помощь функции create model в MySQL Workbench. Она содержит пять таблиц, сформированных на основе, предоставленных CSV файлов, в которых указана информация об отражении астероидов, надстройках лазера, количестве импульсов и т. п.

Фрагмент кода создания базы данных.

CREATE SCHEMA IF NOT EXISTS Reflectance DEFAULT CHARACTER SET utf8 ;
USE Reflectance ;

-- Table Reflectance. LaserIrradiation

CREATE TABLE IF NOT EXISTS Reflectance. LaserIrradiation (
  Wavelength DOUBLE NOT NULL,
  Type VARCHAR(2) NOT NULL,
  Fresh DOUBLE NULL,
  Pulse1 DOUBLE NULL,
  Pulse2 DOUBLE NULL,
  Pulse3 DOUBLE NULL,
  Pulse5 DOUBLE NULL,
  PRIMARY KEY (Wavelength, Type))
ENGINE = InnoDB;

-- Table Reflectance.Parameters

CREATE TABLE IF NOT EXISTS Reflectance.Parameters (
  Type VARCHAR(2) NOT NULL,
  LaserPulses INT NOT NULL,
  NormalizedIntensity DOUBLE NULL,
  Slope DOUBLE NULL,
  BandDepth DOUBLE NULL,
  PRIMARY KEY (Type, LaserPulses))
ENGINE = InnoDB;


Код был написан с помощью функции Forward Engineering. В результате получается база данных с название Reflectance и добавляет в нее таблицы LaserIrradiation, Parameters, ScaledReflectance, VacuumAmbientDiff и DifferenceSpectra.


### Создание ER-диаграммы
>


### Нормализация данных
>

### Заполнение БД данными
>
### Описать проект , созданную БД (документация) и участие (авторство) каждого члена команды
>
### Визуализация данных в Python
>
### Тестирование БД
>

## Дополнительные задачи

### Web-сервер [db4free.net](https://db4free.net/)
>

### Создать Jupiter notebook для извлечения основных данных из созданной базы данных.
>
### Создать Docker для разворачивания созданной базы данных
>



## Участники проекта 

* [Насткин Сергей Дмитриевич ](https://github.com/nstk24)

    - [x] Распределение задач между участниками проекта;
    - [x] Отслеживание прогресса выполнения задач;
    - [x] Создание коллективного проекта с доступом на редактирование;
    - [x]  Создание БД и ее ER-диаграммы;
    - [x] Тестирование и проверка выполнения задач.
    - [ ] Создать Docker для разворачивания созданной базы данных
    
* [Шишков Владислав Александрович ](https://github.com/MiniHero95)
  
    - [x] Визуализация данных на Python;
    - [x] Создать Jupiter notebook для извлечения основных данных из созданной базы данных.
    - [x] Тестирование и проверка выполнения задач.
   
* [Дмитриенко Григорий Алексеевич](https://github.com/tenitskayav)
  
    - [x] Тестирование БД.
    - [x] Тестирование и проверка выполнения задач.
    - [ ] Развернуть базу данных на web-сервере [db4free.net](https://db4free.net/);

* [Зибарева Софья Сергеевна](https://github.com/2022-02150)

    - [x] Проверка заполнения данных.
    - [ ] Тестирование и проверка выполнения задач.
    - [ ] Описать проект , созданную БД (документация) и участие (авторство) каждого члена команды

* [Чурсин Егор Владимирович](https://github.com/EhorChursin)
    - [x]  Заполнение БД данными;
    - [ ]  Нормализация данных БД
    - [x]  Тестирование и проверка выполнения задач.
  
    
  
