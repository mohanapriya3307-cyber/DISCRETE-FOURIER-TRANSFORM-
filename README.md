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
xn=[1 2 3 4 4 3 2 1];
n1=0:1:length(xn)-1;
subplot(3,1,1);
plot2d3(n1,xn);
xlabel('Time n');
ylabel('Amplitude xn');
title('Input Sequence');
j=sqrt(-1);
N=length(xn);
Xk=zeros(1,N);
for k=0:N-1
for n=0:N-1
Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N);
end
end
disp(Xk)
K1=0:1:length(Xk)-1;
magnitude=abs(Xk)
subplot(3,1,2);
plot2d3(K1,magnitude);
xlabel('frequency(Hz)');
ylabel('magnitude(gain)');
title('magnitude spectrum');
angle = atan(imag(Xk),real(Xk))
subplot(3,1,3);
plot2d3(K1,angle);
xlabel('frequency(Hz)');
ylabel('Phase');
title('Phase spectrum');
```
//FAST FOURIER TRANSFORM
```
clear;
clc;
close;
xn = [1 2 3 4 4 3 2 1]
n1=0:1:length(xn)-1;
subplot(2,2,1);
plot2d3(n1,xn);
xlabel('Time n');
ylabel('Amplitude');
title('Input Sequence');
Xk = fft(xn);
K1=0:1:length(Xk)-1;
magnitude=abs(Xk)
subplot(2,2,2);
plot2d3(K1,magnitude);
xlabel('frequency(Hz)');
ylabel('magnitude(gain)');
title('magnitude spectrum');
angle = atan(imag(Xk),real(Xk))
subplot(2,2,3);
plot2d3(K1,angle);
xlabel('frequency(Hz)');
ylabel('Phase');
title('Phase spectrum')
y= ifft(Xk)
n2=0:1:length(y)-1;
subplot(2,2,4)
plot2d3(n2,y)
xlabel('Time n');
ylabel('Amplitude');
title('Inverse FFT OF X(K)');
```

# OUTPUT: 
//DFT

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/7845829c-1d75-4f3b-92c2-379befe7e6bf" />

//FFT

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/409b1ef9-1a07-4a18-8890-e30cb2927e16" />

# RESULT: 
