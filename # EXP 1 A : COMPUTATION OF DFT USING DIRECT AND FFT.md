# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 


# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
```
clc;
clear;

// --- Input Signal ---
x = [1 2 3 4];   
N = length(x);
n = 0:N-1;

// --- Direct DFT (Formula Method) ---
X_dft = zeros(1, N);
for k = 0:N-1
    for m = 0:N-1
        X_dft(k+1) = X_dft(k+1) + x(m+1) * exp(-%i*2*%pi*k*m/N);
    end
end

// --- FFT (Built-in Function) ---
X_fft = fft(x, -1);

// --- Plots ---
subplot(3,1,1);
plot2d3(n, x);   // discrete stem-like graph
title("Input Signal x[n]");
xlabel("n"); ylabel("x[n]");

subplot(3,1,2);
plot2d3(n, abs(X_dft));   // DFT magnitude
title("DFT Magnitude (Direct Method)");
xlabel("k"); ylabel("|X[k]|");

subplot(3,1,3);
plot2d3(n, abs(X_fft));   // FFT magnitude
title("FFT Magnitude (Built-in)");
xlabel("k"); ylabel("|X[k]|");
```

# OUTPUT: 
<img width="1915" height="1078" alt="image" src="https://github.com/user-attachments/assets/d32b4a52-8d7c-4d35-9d1e-810fac31e63f" />


# RESULT: 
The DFT of the given sequence using Direct method and FFT method are obtained.
