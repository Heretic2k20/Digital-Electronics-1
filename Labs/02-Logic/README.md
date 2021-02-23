# Lab 02 - Logic

![Logo](logolink_eng.jpg)

## Část 1 - Příprava:
**Tabulka připravená před cvičením:**

| **n** | **B[1:0]** | **A[1:0]** | **B > A** | **B = A** | **B < A** |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0 0 | 0 0 | 0 | 1 | 0 |
| 1 | 0 0 | 0 1 | 0 | 0 | 1 |
| 2 | 0 0 | 1 0 | 0 | 0 | 1 |
| 3 | 0 0 | 1 1 | 0 | 0 | 1 |
| 4 | 0 1 | 0 0 | 1 | 0 | 0 |
| 5 | 0 1 | 0 1 | 0 | 1 | 0 |
| 6 | 0 1 | 1 0 | 0 | 0 | 1 |
| 7 | 0 1 | 1 1 | 0 | 0 | 1 |
| 8 | 1 0 | 0 0 | 1 | 0 | 0 |
| 9 | 1 0 | 0 1 | 1 | 0 | 0 |
| 10 | 1 0 | 1 0 | 0 | 1 | 0 |
| 11 | 1 0 | 1 1 | 0 | 0 | 1 |
| 12 | 1 1 | 0 0 | 1 | 0 | 0 |
| 13 | 1 1 | 0 1 | 1 | 0 | 0 |
| 14 | 1 1 | 1 0 | 1 | 0 | 0 |
| 15 | 1 1 | 1 1 | 0 | 1 | 0 |

**Funkce pro B = A:**

*f(b=a) = [not(b1).not(b0).not(a1).not(a0)] + [not(b1).b0.not(a1).a0] + [b1.not(b0).a1.not(a0)] + [b1.b0.a1.a0]*

**Funkce pro B < A:**

*f(b<a) = [b1 + b0 + a1 + a0] . [b1 + not(b0) + a1 + a0] . [b1 + not(b0) + a1 + not(a0)] . [not(b1) + b0 + a1 + a0] . [not(b1) + b0 + a1 + not(a0)] . [not(b1) + b0 + not(a1) + a0] . [not(b1) + (notb0) + a1 + a0] . [not(b1) + not(b0) + a1 + not(a0)] . [not(b1) + not(b0) + not(a1) + a0] . [not(b1) + not(b0) + not(a1) + not(a0)]*


## Část 2 - Karnaughovy-Mapy a zjednodušené logické funkce:
![K-Maps](K-maps.JPG)
