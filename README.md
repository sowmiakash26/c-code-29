#include<stdio.h>
int main()
{
    int n;
    printf("Enter the value of n: ");
    scanf("%d", &n);
    if(n<=0)
    {
        printf("Invalid input.Enter any positive integer ");
        return 1;
    }
    int m[n][n];
    int top=0,left=0,right=n-1,bottom=n-1;
    int num=1;
    while(left<=right && top<=bottom){
        for(int i=left;i<=right;i++){
            m[top][i]=num++;
        }
        top++;
        for(int i=top;i<=bottom;i++){
            m[i][right]=num++;
        }
        right--;
        for(int i=right;i>=left;i--){
            m[bottom][i]=num++;
        }
        bottom--;
        for(int i=bottom;i>=top;i--){
            m[i][left]=num++;
        }
        left++;
    }
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            printf("%d ", m[i][j]);
        }
        printf("\n");
    }
    return 0;
}
