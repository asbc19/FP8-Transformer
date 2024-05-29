Files generated for each attention head:  
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