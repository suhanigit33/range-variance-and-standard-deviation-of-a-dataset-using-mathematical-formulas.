# range-variance-and-standard-deviation-of-a-dataset-using-mathematical-formulas.
rang variance and standard deviation
from math import sqrt

# Function to compute range, variance, and standard deviation
def compute_stats(data):
    n = len(data)
    if n == 0:
        print("Empty dataset. Nothing to compute.")
        return
    
  print("\n--- DATASET DETAILS ---")
    print(f"Data: {data}")
    print(f"Total number of items (n) = {n}")
    
  # Range
  print("\n--- STEP 1: RANGE ---")
    data_range = max(data) - min(data)
    print(f"Max = {max(data)}, Min = {min(data)}")
    print(f"Range = Max - Min = {data_range}")
    
   # Mean
  print("\n--- STEP 2: MEAN ---")
    mean = sum(data) / n
    print(f"Mean = (Sum of observations) / n = {sum(data)} / {n} = {mean:.3f}")
    
  # Deviations and Squared Deviations
   print("\n--- STEP 3: DEVIATIONS AND SQUARED DEVIATIONS ---")
    print(f"{'Value':>10} {'Deviation (x - mean)':>25} {'Squared Deviation':>25}")
    deviations = []
    sq_devs = []
   for x in data:
        dev = x - mean
        sq = dev ** 2
        deviations.append(dev)
        sq_devs.append(sq)
        print(f"{x:>10.2f} {dev:>25.3f} {sq:>25.3f}")
    
   sum_sq = sum(sq_devs)
    print(f"\nSum of squared deviations = {sum_sq:.3f}")
    
  # Variance and Standard Deviation
   print("\n--- STEP 4: VARIANCE AND STANDARD DEVIATION ---")
    pop_variance = sum_sq / n
    pop_std = sqrt(pop_variance)
    print(f"Population Variance (σ²) = {sum_sq:.3f} / {n} = {pop_variance:.3f}")
    print(f"Population Standard Deviation (σ) = sqrt({pop_variance:.3f}) = {pop_std:.3f}")
    
   if n > 1:
        sample_variance = sum_sq / (n - 1)
        sample_std = sqrt(sample_variance)
        print(f"\nSample Variance (s²) = {sum_sq:.3f} / ({n}-1) = {sample_variance:.3f}")
        print(f"Sample Standard Deviation (s) = sqrt({sample_variance:.3f}) = {sample_std:.3f}")
   else:
        print("\nSample variance not defined for n = 1.")
    
  print("\n--- FINAL RESULTS ---")
    print(f"Range = {data_range}")
    print(f"Mean = {mean:.3f}")
    print(f"Population Variance = {pop_variance:.3f}")
    print(f"Population Standard Deviation = {pop_std:.3f}")
    if n > 1:
        print(f"Sample Variance = {sample_variance:.3f}")
        print(f"Sample Standard Deviation = {sample_std:.3f}")

# --- MAIN PROGRAM ---
print("Enter the dataset (numbers separated by spaces):")
user_input = input("→ ")
data = [float(x) for x in user_input.split()]
compute_stats(data)
