Лабораторная работа #5
====================================================================================================================================================================================================================
Вариант: 3202
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Внимание! У разных вариантов разный текст задания!
### Реализовать консольное приложение, которое реализует управление коллекцией объектов в интерактивном режиме. В коллекции необходимо хранить объекты класса SpaceMarine, описание которого приведено ниже.

#### Разработанная программа должна удовлетворять следующим требованиям:
<ul>
<li>Класс, коллекцией экземпляров которого управляет программа, должен реализовывать сортировку по умолчанию.</li>
<li>Все требования к полям класса (указанные в виде комментариев) должны быть выполнены.</li>
<li>Для хранения необходимо использовать коллекцию типа java.util.HashSet</li>
<li>При запуске приложения коллекция должна автоматически заполняться значениями из файла.</li>
<li>Имя файла должно передаваться программе с помощью: аргумент командной строки.</li>
<li>Данные должны храниться в файле в формате json</li>
<li>Чтение данных из файла необходимо реализовать с помощью класса java.io.BufferedInputStream</li>
<li>Запись данных в файл необходимо реализовать с помощью класса java.io.FileOutputStream</li>
<li>Все классы в программе должны быть задокументированы в формате javadoc.</li>
<li>Программа должна корректно работать с неправильными данными (ошибки пользовательского ввода, отсутсвие прав доступа к файлу и т.п.).</li>
</ul>

#### В интерактивном режиме программа должна поддерживать выполнение следующих команд:
<ul>
<li>help : вывести справку по доступным командам</li>
<li>info : вывести в стандартный поток вывода информацию о коллекции (тип, дата инициализации, количество элементов и т.д.)</li>
<li>show : вывести в стандартный поток вывода все элементы коллекции в строковом представлении</li>
<li>add {element} : добавить новый элемент в коллекцию</li>
<li>update id {element} : обновить значение элемента коллекции, id которого равен заданному</li>
<li>remove_by_id id : удалить элемент из коллекции по его id</li>
<li>clear : очистить коллекцию</li>
<li>save : сохранить коллекцию в файл</li>
<li>execute_script file_name : считать и исполнить скрипт из указанного файла. В скрипте содержатся команды в таком же виде, в котором их вводит пользователь в интерактивном режиме.</li>
<li>exit : завершить программу (без сохранения в файл)</li>
<li>add_if_max {element} : добавить новый элемент в коллекцию, если его значение превышает значение наибольшего элемента этой коллекции</li>
<li>add_if_min {element} : добавить новый элемент в коллекцию, если его значение меньше, чем у наименьшего элемента этой коллекции</li>
<li>history : вывести последние 6 команд (без их аргументов)</li>
<li>count_less_than_melee_weapon meleeWeapon : вывести количество элементов, значение поля meleeWeapon которых меньше заданного</li>
<li>count_greater_than_heart_count heartCount : вывести количество элементов, значение поля heartCount которых больше заданного</li>
<li>filter_by_weapon_type weaponType : вывести элементы, значение поля weaponType которых равно заданному</li>
</ul>

#### Формат ввода команд:
<ul>
<li>Все аргументы команды, являющиеся стандартными типами данных (примитивные типы, классы-оболочки, String, классы для хранения дат), должны вводиться в той же строке, что и имя команды.</li>
<li>Все составные типы данных (объекты классов, хранящиеся в коллекции) должны вводиться по одному полю в строку.</li>
<li>При вводе составных типов данных пользователю должно показываться приглашение к вводу, содержащее имя поля (например, "Введите дату рождения:")</li>
<li>Если поле является enum'ом, то вводится имя одной из его констант (при этом список констант должен быть предварительно выведен).</li>
<li>При некорректном пользовательском вводе (введена строка, не являющаяся именем константы в enum'е; введена строка вместо числа; введённое число не входит в указанные границы и т.п.) должно быть показано сообщение об ошибке и предложено повторить ввод поля.</li>
<li>Для ввода значений null использовать пустую строку.</li>
<li>Поля с комментарием "Значение этого поля должно генерироваться автоматически" не должны вводиться пользователем вручную при добавлении.</li>
</ul>

#### Описание хранимых в коллекции классов:
public class SpaceMarine {
<ol">
  <li>private Long id; //Поле не может быть null, Значение поля должно быть больше 0, Значение этого поля должно быть уникальным, Значение этого поля должно генерироваться автоматически</li>
  <li>Второй элемент</li>
</ol>
}

##### public class Coordinates {

######     private double x; //Значение поля должно быть больше 0

######     private float y; //Значение поля должно быть больше -381

##### }

##### public class Chapter {

######     private String name; //Поле не может быть null, Строка не может быть пустой

######     private String parentLegion;

######     private Integer marinesCount; //Поле не может быть null, Значение поля должно быть больше 0, Максимальное значение поля: 1000

######     private String world; //Поле может быть null

##### }

##### public enum Weapon {

######     HEAVY_BOLTGUN,

######     BOLT_RIFLE,

######     GRENADE_LAUNCHER,

######     INFERNO_PISTOL,

######     MULTI_MELTA;

##### }

##### public enum MeleeWeapon {

######     CHAIN_SWORD,

######     MANREAPER,

######     LIGHTING_CLAW,

######     POWER_BLADE,

######     POWER_FIST;

##### } 
