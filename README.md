# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Hamming and Shannon-Fano Code

# AIM
To implement Huffman and Shannon-Fano coding for a discrete memoryless source with given probabilities and analyze the efficiency, redundancy, and variance.

# SOFTWARE REQUIRED
Python 

# ALGORITHMS
1. Start
2. Input symbols and their probabilities.
3. Sort symbols:
   - Huffman: Ascending order.
   - Shannon-Fano: Descending order.
4. Generate codewords:
   - Huffman: Combine smallest probabilities until one node remains.
   - Shannon-Fano: Split list recursively with near-equal probabilities.
5. Calculate entropy, average length, efficiency, and redundancy.
6. Display results.
7. End


# PROGRAM
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for i in range (n): 
    l = float(input(f"Enter the length of the sample values {i + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
  var1 = p[k] * (lk[k]-L)**2
  var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")

# OUTPUT
Average Codeword Length is : 2.625
Entropy is : 2.625
Efficiency is : 1.0
Redudancy is : 0.0
Variance is : 0.484
 
# CONCLUSIONS
The experiment demonstrates the successful application of Shannon-Fano or Huffman coding, achieving optimal efficiency with no redundancy, which is ideal for data compression.
