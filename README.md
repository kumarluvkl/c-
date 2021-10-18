# c-
random code that i do in c++
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */
    int n,i,j,temp,mode;
    float s=0,mean,median;
    cin>>n;
    int a[n];
     for (i=0; i<n; i++) {
        cin>>a[i];
    }  
    for (i=0; i<n; i++) {
        s=s+a[i];
    }   
    n=i;
    mean=(s/i);
    for(i=0; i<n; i++)
    {
        for(j=i+1; j<n; j++)
        {
            //If there is a smaller element found on right of the array then swap it.
            if(a[j] < a[i])
            {
                temp = a[i];
                a[i] = a[j];
                a[j] = temp;
            }
        }
    }
    if(i%2!=0){
    median=a[(n/2)+1];
    }
    else {
        s=a[n/2]+a[(n/2)-1];
    median=(s/2);
    }
    
    int maxValue = 0, maxCount = 0;

   for (i = 0; i < n; ++i) {
      int count = 0;
      
      for (j = 0; j < n; ++j) {
         if (a[j] == a[i])
         ++count;
      }
      
      if (count > maxCount) {
         maxCount = count;
         maxValue = a[i];
      }
   }
   mode=maxValue;
   printf("%0.1f\n %0.1f \n %d",mean,median,mode);
    return 0;
}
