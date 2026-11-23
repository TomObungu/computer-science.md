# Stage 4

It does something where it fetches the input and computes it at the same time. For example it will take in the 0th input and compute 0th input, it it will take in 1st input and compute 0th and so on. 

The 0th input is accepted. On clock cycles 1, 2 and 3, the 0th input is also processed. On clock cycles 1, 2 and 3, the 0th, 1st and 2nd inputs are also accepted. It takes $n_{r}$ clock cycles to process the 0th input. After $n_{r}$ clock cycles, $n_{r}$ inputs are processed also. At the end of the $n_{r}$th clock cycle, the $0th$ output is produced. On the $n_{r}+1$th clock cycle the $1st$ output is produced, after the $n_{r}+2$ clock cycle, the $2$nd output is produced. 

It takes 32 rounds to perform the encrypt comb operation thus I assume $n_{r}$ in this case is $32$. 

Thus I'm assuming I will need an array of 32 elements with the key length of m and k. I will also 
the r_r, r_x and r_c for module instantiation and computation. and a_ck.

On each clock cycle I will take in the input. I will then have some holding state to signal after 32 rounds whether or not the first input of computation has been down 

I'm assuming I will probably need 32 module instantiations each of them computing the corresponding input 