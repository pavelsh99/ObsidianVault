---
tags:
  - HW
  - csharp
---

Проверка числа на четность (HW2)


```csharp
            int input;

            Console.WriteLine("Введите число");

            input = int.Parse(Console.ReadLine());

            if (input % 2 == 0)
            {
                Console.WriteLine("число четное");

            }
            else
            {
                Console.WriteLine("число не четное");
            }
```