# MIGRATORY-BIRDS-HACKERANK-3-APPROACHES

Here we explain three approaches to this coding challenge, we check the timing with 1 millon iterations for each, and found that the third approach is the more simpler and faster approach than th first and second approaches.

The challenge is as follows: 

Migratory birds

Given an array of bird sightings where every element represents a bird type id, determine the id of the most frequently sighted type. If more than 1 type has been spotted that maximum amount, return the smallest of their ids.

Example

arr = [1,1,2,2,3]

There are two each of types 1,2 and , and one sighting of type 3. Pick the lower of the two types seen twice: type 1.

Function Description

Complete the migratoryBirds function in the editor below.

migratoryBirds has the following parameter(s):

int arr[n]: the types of birds sighted
Returns

int: the lowest type id of the most frequently sighted birds
Input Format

The first line contains an integer,n , the size of arr.
The second line describes r   as n space-separated integers, each a type number of the bird sighted.

Constraints

5 <= n<= 2 x 10**5

It is guaranteed that each type is1,2,3,4, or 5.
Sample Input 0

6
1 4 4 4 5 3
Sample Output 0

4


Sample Input 1

11
1 2 3 4 5 4 3 2 1 3 4
Sample Output 1

3

APPROACH 1:

1.    Definition of the function "migratoryBirds": The function takes an input "arr" which is a list of integers representing different types of birds that have been sighted.

2. Initialization of a dictionary: A dictionary called "dict" is initialized with keys from 1 to 5 and values 0. This dictionary will be used to count the number of occurrences of each type of bird in the list "arr".

3. Loop over the input list: The function then loops over the input list "arr". For each element "i" in the list, the count of that type of bird in the dictionary is increased by 1. This is done using the following line of code: dict[i] = dict[i] + 1 

4. Return the type of bird with the maximum count: Finally, the function returns the type of bird that has the maximum count. This is done using the following line of code:return max(dict,key = dict.get)

5. The max() function returns the key with the maximum value in the dictionary. The key argument specifies the function to extract the comparison key from each element in the iterable, in this case, the dict.get method is used which returns the value of the specified key. So, the key with the maximum value is returned as the result of the function. 

The code for APPROACH 1 is [here](code1a)

The timing for APPROACH 1 WITH 1000000 ITERATIONS is  9.87 SECONDS.  See the code [here](code1b)

APPROACH 2

1. Importing the "Counter" function from the "collections" module: The "Counter" function is imported from the "collections" module. This function takes an iterable as input and returns a dictionary with the elements of the iterable as keys and their count as values.

2. Definition of the function "migratoryBirds": The function takes an input "arr" which is a list of integers representing different types of birds that have been sighted.

3. Sorting and counting the occurrences of each type of bird: The input list "arr" is sorted using the sorted() function, and the occurrences of each type of bird are counted using the "Counter" function. The result is stored in the variable "x".

4. Return the type of bird with the maximum count: Finally, the function returns the type of bird that has the maximum count. This is done using the following line of code:return max(x,key=x.get)

5. The max() function returns the key with the maximum value in the dictionary "x". The key argument specifies the function to extract the comparison key from each element in the iterable, in this case, the x.get method is used which returns the value of the specified key. So, the key with the maximum value is returned as the result of the function.

This implementation is more concise and efficient than the previous one, as it uses the "Counter" function to count the occurrences of each type of bird in a single line of code.

The code for APPROACH 2 is [here](code2a)

The timing for APPROACH 2  with 1 millon iterations is 12.27 seconds.  See the code [here](code2b)

APPROACH 3
1. Definition of the function "migratoryBirds": The function takes an input "arr" which is a list of integers representing different types of birds that have been sighted.

2. Initialization of a list "count": A list called "count" is initialized with 6 zeros, representing the number of occurrences of each type of bird, with index 1 representing bird type 1, index 2 representing bird type 2, and so on.

3. Loop over the input list "arr": The function then loops over the input list "arr". For each element "bird" in the list, the count of that type of bird in the "count" list is increased by 1. This is done using the following line of code:
count[bird] += 1

4. Finding the maximum count: The maximum count of all bird types is found using the following line of code:
    max_count = max(count)
    
5. Finding the type of bird with the maximum count: The function then loops over the range from 1 to 6. For each iteration, it checks if the count of the current bird type is equal to the maximum count. If it is, the function returns the current bird type as the result. This is done using the following code:
    for i in range(1, 6):
        if count[i] == max_count:
            return i
            
This implementation is straightforward and efficient, as it uses a list to store the counts of each bird type and then finds the maximum count in a single pass.

The code for APPROACH 3 is [here](code3a)

The timing for APPROACH 3  with 1 millon iterations is 8.93 seconds. See the code [here](code3b)

The more efficient in timing for this challenge is APPROACH 3.




