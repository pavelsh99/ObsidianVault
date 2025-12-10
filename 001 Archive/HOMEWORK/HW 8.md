---
tags:
  - HW
  - csharp
date: 2025-08-07
---

![[Pasted image 20250807150224.png]]

```csharp
static void Main(string[] args)
{
    void resize(ref int[] array)
    {
        Console.WriteLine(array);
        Console.WriteLine("введите новое колличество элементов массива");

        uint ammount = uint.Parse(Console.ReadLine());

        int[] ResizedArray = new int[ammount];

        int CopySteps = Math.Min(array.Length, ResizedArray.Length);

        for (int i = 0; i < CopySteps; i++)
        {
            ResizedArray[i] = array[i];
            
        }
        array = ResizedArray;

    }
    Console.WriteLine("Введите длину массива");
    uint lenght = uint.Parse(Console.ReadLine());

    int[] myArray = new int[lenght];

    Random random = new Random();

    for (int i = 0;i < myArray.Length; i++)
    {
        myArray[i] = random.Next(100);

    }

    Console.Clear();



    for (int i = 0; i < myArray.Length; i++)
    {
        Console.Write(myArray[i] + "\t");

    }

    resize(ref myArray);

    for (int i = 0; i < myArray.Length; i++)
    {
        Console.Write(myArray[i] + "\t");

    }


}
```

