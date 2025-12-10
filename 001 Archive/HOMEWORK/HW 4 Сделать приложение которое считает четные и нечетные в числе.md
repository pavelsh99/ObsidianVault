---
date: 2025-05-14
tags:
  - csharp
  - цикл
  - HW
---

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace @while
{
    internal class Program
    {
        static void Main(string[] args)
        {
            while (true)
            {
                double value = 0;

                int chet = 0;
                int nechet = 0;
                int limit;

                try
                {
                    Console.WriteLine("введите число для проверки всех четных и нечетных");
                    limit = int.Parse(Console.ReadLine());
                }
                catch
                {
                    Console.WriteLine("Не удалось преобразовать строку в число");
                    Console.ReadLine();
                    Console.Clear();

                    continue;
                }

                while (value < limit)
                {
                    value++;
                    if (value % 2 == 0)
                        chet++;
                    else
                        nechet++;
                }
                Console.WriteLine("Колличество четных чисел = " + chet);
                Console.WriteLine("Колличество нечетных чисел = " + nechet);
                Console.ReadLine();
                Console.Clear();
            }
        }
    }
}
```

Cложное решение 
```csharp
using System;
using System.CodeDom;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Dificult_solve
{
    internal class Program
    {
        static void Main(string[] args)
        {
            uint oddNumbersCount = 0; //нечетные числа
            uint evenNumbersCount = 0; //четные числа

            int oddNumberssum = 0;
            int evenNumberssum = 0;

            Console.WriteLine("Введите первое число диапазона");
            int currentValue = int.Parse(Console.ReadLine());

            Console.WriteLine("введите последнее число диапазона");
            int limit = int.Parse(Console.ReadLine());

            while (currentValue <= limit)
            {
                if(currentValue%2==0)
                { 
                    evenNumbersCount++;
                    evenNumberssum += currentValue;
                }
                else
                {
                    oddNumberssum = oddNumberssum + currentValue;
                    oddNumbersCount++;
                }
                currentValue++;
            }


            Console.WriteLine("Колличество нечетных чисел = " + oddNumbersCount);
            Console.WriteLine("Колличество четных чисел = " + evenNumbersCount);
            Console.WriteLine($"Сумма нечетных чисел = {oddNumberssum}");
            Console.WriteLine($"Сумма четных чисел = {evenNumberssum}");
            Console.ReadLine();
            Console.Clear();
        }
    }
}

```