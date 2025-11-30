# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.



__Algorithm__:

```c
import numpy as np
import matplotlib.pyplot as plt

Pt = 1000
G = 40
lam = 0.05       # renamed (lambda is keyword in Python)
sigma = 10
pi4 = (4*np.pi)**3

R = np.linspace(1000, 200000, 500)
Pr_R = (Pt * G**2 * lam**2 * sigma) / (pi4 * R**4)

plt.figure(1)
Pr_R_dB = 10 * np.log10(Pr_R)
plt.plot(R/1000, Pr_R_dB)
plt.xlabel("Range (km)")
plt.ylabel("Power Received (dB)")

Pt_values = np.linspace(100, 10000, 500)
R_fixed = 50000

Pr_Pt = (Pt_values * G**2 * lam**2 * sigma) / (pi4 * (R_fixed**4))

plt.figure(2)
plt.plot(Pt_values, Pr_Pt)
plt.xlabel("Power Transmitted (W)")
plt.ylabel("Power Received (W)")

G_values = np.linspace(5, 60, 500)
Pt_fixed = 3000

Pr_G = (Pt_fixed * G_values**2 * lam**2 * sigma) / (pi4 * (R_fixed**4))

plt.figure(3)
plt.plot(G_values, Pr_G)
plt.xlabel("Gain (Linear)")
plt.ylabel("Power Received (W)")

plt.show()




```


 
   __Output__:
   
![WhatsApp Image 2025-11-30 at 11 42 35_499d48a2](https://github.com/user-attachments/assets/ff8a6c18-d536-42bc-84a8-ebe50299bd51)

![WhatsApp Image 2025-11-30 at 11 53 31_339af107](https://github.com/user-attachments/assets/bb47c9ab-4370-414f-8bac-205b82868a02)

![WhatsApp Image 2025-11-30 at 11 54 45_e1ed4ace](https://github.com/user-attachments/assets/42462cd7-8ca2-45ef-9b66-751e1121cd7c)







   ![WhatsApp Image 2025-11-30 at 11 56 24_5f29881a](https://github.com/user-attachments/assets/c0bb3603-576b-4666-81c7-e0b236db487c)

   




