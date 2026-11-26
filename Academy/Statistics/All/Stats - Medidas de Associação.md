---
banner: "![[Pasted image 20260421192206.png]]"
banner-x: 50
banner-y: 40
---
---


| min(r-1, c-1) | Negligible |     Weak     |   Moderate   | Strong |
| :-----------: | :--------: | :----------: | :----------: | :----: |
|       1       |   < 0.10   | [0.10, 0.30) | [0.30, 0.50) | 0.50+  |
|       2       |   < 0.07   | [0.07, 0.21) | [0.21, 0.35) | 0.35+  |
|       3       |   < 0.06   | [0.06, 0.17) | [0.17, 0.29) | 0.29+  |
|       4       |   < 0.05   | [0.05, 0.15) | [0.15, 0.25) | 0.25+  |
|       5       |   < 0.05   | [0.05, 0.13) | [0.13, 0.22) | 0.22+  |
<small>Source: Cohen, J. (1988). Statistical power analysis for the behavioral sciences (2nd ed).</small>






from scipy.stats.contingency import association

v_cramer = association(df_filtrado.to_numpy(), method="cramer")

print(f"V de Cramér: {v_cramer:.4f}")