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
|**Material**|DEEPLEE PLA Plus 2.0 Filament Black 1KG x2 |£9.99/$13.17 x2  |[amazon](https://www.amazon.co.uk/DEEPLEE-Filament-Filaments-Upgraded-Printers/dp/B0F66JNZRD/ref=sr_1_1_sspa?crid=F52B48JVRZOQ&dib=eyJ2IjoiMSJ9.IZ2sT_eHqnoA-2GHiZFGXc6r8gbysEFlIiTkvDoqv-FNzVv2ejXwn1VtXnDnO1syMMHFf0n0XUfiAfY1BJcBi1HC4sUQUVGj3RD_-xbQzIg0R_s-2FScDgEb_IfH9ztALb6eEohivSDFUn8Zerh0g5L-glBf0XNwt1hAvHbpfsEPSAI7II90Io3OJIQy_0yKu6hqfiQKufeETSgto0nKNeiDp_1GdzVr9HNTnNdEfKZ4CX6Qh2xfpQ8jjOW2-oCeDknWFONpor509H7ElGNG3je43jdC2obuGcbSSF_O-pU.JnldRnHp-Ore1vg-EDJuVKyh6G1n4zy9UCGVFMkTUGg&dib_tag=se&keywords=pla%2Bplastic%2Bfor%2B3d%2Bprinter%2B2kg&qid=1774998869&sprefix=pla%2Bplastic%2Bfor%2B3d%2Bprinter%2B2%2Caps%2C319&sr=8-1-spons&aref=NERWNDhK8M&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)|
| **Fans/Frame** | 2x ARCTIC P12 Pro - Powerful Premium Fan, 120 mm PWM Fan, 600-3000 rpm,| £15.98/$21.06 |[amazon](https://www.amazon.co.uk/ARCTIC-P12-Pro-Powerful-600-3000/dp/B0DJDC74BP/ref=sr_1_7?crid=3HGUJHW0A29YB&dib=eyJ2IjoiMSJ9.OImOvGml4ZTCsUmbXCuLDJh_QaauOeGIr7FlzC--QrkKTLMkPdOHi19xCGgIbiHB66ZPnvxXW4HVXNDgk9sXQPQNekzjdLPYr_LXksXODNzj-imME34QP6fEsw-An1d2EQ-WIOKi-gBxU0ONq3iw6MBtEvDh0-MyymEStKk3qWBPZa5mMkeIBCoNWRX84VCZZ3z0HfW2jGLIRl9nSXpqZ7wOiFiwHOvyTEH0PIZ2UfM.bnlSbPCHYeed3BOLrlw11e_1k5DtOS2pNjIKc_25Iu8&dib_tag=se&keywords=2x%2BArctic%2BP12%2B%2B%2BTurbo%2BFan&qid=1774958061&sprefix=2x%2Barctic%2Bp12%2B%2B%2Bturbo%2Bfan%2Caps%2C375&sr=8-7&th=1)|
|**Connect**|300 Pcs M3 Hex Socket Head Cap|£5.99/$7.90|[amazon](https://www.amazon.co.uk/Washers-Assortment-Mechanical-Hexagon-Electronic/dp/B08YXL3P7D/ref=sr_1_10?crid=S1EW784R9EYT&dib=eyJ2IjoiMSJ9.kFwjngNeYg9ccjr9JVostZn2AJo0Mki_7u5B1ZDVrnGJ6fyIQjNN4Ueiz8KolZtcV-QIET5Ghzy9RZz8e2ow8kxHaCIbVevyQh_2kpxZ1R2VImYEudCLtdsmAGfQIWlo56F67h1gGfBxtbaNEjJunZlNUffPbsHL6ETRj4tO-1canJGW5bQXQdU7NEoMbz1uHGCF8OQ3aRs3VcDk3TYyrROloqviW44oMq4q4ZEcPW2ZPDW21Ns-cDdu_K0INBU1GziXfBGv8x7K6w2h1_63u8LBZMZpnTe_zOaMqjicewI.OjKCKE2Veq9X22bc7X9acLpNQOfbNorPhYfNhsu9QRc&dib_tag=se&keywords=M3%2BScrew%2B%26%2BNut%2BAssortment&qid=1774960710&sprefix=%2Caps%2C276&sr=8-10&th=1)
|**Fans/frame**| PC Fans high cfm 120mm fan 31mm/H2O air pressure 5500| £5.95/$7.84|[amazon](https://www.amazon.co.uk/DFG12038B12DN-static-pressure-31-10mm-H2O-connection/dp/B0BPPQXGNH/ref=sr_1_1?crid=1GI9L0O5VWL21&dib=eyJ2IjoiMSJ9.MOC8kfIg1ZC1egZpg_lubWZikbf6t6LclHpQz77-CPpSbZYxoK5rBwNQgw9yF95H2EMLBKvaBLqV3m4rhUhmETEWv6cj7AuGMx3Q-DhTglkoPFI-pzY-N9kWa54KQwlSd8II_AvTmASNWD_7NTRfZoJKRrO3QhPnAzByX2GInwo_RiFAVOzm9Nlho-Bf-00JdC2hb9Uuu5avhw3uPM80N4hmw4Y1uYa_6L6mjrsgTbM.zcPjrpt16YmdMlUBIl92w9rfcylgbi_0bx4jhLqzw18&dib_tag=se&keywords=Delta+Server+Fan&qid=1774959320&refinements=p_36%3A-1100&rnid=388997011&sprefix=%2Caps%2C343&sr=8-1)|
| **Structure** | Wire Mesh Roll Filter Screen Sheets Stainless Steel Woven Wire 20 Mesh Fine Metal Rodent Proof Ai | £5.99 / $7.90 |[amazon](https://www.amazon.co.uk/Filter-Screen-Sheets-Stainless-Rodent/dp/B0F3JHMMRX/ref=sr_1_8_sspa?crid=1N4MVP831KHH2&dib=eyJ2IjoiMSJ9.I55eHo7ROUpoMsweeHQmck5q5nJ5GTG44BJvZGMuJf3tcyOhNB4oXFXF4w14etPf9evFlzSvrvrkGY0jzoOEf2oEjh7BVP9plsNEUvOvbsvbmQYW4sMTSyDDfZFJcuX6Ivy0CU6zVY9Rk4zM_jgWHQ.eNn74ACDDZ_fP7_FdjMT5LCkBgeyMifi8NPDbqJ3fNs&dib_tag=se&keywords=BLOSTM+304+Stainless+Steel+Wire+Mesh+Roll+-+40+cm+15+cm&qid=1774999291&refinements=p_36%3A-1500&rnid=118657031&s=diy&sprefix=blostm+304+stainless+steel+wire+mesh+roll+-+40+cm+15+cm%2Cdiy%2C273&sr=1-8-spons&aref=PkL9Mj5hoX&sp_csd=d2lkZ2V0TmFtZT1zcF9tdGY&psc=1)
| **Thermal** | Aluminum Heat Shield Tape | £5.70 / ~$7..51 |[amazon](https://www.aliexpress.com/item/1005009506779702.html?dp=7362af5bbdf2cb56931232c8f2cd2110&isdl=y&aff_fsk=_ooD0gls&src=TwengaUK&aff_platform=aff_feeds&aff_short_key=_ooD0gls&pdp_npi=4%40dis!GBP!1.12!1.04!!!!!%40!12000049313194335!afff!!!&gad_source=1&gad_campaignid=23633928415&gbraid=0AAAAA-vcSCfVQEaUjJYqm18AMd5PbOw1L)
| **TOTAL** |  | **£296.29 / 390,56** ||
