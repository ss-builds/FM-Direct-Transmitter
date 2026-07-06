# FM Transmitter



##### Problem:

**A cheap Amazon BT FM transmitter for custom audio gives poor quality and volume loss. I'd like better integrated audio without the plug-in transmitter.**



&#x09;I could replace the factory head unit with an aftermarket unit. However, this isn't ideal: the good ones are expensive, look cheap, and I want to maintain the OEM look by keeping the original head unit. My first thought was to replace the antenna (corroded from East Coast weather), but I can't find a replacement short of a junkyard pull, which may be in the same condition or worse.

&#x09;I did find a solution online that replaces the factory antenna with a direct connection to a BT module, but there's little info on the quality of these modules and they're expensive ($100+). ***Custom has to be the way, right?***

&#x09;*(I could do a custom antenna to improve the current setup, but I want better quality than a plug-in transmitter can offer)*



##### Criteria:

* BT capable
* Upgraded audio quality (relative to current solution)
* Ease of use
* Able to switch from FM mode to BT mode with a press of a button or with connection status (will add support for both)



##### Constraints:

* Cheap as possible
* OEM+ (no replacing head-unit, no major modifications, passive)
* Interference from other signals
* Ambient temperature exceeding component operating range (automotive)

**Update 06/29/26:** Given that my Corolla's current head unit has the option for a CD player (which transmits lossless audio), I was considering to use that port to inject my BT signal into. However, this would mean taking out the head unit, probing a (very likely) proprietary communication protocol between the OEM CD player and the head unit. This will be something to consider for the future, but for now, I'll stick to something that injects directly into FM port.

**Update 07/05/2026:** Use two boards with mezzanine connectors for better EMI support & to prevent space problems while capturing the schematic.

**Update 07/06/26:** ADIsimPLL; due to constraints from capacitor sizing and to balance enough charge pump current to prevent external EMI from interfering with my VCO (MAX2606), max tunable frequency without issues is 103.9MHz, compared to the original value of 108MHz. Using 560uF hybrid polymer capacitor for C2, with 220nF C0G filter caps. To even get to a value as low as 560uF, I had to reduce the effective Kvco by using a voltage divider from ~11MHz/V to ~4.46MHz/V (reduction factor of 0.435). Otherwise, I'd be looking at values for C2 that are >1.5mF (way too high for realistic applications).

**Update 07/04/26:** Adding some basic schematic pictures to document progression. NOTE: VERY work in progress.

RF Generation _(As of 07/06/26)_:
<img width="1598" height="1229" alt="image" src="https://github.com/user-attachments/assets/3d1e2612-c225-4e1a-a80f-ca26a0bed9a5" />

Power: 
<img width="1671" height="1160" alt="image" src="https://github.com/user-attachments/assets/c4733e2a-425e-4c3c-8da7-fcf717a077a7" />

Oscillator capacitor shunt selection: 
<img width="2864" height="1363" alt="image" src="https://github.com/user-attachments/assets/a86b12da-44dd-4312-8fed-164d49dedd01" />



