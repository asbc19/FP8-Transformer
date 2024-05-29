**Files generated for each attention head**:  

1. Q, K, and V vectors in FP8.
    - 69 tokens embedded using 64 dimensions.
    - Matrix of size (69x64).

2. Raw scores in FP8: --> $q^{(i)} \cdot k^{(i)T}$
    - Row number --> correspoding q-vector.
    - Column number --> corresponding k-vector.
    - Matrix of size (69x69).

3. Attention scores in FP8: --> $q^{(i)} \cdot k^{(i)T} / \sqrt{64} $
    - Row number --> correspoding q-vector.
    - Column number --> corresponding k-vector.
    - Matrix of size (69x69). 

4. Attention probabilities in FP8 --> after softmax.
    - Row number --> correspoding q-vector.
    - Column number --> corresponding k-vector.
    - Matrix of size (69x69).

5. One raw score calculated in binary: q1 x k1 
    - 1st row --> q1 vector
    - 2nd row --> k1 vector
    - 3rd row --> partial products (q1[i] x k1[i])
    - 4th row --> row score padded with zeros on the right (sum(q1[i] x k1[i]))
    - q1xk1_exact.csv (decimal) and q1xk1_exact_b.csv (binary) 

**Important notes**:
- INTEL emulator works only on weights. This means that the decimal representation of weights corresponds to the decimal values that FP8 allows. On the other hand, IN/OUT keeps the decimal representation from FP32.
For this reason, it is necessary to round any decimal value to its closest FP8 representation before converting to binary.
Files with name including '_r_' are rounded to the closest FP8 representation.

- Files with name including '_r_bin_' are the binary representation of the closest FP8 value.

- Files with name including 'fp16' are FP16 decimal representations of Raw and Attention scores.

- Files with name including 'fp16_bin' are FP16 binary representations of Raw and Attention scores.