---
tags:
  - HW
  - csharp
date: 2025-05-29
---
![[Pasted image 20250530195814.png]]![[Pasted image 20250530195828.png]]

```csharp

        static char[] myArray()
        {
            Console.WriteLine("Введите символ...\t");
            char symbol = char.Parse(Console.ReadLine());

            Console.WriteLine("Введите количество символов...\t");
            int ammount = int.Parse(Console.ReadLine());

            char[] chars = new char[ammount];

            for (int i = 0; i < chars.Length; i++) 
                chars[i] = symbol;
            
            return chars;
        }

        static void showArray(char[] array)
        {
            for (int i = 0;i < array.Length;i++)
            {
                Console.Write(" " + array[i] + " ");
            }
        }
        static void Main(string[] args)
        {
            char[] myArray  = Program.myArray();
            showArray(myArray);
        }
    }
```

```csharp
        static int IndexOf(int [] array, int value)
        {
            for (int i = 0; i < array.Length; i ++) // возвращаем индекс если нашли искомое число, если нет, то -1
            {
                if (array[i] == value)
                    return i;
            }

            return -1;
        }

        static int[] RandomArray (uint length, int minValue, int maxValue)
        {
            Random random = new Random();
            int[] array = new int [length]; 

            for (int i = 0; i < array.Length; i++)
            {
                array[i] = random.Next (minValue, maxValue);
            }

            return array;
        }
        static void Main(string[] args)
        {
            int[] myArrray = RandomArray(1000, 0,1000);

            int result = IndexOf(myArrray, 3);
            
            Console.WriteLine(result);
        }
        
    }
```