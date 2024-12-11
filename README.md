#include<stdio.h>
#include<string.h>
#include<stdlib.h>
void main()
{
    char str[10000];
    scanf("%s",&str);
   
    char arr1[]={'a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'};
    int arr2[]={2,22,222,3,33,333,4,44,444,5,55,555,6,66,666,7,77,777,7777,8,88,888,9,99,999,9999};
    int count=0;
   
    for(int i=0;i<strlen(str);i++)
    {
        if(str[i]=='1')
        continue;
        if(str[i]=='0')
        {
            printf(" ");
            continue;
        }
        count=0;
        for(int j=i+1;j<=strlen(str);j++)
        {
            
            if(str[i]==str[j])
            {
               
                continue;
            }
            else
            {
                count=j-i;
                if(str[i]=='7' || str[i]=='9')
                {
             
                    if(count>=5)
                    {
                        count=count-4;
                    }
                }
                else if(count>=4)
                {
                    count=count-3;
                }
                int sum=0;
               
                for(int k=i;k<count+i;k++)
                {
                    char ch=str[k];
                    sum=sum*10+ch-48;
                }
               
                for(int l=0;l<26;l++)
                {
                    if(sum==arr2[l])
                    {
                        printf("%c",arr1[l]);
                    }
                }
                if(j>=strlen(str))
                {
                    exit(1);
                }
                i=j-1;
                break;
            }
        }
    }

}
