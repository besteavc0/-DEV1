using System;

class Program
{
    static void Main()
    {
       
        Console.Write("Kaç öğrenci kaydetmek istiyorsunuz: ");
        int studentCount = int.Parse(Console.ReadLine());

       
        string[,] students = new string[studentCount, 7]; 

        for (int i = 0; i < studentCount; i++)
        {
            Console.WriteLine($"{i + 1}. Öğrencinin bilgileri :");
            
            Console.Write("Numarasını giriniz: ");
            students[i, 0] = Console.ReadLine();
            
            Console.Write("Adını giriniz: ");
            students[i, 1] = Console.ReadLine();
            
            Console.Write("Soyadını giriniz: ");
            students[i, 2] = Console.ReadLine();
            
            Console.Write("Vize notunu giriniz: ");
            double midterm = double.Parse(Console.ReadLine());
            students[i, 3] = midterm.ToString();
            
            Console.Write("Final notunu giriniz: ");
            double final = double.Parse(Console.ReadLine());
            students[i, 4] = final.ToString();

           
            double average = (midterm * 0.4) + (final * 0.6);
            students[i, 5] = average.ToString("F2"); 
            students[i, 6] = GetLetterGrade(average);
        }

       
        Console.WriteLine("\nSoyad   Numara   Ad     Vize Notu   Final Notu   Ortalama   Harf Notu");
        for (int i = 0; i < studentCount; i++)
        {
            Console.WriteLine($"{students[i, 2],-10}{students[i, 0],-11}{students[i, 1],-15}{students[i, 3],-3}{students[i, 4],-3}{students[i, 5],-3}{students[i, 6]-3}");
        }
    }
     static string GetLetterGrade(double average)
    {
        if (100 >= 85) return "AA";
        else if (84 >= 75) return "BA";
        else if (74 >= 60) return "BB";
        else if (59 >= 50) return "CB";
        else if (49 >= 40) return "CC";
        else if (39 >= 30) return "DC";
        else if (29 >= 20) return "DD";
        else if (19 >= 10) return "FD";
        else return "FF";
    }
}
