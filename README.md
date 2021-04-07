using System;
using System.Collections.Generic;
//3
namespace Algoritm
{
   public abstract class baseclass
    {
        public abstract decimal Getarea(decimal Radius);

        public virtual decimal InterestPermonth(decimal Amount)
        {
            return Amount * 12 / 100;
        }
        public virtual decimal TotalAmount(decimal Amount, decimal PrincipalAmount)
        {
            return Amount +PrincipalAmount;
        }


    }


    public class derivedclass: baseclass
    {
        public override decimal Getarea(decimal Radius)
        {
            return 2 * (22 / 7) * Radius;
        }
        public override decimal InterestPermonth(decimal Amount)
        {
            return Amount * 14 / 100;
        }

    }
    class Program
    {
        // rekursia

      



        static void Main(string[] args)
        {
           











            //
            Random rand = new Random();
            Queue<int> q = new Queue<int>();    //Это очередь, хранящая номера вершин
            string exit = "";
            int u;
            u = rand.Next(3, 5);
            bool[] used = new bool[u + 1];  //массив отмечающий посещённые вершины
            int[][] g = new int[u + 1][];   //массив содержащий записи смежных вершин

            for (int i = 0; i < u + 1; i++)
            {
                g[i] = new int[u + 1];
                Console.Write("\n({0}) вершина -->[", i + 1);
                for (int j = 0; j < u + 1; j++)
                {
                    g[i][j] = rand.Next(0, 2);
                }
                g[i][i] = 0;
                foreach (var item in g[i])
                {
                    Console.Write(" {0}", item);
                }
                Console.Write("]\n");
            }




            //
            Console.Write("N= ");
            var len = Convert.ToInt32(Console.ReadLine());
            var a = new int[len];
            for (var i = 0; i < a.Length; i++)
            {
                Console.WriteLine("a[{0}] = ",i);
                a[i] = Convert.ToInt32(Console.ReadLine());


            }
            Console.WriteLine("Dzac Pchac:{0}", string.Join(",", QuickSort(a)));
            Console.ReadLine();

           

        }
        public static double Factorial(int number)
        {
            if (number == 0)
            {
                return 1;
            }
            double factorial = 1;

            for (int i = number; i >= 1; i++)
            {

                factorial = factorial * i;

            }
            return factorial;

        }
        static void Swap(ref int x, ref int y)
        {
            var t = x;
            x = y;
            y = t;
              
        }

        static int Partition(int[] array, int minIndex, int maxIndex)
        {
            var pivot = minIndex - 1;
            for (var i = minIndex; i < maxIndex; i++)
            {
                if (array[i] < array[maxIndex])
                {
                    pivot++;
                    Swap(ref array[pivot], ref array[i]);
                }
            }

            pivot++;
            Swap(ref array[pivot], ref array[maxIndex]);
            return pivot;
        }

        static int[] QuickSort(int[] array, int minIndex, int maxIndex)
        {
            if (minIndex>= maxIndex)
            {
                return array;
            }
            var pivotIndex = Partition(array, minIndex, maxIndex);
            QuickSort(array, minIndex, pivotIndex - 1);
            QuickSort(array, pivotIndex + 1, maxIndex);

            return array;

        }
        static int [] QuickSort(int[] array)
        {
            return QuickSort(array, 0, array.Length - 1);


        }


    }

    }

