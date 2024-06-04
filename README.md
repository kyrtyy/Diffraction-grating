# Diffraction-grating
to generate a intensity vs angle for a diffraction grating
import numpy as np
import matplotlib.pyplot as plt

# parameters
slit_width = 5e-5  #(meters)
slit_sep = 3e-4  # Slits_separation (meters) 
l = 600e-9  # Wavelength (meters)
n = 400 # Number of slits

# Calculation for Intensity
theta = np.linspace(-np.pi/500, np.pi/500, 1000)
beta = np.pi * slit_width * np.sin(theta) / l
alpha = np.pi * slit_sep * np.sin(theta) / l

Intensity = (np.sin(beta)/beta)**2 * (np.sin(n*alpha)/np.sin(alpha))**2

# Plotting

plt.plot(theta*180/np.pi, Intensity,c="purple",linewidth=2)
plt.xlabel(r"$\theta$ ($^\circ$)")
plt.ylabel(r"Intensity")
plt.grid(True)
plt.title("Intensity Distribution for Diffraction Grating using "+ str(n)+" slits")
plt.show()
