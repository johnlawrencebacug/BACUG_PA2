# PROGRAMMING ASSIGNMENT_2
### Bacug, John Lawrence B. | 2ECE-C
### Date Submitted: September 3, 2026

## Objectives:
Write Python code in a Jupyter Notebook to solve each problem. Import NumPy as np. Place each
problem in a separate, clearly labeled section of the notebook. 
* Use NumPy array operations. Do not use Python loops or list comprehensions to perform the required numerical calculations or filtering.
* Do not hard-code a computed result. Construct every result from the array specified in the problem.
* Use the exact variable and output filenames stated below.
* Display the requested checks in the notebook before saving each result.
* Do not use libraries other than NumPy

## PROBLEM A
* Pseudorandom Seed Initialization Configured `np.random.seed(2112)` to constrain the internal state of the pseudo-random number generator, enabling complete replication of generated data values across environments.
* Matrix Instantiation
Constructed a 5x5 matrix (X) populated with integer values sampled uniformly from the discrete range `[10, 101)` utilizing `np.random.randint()`.
* Parametric Computation
Calculated the aggregate population mean (x_bar) and standard deviation (sigma) over all 25 array entries using `np.mean()` and `np.std()`.
* Linear Transformation
Applied Z-score normalization across the elements via array broadcasting according to the standard transformation equation:
`X_normalized = (X - x_bar)/sigma`
* Validation & Storage
Evaluated the central tendency and dispersion of X_normalized to verify standard scaling compliance, subsequently serializing the array to `X_normalized.npy` via `np.save()`.

```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

x_bar = np.mean(X)

sigma = np.std(X)

X_normalized = (X - x_bar) / sigma

np.save('X_normalized.npy', X_normalized)
```


## PROBLEM B
* Creating and Reshaping the Matrix Generated a simple numbers sequence from 1 to 100 using `np.arange()` and converted it into a 10 \times 10 matrix (C) using `C.resize(10, 10)`.
* Filtering with Boolean Masks
Created a logical check `(C % 4 == 0)` to test which elements have no remainder when divided by 4, extracting those values into a 1D array `(div_by_4)`.
* Counting and Saving
Checked the total count of matched elements using `.size` and saved the filtered array to a file named `div_by_4.npy` via `np.save()`.

```python
C = np.arange(1, 101)
C.resize(10, 10)

div_by_4 = C[C % 4 == 0]

div_by_4.size

np.save('div_by_4.npy', div_by_4)
```


## PROBLEM C
