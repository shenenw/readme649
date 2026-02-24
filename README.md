# 🎰 Western Canada 6/49 Robot
An automated system for retrieving WCLC results, performing deterministic analysis, and generating predictions for the Prairie Provinces.

---

## 📅 Project Roadmap

- [x] **Stage 1: Automated Retrieval** - Automated via GitHub Actions (Runs Wed/Sat at 10:30 PM MT).
  - Fetches from WCLC sources.
- [ ] **Stage 2: Deterministic Analysis** - Calculating Parity (Even/Odd) and Sum-Range from the last 10 draws.
  - Generating 7 filtered "High-Probability" combinations.
- [ ] **Stage 3: Stochastic Modeling** - Future implementation of probabilistic random-walk and frequency modeling.

---

## 📊 Western 6/49 Live Dashboard
> **Robot Status:** Last Checked: 2026-02-22 10:30 PM MT

<table width="100%">
  <tr>
    <th width="50%">Latest WCLC Result: Saturday, Feb 21, 2026</th>
    <th width="50%">Deterministic Stats (Last 10 Draws)</th>
  </tr>
  <tr>
    <td align="center">
      <font size="5"><b>01 - 06 - 07 - 18 - 29 - 48</b></font><br>
      <i>Bonus: 11 | Extra: 1467414</i>
    </td>
    <td align="center">
      <b>Avg Sum:</b> 142 <br>
      <b>Parity (E/O):</b> 2:4 <br>
      <b>Most Frequent:</b> 29
    </td>
  </tr>
</table>

---

## 🔮 Weekly Predictions (Stage 2)
*Calculated using deterministic filters: Sum Range (110-185) + Balanced Parity.*

<div align="center">
  <code>05 - 12 - 21 - 33 - 40 - 46</code><br>
  <code>03 - 17 - 22 - 30 - 38 - 45</code><br>
  <code>10 - 14 - 25 - 31 - 42 - 47</code><br>
  <code>06 - 19 - 24 - 28 - 35 - 41</code><br>
  <code>08 - 11 - 23 - 34 - 39 - 49</code><br>
  <code>02 - 15 - 27 - 32 - 43 - 44</code><br>
  <code>04 - 20 - 26 - 29 - 37 - 48</code>
</div>

---

## 🛠️ Technical Setup

### 1. Automation (The Robot)
The retrieval script is triggered by a **Cron Job** within GitHub Actions. Since Western 6/49 draws close at 8:30 PM MT and results are usually processed by 10:00 PM MT, the robot runs at:
* **Schedule:** `30 04 * * 4,7` (04:30 UTC is 10:30 PM MT Wednesday and Saturday).

### 2. Analysis Parameters (Deterministic)
* **Sum Filter:** Rejects combinations where the sum is outside the historical bell curve.
* **Parity (Even/Odd):** Ensures a balanced ratio (e.g., 3:3, 4:2) to avoid low-probability all-even or all-odd sets.
* **Last Digit Patterns:** Ensuring no more than two numbers in a set share the same last digit (e.g., 4, 14, 24).
* **Frequency Tracker:** Monitors "Hot" and "Cold" numbers within the Western Canada pool.

### 3. Future Implementation (Stochastic)
* **Probabilistic Modeling:** Implementation of random-walk and weighted frequency modeling.
* **Fast Fourier Transform (FFT):** Using signal processing to analyze historical draw cycles in the frequency domain.
* **Continuous Improvement:** More analysis methods will be added as I learn more.

---

## ⚖️ Disclaimer
This software is for **data science and educational purposes only**. Lottery outcomes are random events. Use this tool to study patterns, not as financial advice.
