# SF

In Meshtastic, Channel Presets (Modem Presets) define how your radio modulates signals over the air. Spreading Factor (SF) is the core setting within those presets that controls the balance between range and transmission speed.

## What is Spreading Factor (SF)?

LoRa radios transmit data using chirps that spread the signal across a frequency band. Spreading Factor (SF7 through SF12) dictates how many chirps are used to encode each symbol of data ($2^{\text{SF}}$ chirps per symbol)

* **Higher SF (e.g., SF11, SF12):**
    *   **Pro:** Higher receiver sensitivity, better resistance to noise, and longer physical range.
    *   **Con:** Dramatically increases airtime (packet duration), consumes more battery, and reduces available network bandwidth.

*   **Lower SF (e.g., SF7, SF8):**
    *   **Pro:** Extremely fast transmission, minimal airtime, low battery usage, and higher total mesh network capacity.
    *   **Con:** Shorter range and requires a cleaner signal (higher SNR floor) to decode.

    *Rule of Thumb: Each step up in Spreading Factor (e.g., SF10 → SF11) doubles the airtime required to send the same packet, but adds about +2.5 dB of link budget.*

## The 3 Settings Built into Every Preset

When you select a Preset in Meshtastic, it configures three interconnected settings simultaneously:

1. **Spreading Factor (SF):** Determines signal penetration and range vs. speed.
2. **Bandwidth (BW):** The width of the frequency channel used (typically 125 kHz or 250 kHz). Doubling the bandwidth cuts airtime in half, but reduces receiver sensitivity by ~3 dB
3. **Coding Rate (CR):** Forward error correction redundancy (e.g., 4/5 vs 4/8). A higher CR adds recovery data to rebuild corrupted packets in noisy environments at the expense of slight extra airtime.

## Meshtastic Radio Presets Comparison

Meshtastic offers built-in presets. Below is a comparison of the most common profiles:

|**Radio Preset**|**Alt Preset Name**|**Data-Rate**|**SF / Symbols**|**Coding Rate**|**Bandwidth**|**Link Budget**|
|---|---|---|---|---|---|---|
|**Short Range / Fast**|Short Fast|10.94 kbps|7 / 128|4/5|250 kHz|143dB|
|**Short Range / Slow**|Short Slow|6.25 kbps|8 / 256|4/5|250 kHz|145.5dB|
|**Medium Range / Fast**|Medium Fast|3.52 kbps|9 / 512|4/5|250 kHz|148dB|
|**Medium Range / Slow**|Medium Slow|1.95 kbps|10 / 1024|4/5|250 kHz|150.5dB|
|**Long Range / Turbo**|Long Turbo|1.34 kbps|11 / 2048|4/8|500 kHz|150dB|
|**Long Range / Fast**|Long Fast|1.07 kbps|11 / 2048|4/5|250 kHz|153dB|
|**Long Range / Moderate**|Long Moderate|0.34 kbps|11 / 2048|4/8|125 kHz|156dB|
|**Long Range / Slow (depr.)**|Long Slow|0.18 kbps|12 / 4096|4/8|125 kHz|158.5dB|


## Key Best Practices

*   **Preset Matching:** Nodes must use the exact same modem preset to communicate with each other. A node on LongFast cannot hear a node on MediumFast.
* **Stick with LongFast:** Unless you are configuring a isolated local network (e.g., at a festival or high-density urban project), leave your node on LongFast to stay connected to the wider public mesh.
*   **Mind Channel Congestion:** Using high SF presets (LongSlow / SF12) in crowded areas causes airtime saturation, leading to dropped packets across the entire mesh.
