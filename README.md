## **IDEAL SAMPLING**  

### **AIM**  
To perform ideal sampling on a continuous-time signal and reconstruct it using Python.  

### **APPARATUS REQUIRED**  
- Python IDE  

### **PROGRAM**  
```python
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
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Reconstruct the signal
reconstructed_signal = resample(signal_sampled, len(t))

# Plot only the reconstructed signal
plt.figure(figsize=(10, 4))
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

```

### **PROGRAM OUTPUT**  
![image](https://github.com/user-attachments/assets/5b28355d-6bb4-4b06-bde4-f8e1bd2e6731)
![image](https://github.com/user-attachments/assets/f95a6c82-39da-44dc-bd82-7b9c25b0305f)
![image](https://github.com/user-attachments/assets/cdd14900-fc7b-4532-b18f-07afc3a6753a)



### **RESULT**  
Thus, ideal sampling and reconstruction of a continuous-time signal were successfully performed using Python.
