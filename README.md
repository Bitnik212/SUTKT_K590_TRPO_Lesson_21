# ПРАКТИКУМ 1. ВВЕДЕНИЕ В WPF, XAML РАЗМЕТКА
Цель: формирование навыка создания приложений WPF, изучение языка разметки XAML

- [x] Задание 1. Создание проекта WPF

В задании будет показано, как разработать классическое приложение Windows Presentation Foundation (WPF), включающее элементы, которые являются общими для большинства приложений WPF: разметка XAML (XAML), код программной части, определения приложений, элементы управления, макет и др. 
Создание проекта приложения
Первым шагом является создание инфраструктуры приложения, включающей определение приложения, две страницы и изображение.
Создайте новый проект приложения WPF в Visual C# с именем TestProject1. Для этого откройте Visual Studio и выберите Создать новый проект в меню Приступая к работе.
Откроется диалоговое окно Создание нового проекта (рис.1.1).
В раскрывающемся списке Язык выберите C#.
Выберите шаблон Приложения WPF (платформа .NET Framework) и нажмите кнопку Далее.

Откроется диалоговое окно Настройка нового проекта.
Введите имя проекта TestProject1 и нажмите кнопку Создать (рис.1.2).

Visual Studio создаст проект и откроет конструктор для окна приложения по умолчанию с именем MainWindow.xaml (рис.1.3).

Создайте App.xaml. Этот файл определяет приложение WPF и все ресурсы приложения. Этот файл также используется для указания пользовательского интерфейса, в данном случае MainWindow.xaml, который автоматически отображается при запуске приложения.
Код XAML должен выглядеть следующим образом:

```XAML
<Application x:Class="TestProject1.App"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:local="clr-namespace:TestProject1"
StartupUri="MainWindow.xaml">
<Application.Resources>
</Application.Resources>
</Application>
```
Создайте файл MainWindow.xaml. Этот XAML-файл является главным окном приложения и отображает содержимое, созданное на страницах. Window-класс определяет свойства окна, такие как заголовок, размер или значок, а также обрабатывает события, такие как закрытие или скрытие.
```XAML
<Window x:Class="TestProject1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
    </Grid>
</Window>
```
Измените Window элемент на NavigationWindow , как показано в следующем коде XAML:
```XAML
<NavigationWindow x:Class="TestProject1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
    </Grid>
</NavigationWindow>
```
Это приложение переходит к другому содержимому в зависимости от введенных пользователем данных. Именно поэтому необходимо изменить основное значение Window на NavigationWindow.  
NavigationWindow наследует все свойства Window. NavigationWindow создает экземпляр NavigationWindow класса. 
Удалите Grid элементы между NavigationWindow тегами.
Измените следующие свойства в коде XAML для NavigationWindow элемента:
- Присвойте Title свойству значение " ExpenseIt ".
- Задайте Height для свойства значение 350 пикселей.
- Задайте Width для свойства значение 500 пикселей.

Получится код XAML:
```XAML
<NavigationWindow x:Class="TestProject1.MainWindow"
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
        Title="ExpenseIt" Height="350" Width="500">
</NavigationWindow>
```
Создайте файл MainWindow.xaml.cs
Этот файл является файлом кода программной части, который содержит код для работы с событиями, объявленными в файле MainWindow.xaml. Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.
Измените MainWindow класс на производный от NavigationWindow.
```XAML
*** using (добавленные по умолчанию)
namespace TestProject1
{
    /// <summary>
    /// Логика взаимодействия для MainWindow.xaml
    /// </summary>
    public partial class MainWindow : NavigationWindow
    {
        public MainWindow()
        {
            InitializeComponent();
        }
    }
}
```
***Добавление файлов в приложение***
В этом разделе вы добавите в приложение две страницы и изображение.
Добавьте в проект новую страницу и назовите ее ExpenseItHome.xaml :
В Обозреватель решений щелкните правой кнопкой мыши ExpenseIt узел проекта и выберите команду Добавить > Страницу (рис.1.4).

В диалоговом окне Добавление нового элемента шаблон Page (WPF) уже выбран. Введите имя ExpenseItHome и нажмите кнопку Добавить.
Эта страница является первой страницей, отображаемой при запуске приложения. 
Создайте ExpenseItHome.xaml. Присвойте свойству значение Title "ExpenseItHome".
Задайте для параметра значение DesignHeight 350 пикселей, а для параметра — значение DesignWidth 500 пикселей.
```XAML
</Page x: Class="TestProject1.ExpenseItHome"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" 
      xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 
      xmlns: local="clr-namespace: TestProject1"
      mc:Ignorable="d" 
      d: DesignHeight="350" d: DesignWidth="500"
      Title="ExpenseItHome">
    <Grid>
    </Grid>
</Page> 
```
Создайте файл MainWindow.xaml.
Добавьте Source свойство в NavigationWindow элемент и задайте для него значение " ExpenseItHome.xaml ". Этот набор устанавливается ExpenseItHome.xaml в качестве первой страницы, открытой при запуске приложения
```XAML
<NavigationWindow x: Class="ExpenseIt.MainWindow"
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        Title="ExpenseIt" Height="350" Width="500" Source="ExpenseItHome.xaml">
</NavigationWindow>
```
Также можно задать свойство Source в категории Разное в окне Свойства (рис.1.5).
Добавьте еще одну новую страницу WPF в проект и назовите ее файл ExpenseReportPage.xaml.
Создайте файл ExpenseReportPage.xaml
Присвойте свойству значение Title "ExpenseIt_View_Expense".
Задайте для параметра значение DesignHeight 350 пикселей, а для параметра - значение DesignWidth 500 пикселей.
Файл ExpenseReportPage.xaml теперь выглядит следующим образом:
```XAML
<Page x: Class="TestProject1.ExpenseReportPage"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" 
      xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 
      xmlns: local="clr-namespace: TestProject1"
      mc:Ignorable="d" 
      d: DesignHeight="350" d: DesignWidth="500"
      Title="ExpenseIt_View_Expense">
    <Grid>
    </Grid>
</Page>
```
Код должен выглядеть следующим образом ExpenseItHome:
```XAML
*** using (добавленные по умолчанию)
namespace ExpenseIt
{
    /// <summary>
    /// Interaction logic for ExpenseItHome.xaml
    /// </summary>
    public partial class ExpenseItHome: Page
    {
        public ExpenseItHome ()
        {
            InitializeComponent ();
        }
    }
}
```
И, как и для файла ExpenseReportPage:
```XAML
*** using (добавленные по умолчанию)
namespace ExpenseIt
{
    /// <summary>
    /// Interaction logic for ExpenseReportPage.xaml
    /// </summary>
    public partial class ExpenseReportPage: Page
    {
        public ExpenseReportPage ()
        {
            InitializeComponent ();
        }
    }
}
```
Чтобы выполнить сборку и запуск приложения, нажмите клавишу F5 или выберите начать отладку в меню Отладка.
Закройте приложение, чтобы вернуться в IDE Visual Studio 2019.

- [ ] Задание 2. Создание простой кнопки с обработчиком события

Создайте новый проект «WPFApplication» в IDE Visual Studio 2019.
В строке заголовка формы укажите название окна проекта. Для этого в свойстве окна в Title запишите: Главное окно (рис.1.7).

В данном задании будет сформирован навык работы с такими элементами управления, как ТеxtBox, Label и Button.
TextBox представляет поле для ввода текстовой информации.
Он имеет свойства TextWrapping, TextAlignment и TextDecorations.
С помощью свойства MaxLength можно задать предельное количество вводимых символов.
```XAML
<TextBox MaxLength="250" TextChanged="TextBox_TextChanged">Начальный текст
</TextBox>
```
В коде C# можно обработать событие изменения текста:
```C#
private void TextBox_TextChanged(object sender, TextChangedEventArgs e)
{
    TextBox textBox = (TextBox)sender;
    MessageBox.Show(textBox.Text);
}
```
По умолчанию, если вводимый текст превышает установленные границы поля, то текстовое поле растет, чтобы вместить весь текст. Но визуально это не очень хорошо выглядит. Поэтому можно перенести непомещающийся текст на новую строку, установив свойство TextWrapping="Wrap".
Чтобы переводить по нажатию на клавишу Enter курсор на следующую строку, нам надо установить свойство AcceptsReturn="True".
Также можно добавить полю возможность создавать табуляцию с помощью клавиши Tab, установив свойство AcceptsTab="True"
Для отображения полос прокрутки TextBox поддерживает свойства VerticalScrollBarVisibility и НоrizontalScrollBarVisibility:
Возможно, при создании приложения потребуется сделать текстовое поле недоступным для ввода, тогда для этого надо установить свойство IsReadOnly="True".
Для выделения текста есть свойства SelectionStart, SelectionLength и SelectionText.
Метка (Label). Представляет текстовую подпись для элемента управления и обеспечивает поддержку клавиш доступа.
Главной особенностью меток является поддержка мнемонических команд-клавиш быстрого доступа, которые передают фокус связанному элементу. Например,
```XAML
	<Label Target="{Binding ElementName=TextBox1}">_привет</Label>
<TextBox Name="TextBox1" Margin="0 30 0 0" Height="30" Width="100">
</TextBox>
```
На Панели элементов в разделе Типовые элементы управления выберите компонент Button и щелкните в любом месте формы. При этом на форме появится кнопка, и в ее свойствах найдите Content и запишите: Оk.
На Панели элементов в разделе Типовые элементы управления выберите компонент Label. Щелкните на поле формы, и на нем появится объект Label, в его свойствах для Visibility (видимый) установить в Visible. Это значит, что текст будет видимым. В свойстве Text запишите: «Введите свое имя». В разделе Текст укажите необходимый шрифт и его размер. А в разделе Кисть в свойстве Foreground укажите цвет текста.
На Панели элементов в разделе Типовые элементы управления выберите компонент ТеxtBox и щелкните в любом месте формы. В его свойствах очистите поле Text. 

Для того чтобы при щелчке на кнопке происходило событие «щелчок на кнопке» необходимо написать код, который будет его обрабатывать. Нажмите двойным щелчком левой кнопкой мыши по элементу Ok. Откроется программная часть проекта, в которой необходимо добавить следующий код:
```C#
namespace WPFApplication
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow: Window
    {
        public MainWindow ()
        {
            InitializeComponent ();
        }
        // Обработчик нажатия по кнопке.
        private void Button Click(object sender, RoutedEventArgs e)
        {
            if (textBoxName.Text == string.Empty)
            {
                MessageBox.Show("Вы не ввели свое имя!");
            }
            else
            {
                MessageBox.Show("Привет, " + textBoxName.Text);
            }
        }
    }
}
```

- [ ] Задание 3. Установка свойств в разметке

Создайте новый проект в IDE Visual Studio 2019.
Укажите название окна проекта: Установка свойств в разметке.
На Панели элементов в разделе Типовые элементы управления выберите компонент Rectangle и щелкните в любом месте формы – создайте два квадрата.
Нажмите двойным щелчком левой кнопкой мыши по одному из квадратов. В открывшейся программной части проекта добавить следующий код:
```XAML
<Window x: Class="PropertiesInMarkUp.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Установка свойств в разметке" Height="280" Width="525">
    <StackPanel>
        <!--Установка значения свойства Fill через атрибут-->
        <Rectangle Fill="Green" Width="100" Height="100">
        </Rectangle>
        <!--Установка значения свойства Fill через вложенный элемент-->
        <Rectangle Width="100" Height="100" Margin="10">
            <Rectangle.Fill>
                <LinearGradientBrush>
                    <GradientStop Color="Chocolate" Offset="0"></GradientStop>
                    <GradientStop Color="BlueViolet" Offset="1"></GradientStop>
                </LinearGradientBrush>
            </Rectangle.Fill>
        </Rectangle>
    </StackPanel>
</Window>
```

- [ ] Задание 4. События мыши

Создайте новый проект «EventsInMarkup» в IDE Visual Studio 2019.
Укажите название окна проекта: Установка свойств в разметке. События мыши.
На Панели элементов в разделе Типовые элементы управления выберите компонент Rectangle и щелкните в любом месте формы – создайте два прямоугольника (рис 1.10).
```C#
namespace EventsInMarkup
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }
        // Когда курсор попадает в область прямоугольника, заполняем прямоугольник желтым цветом.
        private void Rectangle_MouseEnter(object sender, MouseEventArgs e)
        {
            (sender as Rectangle).Fill = Brushes.Yellow;
        }
        // При выходе курсора за пределы прямоугольника устанавливаем зеленый цвет.
        private void Rectangle_MouseLeave(object sender, MouseEventArgs e)
        {
            (sender as Rectangle).Fill = Brushes.Green;
        }
    }
}
```

- [ ] Задание 5. Создание адаптивного TextBox

Создайте новый проект «_8Ball» в IDE Visual Studio 2019.
Укажите название окна проекта: Магический 8 ball.
На Панели элементов в разделе Типовые элементы управления выберете 2 TextBox и 1 Button. Разместите элементы на форме следующим образом и задайте такие же свойства (рис.1.12).: 
Нажмите двойным щелчком левой кнопкой мыши по одному из текст-боксов. В открывшейся программной части проекта добавить следующий код:
```XAML
<Window x:Class="_8Ball.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Магический 8 Ball" Height="350" Width="525">
    <!--
        Объект Grid Определяет гибкую область сетки, состоящую из столбцов и строк.        
    -->
    <Grid>
        <!--
            RowDefinitions - Коллекция которая определяет
            строки для отображения - RowDefinition.
        -->
        <Grid.RowDefinitions>
            <!--
                Создаем три строки(RowDefinition) в коллекции - RowDefinitions.
                (Height="100*"):
                100  - Фиксированные размер.
                100* - Указывает, что начальный размер ряда значение до звездочки, но размер может пропорционально изменяться при изменении размера окна.
                Auto - Указывает что размер данного элемента будет подобран под размер
                       самого большого объекта в контейнере.
            -->
            <RowDefinition Height="100*" />
            <RowDefinition Height="Auto" />
            <RowDefinition Height="100*" />
        </Grid.RowDefinitions>
        <!--
            Используем сложную кисть для заливки фона градиентом.
            Добавляем для этого дескриптор - Background.
        -->
        <Grid.Background>
            <!-- LinearGradientBrush - Заполняет область линейным градиентом.
Линейный градиент определяет градиент вдоль прямой линии.
Конечные точки линии определяются свойствами StartPoint и EndPoin линейного градиента.
Кисть LinearGradientBrush рисует свои GradientStops вдоль этой линии.
            -->
            <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">

                <!-- Коллекция свойств GradientStop -->
                <LinearGradientBrush.GradientStops>
                    <!--
                        GradientStop имеет свойства:
                        Offset - Задает позици цвета.
                        Color  - Задает цвет.
                    -->
                    <GradientStop Offset="1" Color="#FFEEEEEE" />
                    <GradientStop Offset="0.881" Color="#FF302F2F" />
                </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
        </Grid.Background>

        <!--
            <TextBox Имя объкта.
                     Name="txtQuestion"
            Выравнивание элемента по горизонтали относительно контейнера.
                     HorizontalAlignment="Stretch" 
            Выравнивание элемента по вертикали относительно контейнера.
                     VerticalAlignment="Stretch" 
            Выравнивание элемента относительно сторон контейнера.
                     Margin="10" 
            Пренос на новую строку в случае, если текст не помещается в одной строке.
                     TextWrapping="Wrap" 
            Шрифт, который будем использовать.
                     FontFamily="Verdana" 
            Размер используемого шрифта.
                     FontSize="20" 
            Строка в контейнере в которой будет находится данный элемент.
                     Grid.Row="0" 
            Цвет используемого шрифта.
                     Foreground="#FF646464" 
            Свойство текст.
                     Text="[Введите свой вопрос.]" />
        -->
        <TextBox Name="txtQuestion" 
                 HorizontalAlignment="Stretch" 
                 VerticalAlignment="Stretch" 
                 Margin="10" 
                 TextWrapping="Wrap" 
                 FontFamily="Verdana" 
                 FontSize="20" 
                 Grid.Row="0" 
                 Foreground="#FF646464" 
                 Text="[Введите свой вопрос.]" TextChanged="txtQuestion_TextChanged" />
        <!-- 
            IsDefault - Получает или задает значение, указывающее, является ли Button кнопкой по умолчанию.
        -->
        <Button HorizontalAlignment="Left" 
                VerticalAlignment="Center" 
                Margin="10,0,10,0"
                Padding="5"
                Grid.Row="1" 
                Content="Ответ на вопрос" 
                Click="Answer_Click" 
                IsDefault="True" />
        <TextBox Name="txtAnswer" 
                 HorizontalAlignment="Stretch" 
                 VerticalAlignment="Stretch" 
                 Margin="10" 
                 TextWrapping="Wrap" 
                 FontFamily="Verdana" 
                 FontSize="20" 
                 IsReadOnly="True"
                 Grid.Row="2" 
                 Foreground="#FF009BFF" 
                 Text="[Ответ появится здесь.]" />
    </Grid>
</Window>
```
Нажмите двойным щелчком левой кнопкой мыши по кнопке Ответ на вопрос. Откроется программная часть проекта, в которой необходимо добавить следующий код:
```C#
namespace _8Ball
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }
        // Обработчик события нажатия кнопки
        private void Answer_Click(object sender, RoutedEventArgs e)
        {
            // Ставим курсор ожидания.
            this.Cursor = Cursors.Wait;
            // Делаем задержку, для создания эффекта того, что программа задумалась.
            Thread.Sleep(TimeSpan.FromSeconds(1));
            // Берем случайный ответ.
            txtAnswer.Text = AnswerGenerator.GetRandomAnswer();
            // Восстанавливаем прежнее состояние курсора.
            this.Cursor = null;
        }
        private void txtQuestion_TextChanged(object sender, TextChangedEventArgs e)
        {
        }
    }
}
```
<hr>

# Задания для самостоятельного выполнения:

Решите предоставленные задания. Для каждого задания создайте проект с графическим интерфейсом пользователя. 
Продемонстрируйте выполненные работы преподавателю.
- Вариант 1. Введите с клавиатуры три целых числа. Найдите их сумму и произведение. Результат выведите на экран в одно поле, при этом по нажатию кнопки будут поочередно демонстрироваться сумма и произведение.
- Вариант 2. Введите с клавиатуры длину стороны квадрата. Найдите его периметр и площадь. Результат выведите на экран, округлив до сотых.
- Вариант 3. Дана длина ребра куба а, вводится с клавиатуры. Найдите объем куба и площадь его полной поверхности. Результат выведите на экран, округлив до сотых.
- Вариант 4. Сгенерируйте случайным образом три числа, задав промежуток с клавиатуры. Найдите их среднее арифметическое. Результат выведите на экран, округлив до сотых.
- Вариант 5. Х кг яблок стоит А рублей. Определите, сколько стоит Ү кг этих же яблок. Все необходимые значения введите с клавиатуры, результат выведите на экран, округлив до сотых.
- Вариант 6. Введите с клавиатуры размер файла в байтах. Переведите эту величину в килобайты. Результат выведите на экран.
- Вариант 7. Сгенерируйте случайным образом двузначное число. Найдите сумму и произведение его цифр. Результат выведите на экран.
- Вариант 8. С начала суток прошло N секунд (введите с клавиатуры). Определите, сколько полных часов прошло с начала суток. Результат выведите на экран.
- Вариант 9. Сгенерируйте случайным образом значения двух катетов прямоугольного треугольника, задав с клавиатуры интервал. Найдите гипотенузу и площадь прямоугольного треугольника.
- Вариант 10. Автомобиль проехал три участка пути разной длины с разными скоростями, введите необходимые данные с клавиатуры. Найдите среднюю скорость автомобиля. Результат выведите на экран.
