# SNR

Signal-to-Noise Ratio (SNR) measures signal clarity. While RSSI (Received Signal Strength Indicator) measures raw signal strength or "loudness" in dBm, SNR measures how far that signal stands out above background radio static (the noise floor) in decibels (dB).

---

## The Analogy: Loudness vs. Clarity

To understand how SNR works in Meshtastic, imagine hearing someone speak in a room:
* **RSSI (Loudness):** How loud the speaker's voice is hitting your ears.
* **Noise Floor (Static):** The background noise in the room (AC hum, traffic, ambient chatter).
* **SNR (Clarity):** How easily you can distinguish their voice from the background noise

## Why Negative SNR is Normal in Meshtastic

In traditional wireless systems (like Wi-Fi, cellular, or Bluetooth), a signal weaker than the background static (a negative SNR) results in total data loss.

Meshtastic relies on LoRa (Chirp Spread Spectrum) modulation, which allows the radio chip to mathematically extract data below the noise floor. Seeing negative values like -5 dB or -12 dB is completely standard for long-distance Meshtastic links.

## SNR Scale Reference Guide


|**SNR Range**|**Link Quality**|**Real-World Context**|
|---|---|---|
|**+5 dB to +12 dB**| Excellent|Clean line-of-sight signal with minimal ambient static.|
|**0 dB to +5 dB**|Good|Reliable connection with low background noise.|
|**-1 dB to -10 dB**|Fair / Moderate|Standard performance for everyday mid-to-long range nodes.|
|**-10 dB to -15 dB**|Marginal|Near the reception threshold for default presets (e.g., LongFast).|
|**Below -15 dB**|Poor / Critical|Reaching the absolute limit of demodulation; expect dropped packets.|

*Note: The exact limit depends on your channel preset (such as LongFast, LongSlow, or ShortFast). Presets using higher Spreading Factors can decode signals deeper into negative SNR levels.*

## Diagnosing Network Issues with RSSI & SNR

Evaluating both metrics simultaneously helps identify hardware or location issues:

*   **High RSSI (e.g., -85 dBm) + Low/Negative SNR (e.g., -12 dB):**
    *   **Issue:** Local radio interference.
    *   **Solution:** Move the node away from noisy electronics like cheap switching power supplies, computers, or nearby radio transmitters.

*   **Low RSSI** (e.g., -118 dBm) + High SNR (e.g., +3 dB):
    *   **Context:** Extremely quiet RF environment (like a rural area).
    *   **Meaning:** The signal is faint, but because there is virtually no background noise, the message decodes perfectly.
*   **Low RSSI (e.g., -120 dBm) + Low SNR (e.g., -15 dB):**
    *   **Context:** Max range limit or severe physical obstruction (terrain/buildings).
