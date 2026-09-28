# 📅 Day 1: Introduction to Bandgap Voltage Reference

## 📘 Concepts Covered

- Introduction to Bandgap Voltage Reference (BGR)
- Why a BGR is needed
- Applications of BGR
- Principle of BGR (CTAT + PTAT)
- BGR types
- Components of a BGR

---

## 1. Introduction to Bandgap

<p align="center">
  <img width="700" alt="Introduction to bandgap" src="https://github.com/user-attachments/assets/18a9d09f-21ad-4d40-b9ad-f8c8a8aa143b" />
</p>

A **Bandgap Voltage Reference (BGR)** is a circuit that provides a stable reference voltage that stays nearly constant across **PVT** variations:

- **P**: Process
- **V**: Voltage (supply)
- **T**: Temperature

It is called a *bandgap* reference because the output voltage, when extrapolated to 0 K, is about **1.2 V**, which is close to the bandgap energy of silicon.

---

## 2. Why BGR?

| Option | Limitation |
|--------|------------|
| **Battery** | Loses voltage over time as it is used, so it cannot serve as a fixed reference |
| **Power supply** | Output is noisy and has ripple |
| **Zener diode reference IC** | External, needs additional resistors and capacitors to change the voltage, and is not suitable for low-voltage applications |

✅ **A BGR solves these problems.** It can be integrated on-chip in **CMOS, BiCMOS, and Bipolar** technologies without any external components.

---

## 3. Applications of BGR

### 🔹 Low Dropout Regulators (LDO)
<p align="center">
  <img width="450" alt="LDO" src="https://github.com/user-attachments/assets/b7a2440c-beae-4c51-9d3a-c097ccb22d68" />
</p>

### 🔹 DC-DC Buck Converters
<p align="center">
  <img width="550" alt="DC-DC Buck Converter" src="https://github.com/user-attachments/assets/298cf9a6-54a0-4e61-be88-e8cff73a24b5" />
</p>

### 🔹 Analog to Digital Converters (ADC)
<p align="center">
  <img width="450" alt="ADC" src="https://github.com/user-attachments/assets/320aeb0f-1ce7-40aa-96fe-d78fb2a5dc5c" />
</p>

### 🔹 Digital to Analog Converters (DAC)
<p align="center">
  <img width="600" alt="DAC" src="https://github.com/user-attachments/assets/1fdf696b-479d-4bde-8677-a46c1a677bb4" />
</p>

---

## 4. Bandgap Voltage Reference Principle

<p align="center">
  <img width="700" alt="BGR principle" src="https://github.com/user-attachments/assets/65aec3aa-10c8-4006-844c-7a6702b7021c" />
</p>

A BGR is built from two blocks:

- **CTAT generator**: produces a voltage with a **negative** temperature coefficient (Complementary To Absolute Temperature)
- **PTAT generator**: produces a voltage with a **positive** temperature coefficient (Proportional To Absolute Temperature)

When the two are combined by a **summing circuit**, their temperature dependencies cancel, giving an output voltage that remains nearly constant over temperature.

---

## 5. BGR Types

<p align="center">
  <img width="700" alt="BGR types" src="https://github.com/user-attachments/assets/87c931cc-d5bc-4d7f-993c-5e1e6bcec805" />
</p>

### Self-Biased Current Mirror Based BGR: Advantages and Limitations

<p align="center">
  <img width="650" alt="Self-biased current mirror BGR advantages and limitations" src="https://github.com/user-attachments/assets/070c3358-e271-4b35-82e2-9534933543b4" />
</p>

---

## 6. Components of a BGR

<p align="center">
  <img width="600" alt="Components of BGR" src="https://github.com/user-attachments/assets/013ba6bf-3a5c-4e3a-80a5-39ce5dbcdc70" />
</p>

---

⬅️ [Back to Main README](../README.md) | ➡️ [Day 2](../Day2)
