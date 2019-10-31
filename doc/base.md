# UBCONFIG

## 1. Общий сведения

### 1.1 Назначение

Проект предназначен для облегчения администрирования и конфигурирования
операционной системы, путем наглядного графического отображение настроек
и спец.интерфейсов взаимодействия.

### 1.2 Аудитория

Разработка ориентирована на разработчиков-визуализаторов, системных администраторов и обычных пользователей. Для первых предусмотрена возможность создание графических объектов, которые в последствие смогут использовать администраторы в своих модулях. Для вторых проект предоставит возможности форматирования вывода системной информаций, быстрое управление операциями, а также платформу для разработки собственных модулей. Для третьих продвинутую визуализация объектов и процессов системы, подготовленные разработчиками-визуализаторов.

### 1.3 Формат

Проект  представляет собой простой Web-интерфейс с двумя уровнями вложаности. Первый уровень
отображает работу с конкретным модулем, который можно выбрать в виде пункта меню. В свою очередь модуль
разбит на части, которые отображает второй уровень в виде дополнительного меню навигаций в формаету вкладок.
Для подготовки графических обьектов разработчик-визуализатор сможет создать структуру в отдельном каталоги 
файлового дерева проекта, которая состоит из одного катлога и двух файлов(код элемента и служебная информация о нем).
Отдельный каталог будет подготовлен для добавление модулей. Он состоит из каталога,служебного файла и подкатолога, который
содержит файлы с кодом, отображающие собой вкладки этого модуля.

### 1.4 Дружелюбие

Разработка должна представлять собой интуитивно понятную навигацию по вложенности, путем использование
привычных для пользователя клише "выделение при наведении", а также отклика на нажатие в виде оповещения
о загрузке выбранного компонента. Внутри модуля должна имеется возможность вызова справочной информации о нем
оставленную автором. Для администраторов необходимо предоставить руководство, по оформлению шаблонов и интерфейс
вызова информаций о готовых к использованию визуальных объектах. Разработчик-визуализатор должен иметь доступ
к руководству по описанию визуальных объектов.

## 2. Требование

* 1. Наглядный и интуитивнно понятный интерфейс для отображение системной информацией и способам взаимодеиствия с ней
* 2. Модульная система, позволяющия реализовать необходимый функционал для взаимодействия с ОС
* 3. Модульная подсистема, позволяющия заготавливать визуальные обьекты для использование в основных модулях
* 4. Распределение прав использование модулей среди пользователей UBCONFIG

## 3. Компоненты проекта

### 3.1 Информационный

Компонент специализируеющися на хранение и обороте информации об компонентах UBCONFIG. Содержит набор функций парсеров
для передачи данных другим компонентам. (Вспомогательный компонент общего назначения)

### 3.2 Рендер

Компонент отвечает за построение внешнего вида интерфейса(выстраевание блоков разметки, подключение стилей и сценариев)
и формирование человеческих URL. Содержит функций отрисовки и перерисовки в браузер.
(Компонент реализует требования 1)

#### 3.3 Перехватчик данных 

Компонент перехватывает данные со сценариев Sh исполнаемые на серверы и внедряют их в код разметки. Содержит функций
по перехвату, отбора и внедрения данных.
(Компонет реализует часть требования 2)

### 3.4 Обработчик запросов

Компонент по контролю за исполнение сцериев Sh направленые на изменение в системе и использующие данные из web-формы. Содержит функции по управление исполнением и получием отчета о нем, а также обработки данных с web-формы.
(Компонет реализует часть требования 2)

#### 3.5 Транслятор визуальных обьктов

Компонент по внедрению заготовленых визуальных обьектов.
(Компонет реализует требования 3)


### 3.6 Управление пользователями

Компонент по манипуляций базой данных с пользователями UBCONFIG.(Вспомогательный компонент для 3.7)

### 3.7 Контроль прав доступа

Компонент по управлению и контролю за доступом к компонентам UBCONFIG. (Компонет реализует требования 4)