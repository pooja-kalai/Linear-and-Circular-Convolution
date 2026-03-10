# EXP 1 : Linear and Circular Convolution

## AIM: 

 To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 
```
clc;
clear;
x = [1 2 3 4];
h = [1 1 1];
lx = length(x);
lh = length(h);
ly = lx + lh - 1;
y = zeros(1, ly);
for n = 1:ly
    for k = 1:lx
        if (n - k + 1 > 0) & (n - k + 1 <= lh) then
            y(n) = y(n) + x(k) * h(n - k + 1);
        end
    end
end
disp("first sequence x(n) = " + string(x));
disp("second sequence h(n) = " + string(h));
disp("linear convolution y(n) = " + string(y));
clf;
subplot(3,1,1);
plot2d3(0:lx-1, x);
xlabel("n");
ylabel("x(n)");
title("first sequence");
subplot(3,1,2);
plot2d3(0:lh-1, h);
xlabel("n");
ylabel("h(n)");
title("second sequence");subplot(3,1,3);
plot2d3(0:ly-1, y);
xlabel("n");
ylabel("y(n)");
title("linear convolution");
```

## PROGRAM (Circular Convolution): 
```
clc;
clear;
x = [1 2 3 4];
h = [1 1 1];
lx = length(x);
lh = length(h);
N = max(lx, lh);
x1 = [x zeros(1, N-lx)];
h1 = [h zeros(1, N-lh)];
y = ifft(fft(x1) .* fft(h1));
disp("first sequence x(n) = " + string(x));
disp("second sequence h(n) = " + string(h));
disp("circular convolution y(n) = " + string(real(y)));
clf;
subplot(3,1,1);
plot2d3(0:lx-1, x);
xlabel("n");
ylabel("x(n)");
title("first sequence");
subplot(3,1,2);
plot2d3(0:lh-1, h);
xlabel("n");
ylabel("h(n)");
title("second sequence");
subplot(3,1,3);
plot2d3(0:N-1, real(y));
xlabel("n");
ylabel("y(n)");
title("circular convolution");
```

## OUTPUT (Linear Convolution): 
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/cfe6707b-9fcd-40c2-869b-0c70a31eef67" />

## OUTPUT (Circular Convolution): 
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/abae1de1-0df8-4e23-98c5-ff8120b65798" />

## RESULT: 

Thus, the linear convolution and circular convolution of the two given sequences were performed and its result was verified.
