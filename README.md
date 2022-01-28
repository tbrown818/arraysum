# arraysum
#include <iostream>
using namespace std;
int main ()
{
   int arr[] = {15, 4, 23, 9, 3, 18, 8, 44, 10, 1};
   int n = 10, sum = 0;
   for (int i = 0; i < n ; i++)
   {
      sum+=arr[i];
   }
                      
   cout<< "The array sum is " <<sum;                            
   return 0;
}
