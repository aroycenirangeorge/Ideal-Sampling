## **IDEAL SAMPLING**  

### **AIM**  
To perform ideal sampling on a continuous-time signal and reconstruct it using Python.  

### **APPARATUS REQUIRED**  
- Python IDE  

### **PROGRAM**  
```python
# Ideal Sampling (Impulse Sampling) and Reconstruction

import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample

# Define sampling parameters
fs = 100  # Sampling frequency (Hz)
t = np.arange(0, 1, 1/fs)  # Time vector
f = 5  # Signal frequency (Hz)

# Generate continuous-time signal
signal = np.sin(2 * np.pi * f * t)

# Plot continuous-time signal
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Perform sampling
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)

# Plot sampled signal
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Reconstruct the signal
reconstructed_signal = resample(signal_sampled, len(t))

# Plot reconstructed signal
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
```

### **PROGRAM OUTPUT**  
![image](https://github.com/user-attachments/assets/e0d2976f-4a6d-4a2f-9a1e-07ad3540275a)
![image](https://github.com/user-attachments/assets/9017b015-cff1-4903-b836-98ca71fdd852)
![image](https://github.com/user-attachments/assets/a552f5e3-4251-40cf-904a-ae663c560bf1)


### **RESULT**  
Thus, ideal sampling and reconstruction of a continuous-time signal were successfully performed using Python.
