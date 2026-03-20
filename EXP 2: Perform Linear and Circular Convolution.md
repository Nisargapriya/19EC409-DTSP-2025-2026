# EXP 1 : Linear and Circular Convolution

## AIM: 

 To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 
```
// Linear Convolution
clc;
clear;

// --- Input sequences ---
x = [1 1 2 1];
h = [1 2 3 4];

N = length(x) + length(h) - 1;

// --- Zero Padding ---
x1 = [x, zeros(1, N - length(x))];
h1 = [h, zeros(1, N - length(h))];

// --- FFT Method ---
X = fft(x1, -1);
H = fft(h1, -1);
Y = X .* H;
y_lin = real(fft(Y, 1));

// --- Display Result ---
disp(y_lin, "Linear Convolution Result:");

// --- Plotting ---
n = 0:N-1;

subplot(3,1,1);
plot2d3(0:length(x)-1, x);
xtitle("Input Sequence x(n)", "n", "Amplitude");

subplot(3,1,2);
plot2d3(0:length(h)-1, h);
xtitle("Impulse Response h(n)", "n", "Amplitude");

subplot(3,1,3);
plot2d3(n, y_lin);
xtitle("Linear Convolution Result y(n)", "n", "Amplitude");



```

## PROGRAM (Circular Convolution): 
```
// Circular Convolution
clc;
clear;
clf;   // clear previous graphs

// --- Input Sequences ---
x1 = [1 -1 -2 3 -1];
x2 = [1 2 3];

N = max(length(x1), length(x2));

// --- Zero Padding ---
x1p = [x1, zeros(1, N - length(x1))];
x2p = [x2, zeros(1, N - length(x2))];

// --- FFT Method for Circular Convolution ---
X1 = fft(x1p, -1);
X2 = fft(x2p, -1);
Y  = X1 .* X2;
y_circ = real(fft(Y, 1));

// --- Display Result ---
disp("Circular Convolution Result:");
disp(y_circ);

// --- Plotting ---
figure();   // open graph window

n = 0:N-1;

// Input x1
subplot(3,1,1);
plot2d3(0:length(x1)-1, x1);
xtitle("Input Sequence x1(n)", "n", "Amplitude");

// Input x2
subplot(3,1,2);
plot2d3(0:length(x2)-1, x2);
xtitle("Input Sequence x2(n)", "n", "Amplitude");

// Output
subplot(3,1,3);
plot2d3(n, y_circ);
xtitle("Circular Convolution Result", "n", "Amplitude");

```
## OUTPUT (Linear Convolution): 
<img width="819" height="714" alt="image" src="https://github.com/user-attachments/assets/70ee89c7-ab0f-471c-99e8-9cfda5f02cae" />

## OUTPUT (Circular Convolution): 
<img width="845" height="679" alt="image" src="https://github.com/user-attachments/assets/14efee7a-46e5-4bde-9b7d-dbf6e71f5c27" />

## RESULT: 
The linear and circular convolution of the given sequences were successfully performed using Scilab and the corresponding output sequences were obtained
