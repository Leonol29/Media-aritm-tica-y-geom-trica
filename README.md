Media-aritm-tica-y-geom-trica
Google colab código
import random
import math

flag = 0
"""Calculates the geometric mean of a list of numbers."""
def geometric_mean(data):
    product = 1
    for x in data:
        product *= x
    return product**(1/len(data))

"""Calculates the arithmetic mean of a list of numbers."""
def arithmetic_mean(data):
    return sum(data) / len(data)

# Get the number of random numbers to generate from the user
n = int(input("Enter the number of random numbers to generate: "))

for i in range(1000000):
    # Generate n random numbers between 0 and 1000
    random_numbers = [random.uniform(0, 1000) for _ in range(n)]

    # Compare
    if arithmetic_mean(random_numbers) < geometric_mean(random_numbers):
        print(f"Arithmetic Mean: {arithmetic_mean(random_numbers)}")
        print(f"Geometric Mean: {geometric_mean(random_numbers)}")

        flag = 1

if flag == 0:
    print("MA always bigger than MG.")
else:
    print("There exists one case where MA is smaller than MG.")
