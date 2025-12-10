---
tags:
  - csharp
  - HW
date:
---
Сделать программу, которая рисует треугольники:
![[Pasted image 20250515204142.png]]
```csharp
        static void Main(string[] args)
        {
            int amount = 10;
            for (int startlengh = 1; startlengh <= 10; startlengh++) //первый треугольник
            {

                for(int symbol = 0; symbol < startlengh; symbol++) 
                {
                    Console.Write("#");
                }
                for (int space = 1; space < amount; space++)
                {
                    Console.Write("_"); 
                }
                Console.WriteLine();
                amount--;
            }
            Console.WriteLine("\n\n\n");// пропуск 3 строки

            for (int lengh = 10; lengh > 0; lengh--) //второй треугольник
            {

                for (int symbol = 0; symbol < lengh; symbol++)
                {
                    Console.Write("#");
                }
                for (int space = 0; space < amount; space++)
                {
                    Console.Write("_");
                }
                Console.WriteLine();
                amount++;
            }
            Console.WriteLine("\n\n\n");// пропуск 3 строки



            for (int startlengh = 1;  startlengh <= 10; startlengh++) //третий треугольник
            {
                for (int space = 1; space < amount; space++)
                {
                    Console.Write("_");
                }
                for(int symbol = 1;  symbol <= startlengh; symbol++)
                {
                    Console.Write("#");
                }
                amount--;
                Console.WriteLine();
            }
            Console.WriteLine("\n\n\n"); //пропуск 3 строки
            
            for (int lengh = 10; lengh > 0; lengh--)//четвертый треугольник
            {
                for (int space = 0; space < amount; space++)
                {
                    Console.Write("_");
                }

                for (int symbol = 0; symbol < lengh; symbol++)
                {
                    Console.Write("#");
                }

                Console.WriteLine();
                amount++;
            }
            Console.WriteLine("\n\n\n");
            Console.ReadLine();

        }
    }
}

```