# Pascal Triangle
Create a function def pascal_triangle(n): that returns a list of lists of integers representing the Pascal’s triangle of n:

- Returns an empty list if n <= 0
- You can assume n will be always an integer


# Description of Solution
def pascal_triangle(n):: This line defines a function called pascal_triangle that takes an integer n as a parameter. This function calculates and returns Pascal's triangle for the given number.

triangle = []: This creates an empty list called triangle to store the rows of Pascal's triangle.

if n <= 0: return triangle: If the given number n is less than or equal to 0, the function returns an empty triangle.

for i in range(n):: This loop iterates i from 0 to n-1, representing each row of Pascal's triangle.

temp_list = []: This creates an empty list called temp_list to store the numbers in the current row of the triangle.

for j in range(i+1):: This loop iterates j from 0 to i, representing each number in the current row.

if j == 0 or j == i: temp_list.append(1): If j is the first or last number in the row (0 or i), it is set to 1 because these are the edge numbers of Pascal's triangle.

else: temp_list.append(triangle[i-1][j-1] + triangle[i-1][j]): For the numbers in between the edge numbers, they are the sum of the two numbers directly above them in the previous row of Pascal's triangle.

triangle.append(temp_list): The completed row is added to the triangle list.

return triangle: Finally, the function returns the completed Pascal's triangle as a list of lists of integers.
