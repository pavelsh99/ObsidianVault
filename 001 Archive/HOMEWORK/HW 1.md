---
---
---
#HW #csharp 
![[Pasted image 20250511163146.png]]
![[Pasted image 20250511163121.png]]
# **Задача 1**

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Globalization;

namespace APP_DZ
{
    internal class Program
    {
        static void Main(string[] args) //Программа вычисляет среднее арифметическое
        {
            double number1, number2, result;

            string str;

            NumberFormatInfo numberFormatInfo = new NumberFormatInfo()
            {
                NumberDecimalSeparator = (".")

            };

            Console.WriteLine("Для Вычисление среднего арифметического в 2х числах, введите число 1");


            str = Console.ReadLine();

            bool res = double.TryParse(str, out number1);

            if (res)
            {

                Console.WriteLine("ВВЕДИТЕ ЧИСЛО 2");

                str=Console.ReadLine();

                bool res2 = double.TryParse(str, out number2);

                if (res2)
                {

                    result = (number1 + number2) / 2;

                    Console.WriteLine("Среднее арифметическое = " + result);



                }

                else
                {

                    Console.WriteLine("ОШИБКА!!!");

                }



            }
            else 
            {

                Console.WriteLine("ОШИБКА");

            }
        }
    }
}

```
# **Задача 2**


```csharp
using System;
using System.Globalization;

namespace Lesson2
{
    internal class Program
    {
        static void Main(string[] args)
        {

            double b, c;
            
            string str;
            
            Console.WriteLine("Введите первое число");
            
            str = Console.ReadLine();
            
            bool result = double.TryParse(str, out double a);
            if (result)
            {

                Console.WriteLine("Введите второе число");

                str = Console.ReadLine();

                bool resultb = double.TryParse(str, out b);

                if (resultb)
                {

                   Console.WriteLine("Введите третье число");

                    str = Console.ReadLine();

                    bool resultc = double.TryParse(str, out c);

                    if (resultc)

                    {
                        double mul = a * b * c;

                        double sum = a + b + c;

                        Console.WriteLine("Результат умноженя = " + mul);

                        Console.WriteLine("Результат суммы = " + sum);

                    }

                    else

                    {

                        Console.WriteLine ("Повторите попытку");

                    }

                }
                else
                {

                    Console.WriteLine("Вы ввели число неверно");

                }
            
            }

            else
            {

                Console.WriteLine("Введите число правильно, повоторите попытку.");

            }

        }
    }
}
```

# **Задача 3**
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace WalletConverter
{
    internal class Program
    {
        static void Main(string[] args)
        {

            double Amount;

            double RateEURRUB = 89.89;

            double RateUSDRUB = 81.03;

            double RateUSDEUR = 0.90;

            double ConvertedAmount;

            Console.WriteLine("Введите количество вашей валюты");

            string str = Console.ReadLine();

            bool result = double.TryParse(str, out Amount);

            if (result)
            {

                Console.WriteLine("Какую валюту вы хотите конвертировать? ");

                Console.WriteLine("1. USD");

                Console.WriteLine("2. EUR");

                Console.WriteLine("3. RUB");

                Console.WriteLine("Для выбора нажмите 1 2 или 3.");

                ConsoleKeyInfo Key = Console.ReadKey();

                Console.WriteLine();

                if (Key.KeyChar == '1') //USD
                {

                    Console.WriteLine();

                    Console.WriteLine("В какую Валюту вы хотите перевести ваши USD?");

                    Console.WriteLine("1. EUR");

                    Console.WriteLine("2. RUB");

                    Console.WriteLine("Нажмите 1 или 2...");

                    ConsoleKeyInfo Key2 = Console.ReadKey();

                    if (Key2.KeyChar == '1') // USD to EUR
                    {
                        ConvertedAmount = Amount * RateUSDEUR;

                        Console.WriteLine();

                        Console.WriteLine("У вас " + Amount + " USD, что составляет " + ConvertedAmount + " EUR.");

                    }

                    else if (Key2.KeyChar == '2')//USD to RUB
                    {

                        ConvertedAmount = Amount * RateEURRUB;

                        Console.WriteLine();

                        Console.WriteLine("У вас " + Amount + " USD, что составляет " + ConvertedAmount + " RUB.");
                    }

                    else
                    {

                        Console.WriteLine("ОШИБКА ВВОДА!");

                    }

                }

                else if (Key.KeyChar == '2') //EUR
                {
                    Console.WriteLine("В какую Валюту вы хотите перевести ваши EUR?");

                    Console.WriteLine("1. USD");

                    Console.WriteLine("2. RUB");

                    Console.WriteLine("Нажмите 1 или 2...");

                    ConsoleKeyInfo Key2 = Console.ReadKey();

                    if (Key2.KeyChar == '1') // EUR to USD
                    {
                        ConvertedAmount = Amount / RateUSDEUR;

                        Console.WriteLine();

                        Console.WriteLine("У вас " + Amount + " EUR, что составляет "+ ConvertedAmount + " USD.");

                    }

                    else if (Key2.KeyChar == '2')//EUR to RUB
                    {

                        ConvertedAmount = Amount * RateEURRUB;

                        Console.WriteLine();

                        Console.WriteLine("У вас " + Amount + " EUR, что составляет " + ConvertedAmount + " RUB.");
                    }

                    else 
                    {

                        Console.WriteLine("ОШИБКА ВВОДА!");

                    }


                }

                else if (Key.KeyChar == '3') // RUB
                {

                    Console.WriteLine("В какую Валюту вы хотите перевести ваши RUB?");

                    Console.WriteLine("1. USD");

                    Console.WriteLine("2. EUR");

                    Console.WriteLine("Нажмите 1 или 2...");

                    ConsoleKeyInfo Key2 = Console.ReadKey();

                    if (Key2.KeyChar == '1') // RUB to USD
                    {
                        ConvertedAmount = Amount / RateEURRUB;

                        Console.WriteLine();

                        Console.WriteLine("У вас " + Amount + " RUB, что составляет " + ConvertedAmount + " USD.");

                    }

                    else if (Key2.KeyChar == '2')//RUB to EUR
                    {

                        ConvertedAmount = Amount / RateEURRUB;

                        Console.WriteLine();

                        Console.WriteLine("У вас " + Amount + " RUB, что составляет " + ConvertedAmount + " EUR.");
                    }

                    else
                    {

                        Console.WriteLine("ОШИБКА ВВОДА!");

                    }

                }

                else
                {

                    Console.WriteLine("ОШИБКА ВВОДА!");

                }

            }
            
            else 
            {

                Console.WriteLine("ОШИБКА ВВОДА!");

            }
        }
    }
}

```

[^1]: fgasdasd
