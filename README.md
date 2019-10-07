// three ways to calculate fibonachi

```
Fibunachi fibu = new Fibunachi();
Console.WriteLine(fibu.Solver1(20));
Console.WriteLine(fibu.Solver2(92));
Console.WriteLine(fibu.Solver3(95));
Console.WriteLine(fibu.Solver4(920));
Console.ReadLine();
            
            
using System;
using System.Collections.Generic;
using System.Numerics;
using System.Text;

namespace Kri.School
{
    class Fibunachi
    {
        public long Solver1(int n)
        {
            if (n == 1 || n == 2)
            {
                return 1;
            }

            return Solver1(n - 1) + Solver1(n - 2);
        }

        Dictionary<long, long> lookup = new Dictionary<long, long>();

        public long Solver2(int n)
        {
            if (n == 1 || n== 2)
            {
                return 1;
            }

            if (!lookup.ContainsKey(n-1))
                lookup[n - 1] = Solver2(n - 1);

            if (!lookup.ContainsKey(n - 2))
                lookup[n - 2] = Solver2(n - 2);

            return lookup[n - 1] + lookup[n - 2];
        }

        public long Solver3(int n)
        {
            long temp = 0;
            long temp1 = 1;
            long temp2 = 1;
            for (int i = 0; i < n-2; i++)
            {
                temp = temp1 + temp2;
                temp1 = temp2;
                temp2 = temp;
            }

            return temp;
        }

        public BigInteger Solver4(int n)
        {
            BigInteger temp = 0;
            BigInteger temp1 = 1;
            BigInteger temp2 = 1;
            for (int i = 0; i < n - 2; i++)
            {
                temp = temp1 + temp2;
                temp1 = temp2;
                temp2 = temp;
            }

            return temp;
        }
    }
}

```
