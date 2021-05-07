#include <iostream>
#include <iomanip>

using namespace std;
 
int main()
{
 
    const int M = 5 ;//矩阵行数
	const int N = 5 ;//矩阵列数
 
	int matrix[M][N] = { 0 };
	int row = 0;
	int col = 0;
	int start = 1; //起始值
	int m = M;
	int n = N;
	//可以画 N/2个圈	
	for (int count = 0; count < N / 2; count++)  
	{
		for (col=count;col<n-1;col++) //a排赋值
		{
			matrix[row][col] = start++;
		}
		for (row=count;row<m-1;row++) //b排赋值
		{
			matrix[row][col] = start++;
		}
		for (col = n - 1; col > count; col--) //c排赋值
		{
			matrix[row][col] = start++;
		}
		for (row = m- 1; row > count; row--) //d排赋值
		{
			matrix[row][col] = start++;
		}
		//进入下一圈
		m--;
		n--;
		row++;
	}
	if (N % 2 != 0) //如果size为奇数则最后中间那一个数遍历不到，这里补上
	{
		int  z = M - 2 * row;
		for(int i=0; i < z; ++i)
		matrix[row++][col+1] =start++;
	}
 
	//输出数组
	for (int i = 0; i < M; i++)
	{
		for (int j = 0; j < N; j++)
		{
			cout << setw(4) << matrix[i][j];//设定输出宽度为3
		}
		cout << endl;
	}
 
 
	return 0;
}
 
