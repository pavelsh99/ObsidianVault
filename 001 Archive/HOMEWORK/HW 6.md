---
tags:
  - csharp
  - HW
  - массив
  - цикл
date: 2025-05-19
---
![[Pasted image 20250519112928.png]]


```csharp
using System;
using System.Linq;

namespace ConsoleApplication1
{
    internal class Program
    {
        public static void Main(string[] args)
        {
            Console.WriteLine("Enter lenght of array"); //Ввод длины массива

            int length = int.Parse(Console.ReadLine());

            int[] myArray = new int[length];

            for (int i = 0; i < myArray.Length; i++)
            {

                Console.Write("Enter a number: ");
                myArray[i] = int.Parse(Console.ReadLine());


            }



            Console.WriteLine("Massive backwards is:"); // Масси задом наперед

            for (int maxNumber = myArray.Length - 1; maxNumber >= 0; maxNumber--)
            {
                Console.WriteLine(myArray[maxNumber]);
            }

            int evenNumber = 0;// сумма четных чисел

            for (int i = 0; i < myArray.Length; i++)
            {
                if (myArray[i] % 2 == 0)
                {
                    evenNumber += myArray[i];
                }


            }
            Console.WriteLine("Sum of even number is " + evenNumber); 

            int Lowest = myArray[0];/// Наименьшее число

            for (int i = 0; i < myArray.Length; i++)
            {

                if (myArray[i]<Lowest)
                {
                    Lowest = myArray[i];
                }
            }

            Console.WriteLine("The lowest number is " + Lowest);

        }
    }
}
```
Измененный вариант
```csharp
using System;
using System.Linq;

namespace ConsoleApplication1
{
    internal class Program
    {
        public static void Main(string[] args)
        {
            Console.Write("\nEnter lenght of array:\t"); //Ввод длины массива

            int[] myArray = new int[int.Parse(Console.ReadLine())];

            for (int i = 0; i < myArray.Length; i++)
            {

                Console.Write($"\nEnter a number with index {i}: \t");
                myArray[i] = int.Parse(Console.ReadLine());


            }



            Console.WriteLine("Massive backwards is:"); // Масси задом наперед

            for (int maxNumber = myArray.Length - 1; maxNumber >= 0; maxNumber--)//Длина - 1 потому что массив начинается с индекса 0
            {
                Console.Write(myArray[maxNumber]);
            }

            int evenNumber = 0;// сумма четных чисел

            for (int i = 0; i < myArray.Length; i++)
            {
                if (myArray[i] % 2 == 0)
                {
                    evenNumber += myArray[i];
                }


            }
            Console.WriteLine("\nSum of even number is " + evenNumber); 

            int Lowest = myArray[0];/// Наименьшее число

            for (int i = 0; i < myArray.Length; i++)
            {

                if (myArray[i]<Lowest)
                {
                    Lowest = myArray[i];
                }
            }

            Console.WriteLine("The lowest number is " + Lowest);

        }
    }
}
```