# Deliverable 1 — Table of Results

**Student:** 5714699 | **Design Number:** 27 | **Course:** EE4520 2025-2026

| # | Design Item | Unit | Spec | Achieved |
|---|-------------|------|------|----------|
| 1 | Design Number | [-] | 27 | N/A |
| 2 | SNR | [dB] | 80.64 | 80.85 |
| 3 | A_settle | [dB] | 63 | 63.32 |
| 4 | T_settle | [ns] | 2800 | 2800 |
| 5 | BW_cl from open-loop AC sims | [MHz] | --- | 0.329 |
| 6 | BW_cl from closed-loop AC sims | [MHz] | --- | 0.329 |
| 7 | Time-constant tau_cl from closed-loop AC sims | [ns] | --- | 483.1 |
| 8 | T_40dB (time to reach accuracy of 40 dB) | [ns] | --- | 1396.9 |
| 9 | T_48.69dB (time to reach accuracy of 48.69 dB) | [ns] | --- | 1894.3 |
| 10 | Time-constant tau_cl from transient sim | [ns] | --- | 497.4 |
| 11 | Power dissipation | [mW] | Lowest possible | 0.1119 |
| 12 | I(Vdd) | [mA] | Lowest possible | 0.0622 |
| 13 | Total integrated noise | [uV] | --- | 76.93 |
| 14 | Input step voltage | [mV] | 150 | 150 |
| 15 | Output step voltage | [V] | 1.2 | 1.2 |
| 16 | C_in | [pF] | --- | 18 |
| 17 | C_fb | [pF] | --- | 2.25 |
| 18 | C_load | [pF] | --- | 18 |
| 19 | C_CM | [pF] | --- | 2.25 |
| 20 | R_big | [GOhm] | Big | 100 |
| 21 | C_big | [nF] | Big | 1000 |
| 22 | Bonus points on FoM_dB | [-] | 0 | N/A |
| 23 | FoM_lin = 2pi * Power * T_8.6dB / SNR_lin^2 | [J] | ≤ 3.98e-18 | 3.02e-18 |
| 24 | FoM_dB = -10 log10(FoM_lin) | [dB] | ≥ 174.00 | 175.20 |

## Computation Notes

- **BW_cl (open-loop):** Frequency where |A*beta| = 1 → 329,348 Hz = 0.329 MHz
- **BW_cl (closed-loop):** -3 dB frequency of closed-loop gain → 329,397 Hz = 0.329 MHz
- **tau_cl (AC):** 1 / (2*pi*329,397) = 483.1 ns
- **tau_cl (transient):** T_48.69dB - T_40dB = 1894.3 - 1396.9 = 497.4 ns
- **SNR achieved:** 20*log10(0.8485 / 76.93e-6) = 80.85 dB
- **Power:** avg(I(Vdd)) * 1.8V = 62.17 uA * 1.8V = 0.1119 mW
- **FoM_lin:** 2*pi * 0.1119e-3 * 497.4e-9 / (10764.5)^2 = 3.02e-18 J
- **FoM_dB:** -10*log10(3.02e-18) = 175.20 dB

## Design Parameters

- ScaleA = 0.25, Mn34 = 200, Cin = 18 pF, Ibm = 350 uA
- W = 1 um, L = 0.18 um, Mp = 60, Mn = 11, mp_ratio = 5.45
- Rn = 5.8, Rp = 7.5, Aadd = 100