# -Frequency-Modulation-and-Demodulation-using-NumPy-and-Matplotlib-

__Aim:__

To implement and analyze frequency modulation (FM) using Python's NumPy and Matplotlib libraries.

__Apparatus Required:__ 

1. Software: Python with NumPy and Matplotlib libraries
   
2. Hardware: Personal Computer

 
__Theory:__

Frequency Modulation (FM) is a method of transmitting information over a carrier wave by varying its 
frequency in accordance with the amplitude of the input signal (message signal). The frequency of the carrier 
wave is varied according to the instantaneous amplitude of the message signal.

__Algorithm:__

1. Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and 
   frequency deviation.
   
2. Generate Time Axis: Create a time vector for the signal duration.
    
3. Generate Message Signal: Define the message signal as a cosine wave.
    
4. Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
    
5. Generate FM Signal: Apply the FM modulation formula to obtain the modulated signal.
 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Programme:__
```
import numpy as np
import matplotlib.pyplot as plt

Ac = 37.7
fc = 8900

Am = 18.9
fm = 890

fs = 89000
beta = 3.6

# Time Vector
t = np.arange(0, 2/fm, 1/fs)

# Message Signal
Em = Am * np.cos(2 * np.pi * fm * t)

# Carrier Signal
Ec = Ac * np.cos(2 * np.pi * fc * t)

# FM Signal
Efm = Ac * np.cos(2 * np.pi * fc * t + beta * np.sin(2 * np.pi * fm * t))

# Plotting
plt.figure(figsize=(10, 6))

plt.subplot(3, 1, 1)
plt.plot(t, Em)
plt.title("Message Signal")
plt.grid()

plt.subplot(3, 1, 2)
plt.plot(t, Ec)
plt.title("Carrier Signal")
plt.grid()

plt.subplot(3, 1, 3)
plt.plot(t, Efm)
plt.title("FM Signal")
plt.grid()

plt.tight_layout()
plt.show()

```

__Output:__

<img width="1189" height="990" alt="image" src="https://github.com/user-attachments/assets/f4e3a1cc-6540-41d3-ad88-a17078452c3f" />

__Result:__

<img width="1280" height="671" alt="image" src="https://github.com/user-attachments/assets/f6bcb64f-5759-4922-815f-9164a5df23b8" />

