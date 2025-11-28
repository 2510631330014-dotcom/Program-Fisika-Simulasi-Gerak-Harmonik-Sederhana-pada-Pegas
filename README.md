# Program-Fisika-Simulasi-Gerak-Harmonik-Sederhana-pada-Pegas
import matplotlib.pyplot as plt
import math

print("=== SIMULASI GERAK HARMONIK PEGAS ===")
print("Program ini mensimulasikan gerak benda pada pegas (Hukum Hooke).")

# Input parameter fisika
k = float(input("Masukkan konstanta pegas k (N/m): "))
m = float(input("Masukkan massa beban m (kg): "))
A = float(input("Masukkan amplitudo awal A (meter): "))

# Menghitung frekuensi sudut
omega = math.sqrt(k / m)

# Set waktu simulasi
t = 0
dt = 0.05
t_max = 10  # lama simulasi 10 detik

# List untuk data plot
time_data = []
x_data = []

# Looping simulasi
while t <= t_max:
    x = A * math.cos(omega * t)  # posisi benda

    # If condition — cek batas tertentu (opsional)
    if abs(x) > A:
        print("Error: posisi benda melebihi batas amplitudo.")
        break

    time_data.append(t)
    x_data.append(x)

    print(f"t = {t:.2f} s | posisi x = {x:.3f} meter")

    t += dt

# Plotting grafik
plt.plot(time_data, x_data)
plt.title("Simulasi Gerak Harmonik Pegas")
plt.xlabel("Waktu (s)")
plt.ylabel("Posisi (m)")
plt.grid(True)
plt.show()
