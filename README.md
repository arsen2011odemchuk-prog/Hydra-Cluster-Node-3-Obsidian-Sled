# ⚡ Hydra Node 3: Obsidian Sled (GPU Expansion)

Node 3 is a "Stateless Compute" unit designed to scale the VRAM capacity of the Hydra Cluster without the overhead of a full PC build. It is physically controlled by the **Sentinel Phase 2** interface.

## 🧠 System Concept
Traditional clusters waste budget on multiple CPUs and RAM sticks. Node 3 focuses 75% of its budget on the **GPU (RTX 3060 12GB)**. It connects directly to the Master Node's PCIe bus via an M.2 bridge, appearing as a native second GPU for AI models.

## 🛠️ Hardware Specifications
- **GPU:** NVIDIA RTX 3060 (12GB GDDR6 version for LLM context depth).
- **Interface:** ADT-Link R43SG (M.2 NVMe to PCIe x16 Gen3 Bridge).
- **Power Unit:** 1200W Platinum Server PSU + 12-Port Breakout Board.
- **Cooling:** Open-frame chassis with dual 120mm high-static pressure fans.

## 🔌 Connection & Logic
- **Data:** M.2 Slot (Master Node) <---> R43SG Bridge <---> RTX 3060 (Node 3).
- **Power Control:** RPi Pico (Sentinel) <---> 5V Relay <---> Server PSU (Node 3).
- **Authorization:** Node 3 only powers up when Dual-RFID keys are validated at the Sentinel Terminal.

## 💰 Budget Breakdown ($400 Target)

| Component | Model | Est. Price £/$ |Link|
| :--- | :--- | :--- |:---|
| **GPU** |ASUS NVIDIA GeForce RTX 3060 TUF Gaming OC 12GB | £208.70/$275,10 |[ebay](https://www.ebay.co.uk/itm/137180841263?_skw=3060+12+gb+TUF&itmmeta=01KN0EGY7N66PHMG95DNC010YX&hash=item1ff09d852f%3Ag%3AgRQAAeSwERVpypWb&itmprp=enc%3AAQALAAAA0GfYFPkwiKCW4ZNSs2u11xB6IISiCrmYDIsu6tOCWt58%2FAKfNATxP4pREMmpzvTf57umhQ9pZyUX7JxMHzc0DAsL6p2na20VgOiPoXdeaZStsyuoms00EbQk7EKqI0%2F9c3%2Fk6gAXG%2FG495%2BPYj3eRfUPPoKdLIP2tYvNcBMcqKSJUTmKbNCUwop4z%2FrxZ5cAFXc%2FC%2FnNiqR7NAf65nmAgyqSWB04xOyfpkQAB94iYgvZtfSFfHa5K)|
| **Bridge** | ADT-Link R43SG M.2 Adapter | £29/$38,23 |[amazon](https://www.amazon.co.uk/ADT-Link-Extension-Graphics-Adapter-PCI-Express/dp/B07YDH8KW9/ref=sr_1_3?crid=IP2M1D83PV6K&dib=eyJ2IjoiMSJ9.89hazMOv-EwiXi3WT9_fQSIhJ8yCGiuaAfyAYm1IO0KaedGCE0FmTV3ZMuobxmJQ7MAF5YI1hCwvUglGL1dDB0Rv9j3AKuRekO-k5ROi_9OYL17MpxlwFvB3eC6WiNRU.8Ui7_1g9qoNt2Zo7uPmE6DatMMnl0sBGAsjH0iIgb80&dib_tag=se&keywords=ADT-Link%2BR43SG%2BM.2%2BAdapter&qid=1774911096&sprefix=%2Caps%2C301&sr=8-3&th=1)|
|**Control**| Yizhet Relay 5V 4 Channel, DC 5V 230V| £5.99/$7.99|[amazon](https://www.amazon.co.uk/Yizhet-Channel-Relay-Control-Optocoupler-Raspberry/dp/B07GXBSX58/ref=sr_1_1?crid=FBS4TWF5DUOG&dib=eyJ2IjoiMSJ9.D96yvnBdY1rKWi33q8_fFp4TXajr3M28cA6aD_gqIjPaEcB8fXIThVak4uKLP7uTukyKod9QwsfQIkB2_EA1rtttlySnO_pR-aFKhfWXy2mQaH6V1XvHlSih53nPzknKq2Q2b3U_3T7ytqlS0Lc1tTXePJY--OlmvHGFpmLTi1UpDLxiswCWhnNVIuZe6GTzHmBv5jCNIxs1wQKbOI2AWRA572jUUKxWes6_Hgpxhp9Q1ILcwacZMnvw7gf2e3X8.cA-TrEF5P0afijbglglWPlCJ5oYx2pxH8el6kwkhgHA&dib_tag=se&keywords=dual%2Brelay%2Bmodule%2Bpre%2Bsolder&qid=1774959837&refinements=p_36%3A-600&rnid=301350031&sprefix=dual%2Brelay%2Bmodule%2Bpre%2Bsoilde%2Caps%2C290&sr=8-1&th=1)|
|**Wiring**|Chanzon 40pcs 30cm long Female to Female Header Jumper Wire Dupont Cable Line Connecto|£6.99/$9.21|[amazon](https://www.amazon.co.uk/Solderless-Multicolored-Electronic-Breadboard-Protoboard-3-Female-40pcs/dp/B09GJQGVBB/ref=sr_1_22?crid=Z4P20OFP4P5P&dib=eyJ2IjoiMSJ9.D28-upm8JsUG4FRtCi4hcJx7xHrujiaATKEqYdzrAK84nwACrDuip9s7m-iiKnriutMP5ytTq8W6y8frO13Tw32owFUlQ1BSQjIngWStSzD_2uYeOPgUAXrG3h2sxbzKoDxZqwfQ6XaV7vjV1pyQVkHHLUSkFCOVjxrjwbsYlQpnCfSqYkatyMlXe09YyAUKK-wc9O9HQQSZ72G3x0E1El_aGekeH-QuQXXYYwOltqT7aJ24TFA0XypJx9a71arTJTkx7eNV7tSQsLU2tiiOzn-VAKg9uzzSvAPtq8N8dMQ.bd9L9sX68edU7Hgarzg_8rPZ8r7ULD0apjEke4Cd2kU&dib_tag=se&keywords=dupont%2Bjumper%2Bwires%2Bfemale%2Bto%2Bfemale%2B40%2Bpc%2B30%2Bcm&qid=1774971494&sprefix=dupont%2Bjumper%2Bwires%2Bfemale%2Bto%2Bfemale%2B40%2Bpc%2B30%2B%2Caps%2C289&sr=8-22&th=1)|
| **Fans/Frame** | 2x ARCTIC P12 Pro - Powerful Premium Fan, 120 mm PWM Fan, 600-3000 rpm,| £15.98/$21.06 |[amazon](https://www.amazon.co.uk/ARCTIC-P12-Pro-Powerful-600-3000/dp/B0DJDC74BP/ref=sr_1_7?crid=3HGUJHW0A29YB&dib=eyJ2IjoiMSJ9.OImOvGml4ZTCsUmbXCuLDJh_QaauOeGIr7FlzC--QrkKTLMkPdOHi19xCGgIbiHB66ZPnvxXW4HVXNDgk9sXQPQNekzjdLPYr_LXksXODNzj-imME34QP6fEsw-An1d2EQ-WIOKi-gBxU0ONq3iw6MBtEvDh0-MyymEStKk3qWBPZa5mMkeIBCoNWRX84VCZZ3z0HfW2jGLIRl9nSXpqZ7wOiFiwHOvyTEH0PIZ2UfM.bnlSbPCHYeed3BOLrlw11e_1k5DtOS2pNjIKc_25Iu8&dib_tag=se&keywords=2x%2BArctic%2BP12%2B%2B%2BTurbo%2BFan&qid=1774958061&sprefix=2x%2Barctic%2Bp12%2B%2B%2Bturbo%2Bfan%2Caps%2C375&sr=8-7&th=1)|
|**Connect**|300 Pcs M3 Hex Socket Head Cap|£5.99/$7.90|[amazon](https://www.amazon.co.uk/Washers-Assortment-Mechanical-Hexagon-Electronic/dp/B08YXL3P7D/ref=sr_1_10?crid=S1EW784R9EYT&dib=eyJ2IjoiMSJ9.kFwjngNeYg9ccjr9JVostZn2AJo0Mki_7u5B1ZDVrnGJ6fyIQjNN4Ueiz8KolZtcV-QIET5Ghzy9RZz8e2ow8kxHaCIbVevyQh_2kpxZ1R2VImYEudCLtdsmAGfQIWlo56F67h1gGfBxtbaNEjJunZlNUffPbsHL6ETRj4tO-1canJGW5bQXQdU7NEoMbz1uHGCF8OQ3aRs3VcDk3TYyrROloqviW44oMq4q4ZEcPW2ZPDW21Ns-cDdu_K0INBU1GziXfBGv8x7K6w2h1_63u8LBZMZpnTe_zOaMqjicewI.OjKCKE2Veq9X22bc7X9acLpNQOfbNorPhYfNhsu9QRc&dib_tag=se&keywords=M3%2BScrew%2B%26%2BNut%2BAssortment&qid=1774960710&sprefix=%2Caps%2C276&sr=8-10&th=1)
|**Fans/frame**| PC Fans high cfm 120mm fan 31mm/H2O air pressure 5500| £5.95/$7.84|[amazon](https://www.amazon.co.uk/DFG12038B12DN-static-pressure-31-10mm-H2O-connection/dp/B0BPPQXGNH/ref=sr_1_1?crid=1GI9L0O5VWL21&dib=eyJ2IjoiMSJ9.MOC8kfIg1ZC1egZpg_lubWZikbf6t6LclHpQz77-CPpSbZYxoK5rBwNQgw9yF95H2EMLBKvaBLqV3m4rhUhmETEWv6cj7AuGMx3Q-DhTglkoPFI-pzY-N9kWa54KQwlSd8II_AvTmASNWD_7NTRfZoJKRrO3QhPnAzByX2GInwo_RiFAVOzm9Nlho-Bf-00JdC2hb9Uuu5avhw3uPM80N4hmw4Y1uYa_6L6mjrsgTbM.zcPjrpt16YmdMlUBIl92w9rfcylgbi_0bx4jhLqzw18&dib_tag=se&keywords=Delta+Server+Fan&qid=1774959320&refinements=p_36%3A-1100&rnid=388997011&sprefix=%2Caps%2C343&sr=8-1)|
| **TOTAL** | | **£289.09/$381,07** |
