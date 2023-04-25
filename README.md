# Bitwise Operators and their Operations in C

In C, bitwise operators are operators that are used to perform operations on individual bits of integers. They manipulate the bits of integers at the binary level, providing low-level bit-level manipulation capabilities. 

There are six bitwise operators in C:

- **Bitwise AND (&):** This operator compares each bit of the first operand with the corresponding bit of the second operand. If both bits are 1, the result will be 1; otherwise, the result will be 0.

- **Bitwise OR (|):** This operator compares each bit of the first operand with the corresponding bit of the second operand. If either of the bits is 1, the result will be 1; otherwise, the result will be 0.

- **Bitwise XOR (^):** This operator compares each bit of the first operand with the corresponding bit of the second operand. If the bits are different (one is 0 and the other is 1), the result will be 1; otherwise, the result will be 0.

- **Bitwise NOT (~):** This operator is a unary operator and it inverts the bits of its operand. It changes 1s to 0s and 0s to 1s.

- **Left shift (<<):** This operator shifts the bits of the left operand to the left by a specified number of positions. The vacant positions on the right are filled with zeros.

- **Right shift (>>):** This operator shifts the bits of the left operand to the right by a specified number of positions. The vacant positions on the left are filled with zeros (for unsigned integers) or with the sign bit (for signed integers).

Bitwise Operators:

![Bitwise Operators](https://examradar.com/wp-content/uploads/2016/10/Bitwise-operators.png)

Bitwise operators can be used to perform various operations such as setting or clearing individual bits, checking the status of specific bits, or performing bit-level manipulations in C programming. They are commonly used in low-level programming, embedded systems, and device drivers.

The program in this repository demonstrates the usage of bitwise operators to perform operations such as converting an integer to its binary equivalent, counting the number of 1s in a number, checking if a number is a power of two or not, among others.

### Code:

```
/* Using bitwise operators write programs:
	1. to perform AND operation of two numbers
	2. to perform OR operation of two numbers
	3. to perform XOR operation of two numbers
	4. to count number of 1s in an integer number
	5. to check if a number is even or odd
	6. to check if a number is a power of two or not
	7. to print a number in binary
*/

#include <stdio.h>

#define SIZE sizeof(int) * 4

int main()
{
	int n1, n2, x, y, z, choice;
	int count = 0;
	int copy;
	
	printf("Bitwise Operations:\n\n1 - AND, OR, XOR of two numbers\n2 - Count the number of 1s in an integer\n3 - Check if a number is even or odd\n4 - Check if a number is a power of two or not\n5 - Print a number in binary\n\n");
	printf("Enter a number from the list above: ");
	scanf("%d", &choice);
	
	printf("\n\n\n");
	
	switch(choice)
	{
		case 1:
		{
			// AND, OR, XOR of two numbers
			
			printf("Entered choice: 1\n\n");
			
			printf("Enter the first number: ");
			scanf("%d", &n1);
			printf("Enter the second number: ");
			scanf("%d", &n2);
	
			printf("\n");
	
			printf("AND of two numbers: %d\n", n1 & n2);
			printf("OR of two numbers: %d\n", n1 | n2);
			printf("XOR of two numbers: %d\n", n1 ^ n2);
			
			break;	
		}
		case 2:
		{
			// count the number of 1s in an integer
			
			printf("Entered choice: 2\n\n");
			
			printf("Enter a number: ");
			scanf("%d", &x);
			
			copy = x;
			
			do
			{
				if(copy & 1)
				{
					count++;
				}
				
				copy = copy >> 1;
				
			}while(copy != 0);
			
			printf("Number of 1s in the entered integer's binary form: %d\n", count);
			
			break;
		}
		case 3:
		{
			// check if a number is even or odd
			
			printf("Entered choice: 3\n\n");
			
			printf("Enter a number: ");
			scanf("%d", &x);
			
			(x & 1 != 0) ? 
				printf("Odd number.\n") :
				printf("Even number.\n");

			break;
		}
		case 4:
		{
			// check if a number is a power of two or not
			
			printf("Entered choice: 4\n\n");
			
			printf("Enter a number: ");
			scanf("%d", &y);
			
			copy = y;
			
			do
			{
				if(copy & 1)
				{
					count++;
				}
				
				copy = copy >> 1;
				
			}while(copy != 0);
			
			
			(count == 1) ? 
				printf("The entered number is a power of 2.\n") :
				printf("The entered number is not a power of 2.\n");
					
			break;
		}
		case 5:
		{
			// print a number in binary
			// check

			int binary[SIZE];
			int index = SIZE - 1;
			int i;
			
			printf("Entered choice: 5\n\n");
			
			printf("Enter a number: ");
			scanf("%d", &z);

			while(index >= 0)
			{
				// storing LSB of the number into the binary array
				binary[index] = z & 1;

				index--;

				// right-shifting the number z by 1
				z >>= 1;
			}
			
			printf("The entered number in binary is:\n");

			// printing the converted number
			for(i = 0; i < SIZE; i++)
			{
				printf("%d", binary[i]);
			}
			
			break;
		}
		default:
		{
			printf("Invalid choice. Terminating...\n\n");
			
			break;
		}
	}
	
	return 0;
		
}
```

### Outputs:

![OP1](https://user-images.githubusercontent.com/88421625/234431141-4e507e78-9825-4b56-b297-1ede4e61eeb6.png)

![OP2](https://user-images.githubusercontent.com/88421625/234431142-a992902e-12ea-4aa3-bd50-d24e74ce8fe0.png)

![OP3](https://user-images.githubusercontent.com/88421625/234431143-a323c2e3-41cb-4b17-9f7e-cf76891dd672.png)

![OP4](https://user-images.githubusercontent.com/88421625/234431145-05eedbb6-0b48-469a-87d6-2ef5a4e04357.png)

![OP5](https://user-images.githubusercontent.com/88421625/234431178-61f0f125-812b-4e4a-b817-16ad8b9f60ea.png)

![OP6](https://user-images.githubusercontent.com/88421625/234431181-c42b91f3-22ef-48e4-9565-2c818c4c1889.png)

![OP7](https://user-images.githubusercontent.com/88421625/234431182-b4775265-03d9-43a5-b16d-fee19e48a486.png)
