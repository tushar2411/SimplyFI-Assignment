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

