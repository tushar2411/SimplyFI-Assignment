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

