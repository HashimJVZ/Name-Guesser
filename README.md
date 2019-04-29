#include<stdio.h>

void main()
{
	int i, j, k=0, l, m, n, y;
	char x = 'A';

	printf("Think of a name !!!\n");
	printf("Enter number of letters: ");
	scanf("%d",&n);
	printf("\n");

	m = 26/n;

	if (26%n!=0)
		m=m+1;

	char A[m][n], B[n][n], C[n][n], D[n][n];

	for (i=0; i<m; i++)
		for (j=0; j<n; j++)
		{
			
			k++;
			if(k<=26)
			{
				A[i][j] = x;
				x++;
			}
			else
				A[i][j] = ' ';
		}

	for (i=0; i<m; i++)
		{
			for(j=0; j<n; j++)
				printf("%c",A[i][j]);
			printf("\n");
		}

	printf("\n");

	i = 0;
	while (i<n)
	{
		printf("Enter row number of letter %d: ", i+1);
		scanf("%d",&y);

		for (j=0; j<n; j++)
			B[i][j] = A[y-1][j];
		i++;
	}

	printf("\n");

	for (i=0; i<n; i++)
		{
			for(j=0; j<n; j++){
				C[i][j]=B[j][i];
				printf("%c",C[i][j]);
			}
			printf("\n");
		}

	printf("\n");

	i = 0;
	while (i<n)
	{
		printf("Enter row number of letter %d: ", i+1);
		scanf("%d",&y);

		for (j=0; j<n; j++)
			D[i][j] = C[y-1][j];
		i++;
	}

	for (i=0; i<n; i++)
	{
		for (j=0; j<n; j++)
		{
			if(i==j)
				printf("%c",D[i][j]);
			else
				printf(" ");
		}
		printf("\n");
	}
}
