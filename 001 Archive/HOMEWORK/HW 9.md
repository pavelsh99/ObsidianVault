---
tags:
  - HW
  - csharp
date: 2025-08-11
---
![[Pasted image 20250807150327.png]]
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Custom_addition_to_array
{
    internal class Program
    {
        static void Main(string[] args)
        {
            void AddtoBegginig(ref int[] Oldarray, int number)
            {

                int[] Newarray = new int[Oldarray.Length+1];

                Newarray[0] = number;

                for (int i = 0; i < Oldarray.Length; i++)
                {

                    Newarray[i+1] = Oldarray[i];

                }

                Oldarray = Newarray;
                
                for (int i = 0; i < Newarray.Length; i++)
                {
                    Console.Write(Newarray[i] + "\t");
                }
            }

            void AddtoTheEnd(ref int[] Oldarray, int number)
            {

                int[] Newarray = new int[Oldarray.Length + 1];

                Newarray[Oldarray.Length] = number;

                for(int i = 0;i < Oldarray.Length;i++)
                {
                    Newarray[i] = Oldarray[i];
                }

                Newarray[Oldarray.Length] = number;

                Oldarray = Newarray;

                for (int i = 0; i < Newarray.Length; i++)
                {
                    Console.Write(Newarray[i] + "\t");
                }
            }

            void AddtoIndex(ref int[] Oldarray, int number, int indexNumber)
            {
                int[] Newarray = new int[Oldarray.Length + 1];

                for (int i = 0; i < indexNumber; i++)
                {
                    Newarray[i] = Oldarray[i];
                }

                Newarray[indexNumber] = number;

                for (int i = indexNumber; i < Oldarray.Length; i++)
                {
                    Newarray[i+1] = Oldarray[i];
                }

                Oldarray = Newarray;

                for (int i = 0; i < Newarray.Length; i++)
                {
                    Console.Write(Newarray[i] + "\t");
                }
            }

            Console.WriteLine("введите длинну массива \n");
            int ammount = int.Parse(Console.ReadLine());

            Console.Clear();

            int[] myArray = new int[ammount];

            Random random = new Random();

            for (int i = 0; i < myArray.Length; i++)
            {
                myArray[i] = random.Next(500);
            }

            for (int i = 0;i < myArray.Length; i++)
            {
                Console.Write(myArray[i] + "\t");
            }

            bool inputIsValueble = false;


            do
            {

                Console.WriteLine("\n\nДля добавления элемента в начало введите 1 \n ");
                Console.WriteLine("Для добавления элемента в конец введите 2 \n");
                Console.WriteLine("Для добавления элемента по указанному индексу введите 3 \n");

                string input = Console.ReadLine();

                try
                {
                    int parsedInput = int.Parse(input);
                    switch (parsedInput)
                    {
                        case 1:
                            inputIsValueble = true;

                            Console.WriteLine("Введите число, которое вы хотите добавить в начало массива");
                            int parsedNumber = int.Parse(Console.ReadLine());

                            AddtoBegginig(ref myArray, parsedNumber);

                            break;

                        case 2:
                            inputIsValueble = true;

                            Console.WriteLine("Введите число, которое вы хотите добавить в конец массива");
                            parsedNumber = int.Parse(Console.ReadLine());

                            AddtoTheEnd(ref myArray, parsedNumber);

                            break;

                        case 3:
                            inputIsValueble = true;

                            Console.WriteLine("Введите число, которое вы хотите добавить в массив");
                            parsedNumber = int.Parse(Console.ReadLine());

                            Console.WriteLine("Введите индекс, куда вы хотите поместить число");
                            int parsedIndex = int.Parse(Console.ReadLine());

                            AddtoIndex(ref myArray, parsedNumber, parsedIndex);

                            break;

                        default:
                            Console.WriteLine("\nВведите число от 1 до 3...");
                            break;

                    }

                }
                catch
                {
                    Console.WriteLine("\nВведите число, а не текст");
                }


            } while (inputIsValueble == false);




        }
    }
}

```


