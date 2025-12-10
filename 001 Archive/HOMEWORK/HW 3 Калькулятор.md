---
tags:
  - csharp
  - HW
date: 2025-05-12
---

Должен выполнять простые действия 
- сложение
- вычитание
- умножение
- деление
Сделать 2 варианта:
- [x] switch
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace test
{
    internal class Program
    {
        static void Main(string[] args)
        {
            double Number1, Number2, result, addition, subtraction, multiply, division;

            Console.WriteLine("Введите число 1");
            Number1 = double.Parse(Console.ReadLine());

            Console.WriteLine("Введите число 2");;
            Number2 = double.Parse(Console.ReadLine());

            addition = Number1 + Number2;
            subtraction = Number1 - Number2;
            multiply = Number1 * Number2;
            division = Number1 / Number2;

            Console.WriteLine("Что вы хотите сделать?\nНажмите\n1 для сложения\n2 для вычитания\n3 для умножения и\n4 для деления...");

            ConsoleKey consoleKey = Console.ReadKey().Key;

            switch (consoleKey)
            {
                case ConsoleKey.D2:
                    result = subtraction;
                    Console.WriteLine("\nРезультат вычитания " + "= " + result);
                    break;
                case ConsoleKey.D1:
                    result = addition;
                    Console.WriteLine("\nРезультат сложения " + "= " + result);
                    break;
                case ConsoleKey.D3:
                    result = multiply;
                    Console.WriteLine("\nРезультат умножения " + "= " + result);
                    break;
                case ConsoleKey.D4:
                    if (Number2 == 0)
                    {
                        Console.WriteLine("\nНа ноль делить нельзя");

                    }
                    else
                    {
                        result = division;
                        Console.WriteLine("\nРезультат деления " + "= " + result);
                    }
                    break;
                    default:
                    Console.WriteLine("Ошибка ввода");
                        break;
            }

        }
    }
}

```
- [x] if else
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace test
{
    internal class Program
    {
        static void Main(string[] args)
        {
            double Number1, Number2, result, addition, subtraction, multiply, division;

            Console.WriteLine("Введите число 1");

            Number1 = double.Parse(Console.ReadLine());

            Console.WriteLine("Введите число 2");

            Number2 = double.Parse(Console.ReadLine());

            addition = Number1 + Number2;
            subtraction = Number1 - Number2;
            multiply = Number1 * Number2;
            division = Number1 / Number2;

            Console.WriteLine("Что вы хотите сделать?\nНажмите\n- для сложения\n+ для вычитания\n* для умножения и\n/ для деления...");

            ConsoleKeyInfo consoleKeyInfo = Console.ReadKey();

            char key = consoleKeyInfo.KeyChar;

            if (key == '-')
            {
                result = subtraction;
                Console.WriteLine("\nРезультат вычитания =\n"+ result);
            }
            else if (key == '+')
            {
                result = addition;
                Console.WriteLine("\nРезультат сложения =\n"+ result);
            }
            else if (key == '/')
            {
                if 
                    (Number2 == 0)
                {
                    Console.WriteLine("Деление на 0 невозможно");
                }
                else 
                { 
                    result = division;
                    Console.WriteLine("\nРезультат деления =\n" + result); 
                }
            }
            else if (key == '*')
            {
                result = addition;
                Console.WriteLine("\nРезультат умножения =\n" + result);
            }
            else 
            { 
                Console.WriteLine("Ошибка вводa"); 
            }
        }
    }
}
```