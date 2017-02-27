# Uva---100

#include <stdio.h>

long int length(long int j)
{
    long int c = 0;
    while(j)
    {
        if(j == 1)                                          // solved
        {
            c++;
            break;
        }
        else if(j%2 == 1)
        {
            j = 3*j+1;
            c++;
        }
        else if(j%2 == 0)
        {
            j = j/2;
            c++;
        }
    }
    return c;
}
int main()
{
    long int a,b,n,i,max;
    while(scanf("%ld %ld",&a,&b) == 2)
    {
        if(a > 0 && b > 0)
        {
            if(a <= b)
            {
                max = 0;
                for(i=a;i<=b;i++)
                {
                    n = length(i);
                    if(max < n)
                        max = n;
                }
                printf("%ld %ld %ld\n",a,b,max);
            }
            else
            {
                max = 0;
                for(i=b;i<=a;i++)
                {
                    n = length(i);
                    if(max < n)
                        max = n;
                }
                printf("%ld %ld %ld\n",a,b,max);
            }
        }
    }
    return 0;
}
