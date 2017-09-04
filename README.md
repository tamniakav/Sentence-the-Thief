# Sentence-the-Thief
Just another repository
using System;

namespace _7.Sentence_the_Thief
{
    class Program
    {
        static void Main(string[] args)
        {
            string numType = Console.ReadLine();
            int n = int.Parse(Console.ReadLine());
            long thiefId = long.MinValue;

            for (int i = 0; i < n; i++)
            {
                long ids = long.Parse(Console.ReadLine());

                if (numType == "sbyte")
                {
                    if (ids > thiefId && ids <= sbyte.MaxValue)
                    {
                        thiefId = ids;
                    }
                }
                else if (numType == "int")
                {
                    if (ids > thiefId && ids <= int.MaxValue)
                    {
                        thiefId = ids;
                    }
                }
                else if (numType == "long")
                {
                    if (ids > thiefId && ids <= long.MaxValue)
                    {
                        thiefId = ids;
                    }
                }
            }

            double years = 0;

            if (thiefId < 0)
            {
                 years = Math.Ceiling(thiefId / -128.0);
            }
            else
            {
                 years = Math.Ceiling(thiefId / 127.0);
            }

            if (years > 1)
            {
                Console.WriteLine($"Prisoner with id {thiefId} is sentenced to {years} years");
            }
            else
            {
                Console.WriteLine($"Prisoner with id {thiefId} is sentenced to {years} year");
            }
        }
    }
}
