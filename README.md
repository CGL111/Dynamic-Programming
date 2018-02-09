# Dynamic-Programming
寻找一个数列里连续子序列最大的和
1.O(n^3)
int Max = 0;
for(int i = 1;i < n;i++)
{
for(int j = i;j < n;j++)
{
  int sum = 0;
  for(int k = i;k <= j;k++){
      sum +=A[k];
  }
  Max = max(sum,Max);
}
}
2.O(n^2)
S[i-1] = A[0];
Max = 0;
for(int i = 1;i < n;i++) S[i]+=S[i-1] + A[i];
for(int i = 0;i < n;i++) 
   for(int j = i;j < n;j++)
       Max = max(Max,S[j]-S[i]);
3.分治法
 递归思想
 m = a + (b-a)/2
 Max = (L+R,max((a,m),(m,b)))
