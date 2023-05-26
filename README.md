# SimplyFI-Assignment

# Question 1
Write a python code for converting integer values to Indian currency notations, without
using the currency libraries
Example:
input: 504678
output: 5,04,67

```
def formatINR(number):
    s, *d = str(number).partition(".")
    r = ",".join([s[x-2:x] for x in range(-3, -len(s), -2)][::-1] + [s[-3:]])
    return "".join([r] + d)

amount = 504678
formatted_amount = formatINR(amount)
print(formatted_amount)
```
![image](https://github.com/tushar2411/SimplyFI-Assignment/assets/97248089/44c87b1b-d40b-46f9-a273-65cb08883f3f)



The formatINR function takes a number as input and returns a formatted string representing the amount in Indian Rupees (INR).

s, *d = str(number).partition("."): This line converts the input number to a string and separates it into two parts: the integer part (s) and the decimal part (d), if any. The dot (".") is used as the separator.

r = ",".join([s[x-2:x] for x in range(-3, -len(s), -2)][::-1] + [s[-3:]]): This line formats the integer part (s) of the number. It does the following steps:

It loops through the integer part of the number in reverse order, taking groups of two digits at a time.
Each group of two digits is joined with a comma.
The resulting groups are reversed again to get the correct order.
The last three digits of the integer part are added separately without a comma.
The final formatted integer part is assigned to the variable r.
return "".join([r] + d): This line combines the formatted integer part (r) with the decimal part (d), if any, to form the final formatted string. The two parts are joined together without any additional characters.

amount = 504678: Here, we define a variable amount with the value 504678, representing the input number.

formatted_amount = formatINR(amount): The formatINR function is called with the amount as the argument, and the returned formatted string is assigned to the variable formatted_amount.

print(formatted_amount): Finally, the formatted amount is printed to the console.


# Question 2
You won’t get caught if you hide behind someone.”
Sang-Woo advises Gi-Hun to hide behind someone to avoid getting shot.
Gi-Hun follows Sang-Woo's advice and hides behind Ali, who saved his life earlier. Gi-Hun and Ali
both have the same height, K
. Many players saw this trick and also started hiding behind Ali.
Now, there are N
players standing between Gi-Hun and Ali in a straight line, with the ith player having height Hi
. Gi-Hun wants to know the minimum number of players who need to get shot so that Ali is visible
in his line of sight.

```
# Function to solve the problem for a single test case
def minimumShots(N, K, heights):
    shots = 0

    for height in heights:
        if height > K:
            shots += 1
        if height == K:
            break

    return shots


# Input
input_data = [
    (4, 10, [2, 13, 4, 16]),
    (5, 8, [9, 3, 8, 8, 4]),
    (4, 6, [1, 2, 3, 4])
]

# Solve the problem for each test case
for test_case in input_data:
    N, K, heights = test_case

    # Call the function to solve the problem for the current test case
    result = minimumShots(N, K, heights)

    # Print the result for the current test case
    print(result)
    ```
    
    ![image](https://github.com/tushar2411/SimplyFI-Assignment/assets/97248089/5f77c657-9a9f-4513-a273-2dcee78c9562)
    
    
    We define a function minimumShots that takes three parameters: N, K, and heights. This function is responsible for solving the problem for a single test case.

Inside the minimumShots function, we initialize a variable shots to keep track of the number of players who need to get shot. This variable starts at 0.

I iterate over each height in the heights list, which represents the heights of the players.

For each player's height, we check if it is greater than K, the height of Gi-Hun and Ali. If a player's height is greater than K, it means they are taller than Gi-Hun and Ali, and they need to get shot. In this case, we increment the shots variable by 1.

Additionally, if a player's height is equal to K, it means they have the same height as Gi-Hun and Ali. According to the problem statement, even if there are players with the same height, Ali will be visible in Gi-Hun's line of sight. Therefore, we break out of the loop at this point.

After iterating through all the players' heights, we return the value of shots, which represents the minimum number of players who need to get shot in order for Ali to be visible to Gi-Hun.

The code then defines an input_data list that contains multiple test cases. Each test case is represented as a tuple (N, K, heights), where N is the number of players, K is the height of Gi-Hun and Ali, and heights is the list of heights of the players between Gi-Hun and Ali.

The code then loops over each test case in the input_data list.

For each test case, it extracts the values of N, K, and heights from the tuple.

It calls the minimumShots function with the extracted values to solve the problem for the current test case.

The result is stored in the result variable.

Finally, the result is printed for each test case.

