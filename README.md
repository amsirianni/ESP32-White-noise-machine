# ESP32 White noise machine
Simple ESP32 driven white noise machine to help baby sleep when away from home.

**Intro to project**

We were heading away camping in the Australian summer with the baby and I wanted a simple, battery powered white noise machine to help the baby sleep. Because I was worried about temperature inside the tent, I decided to add a temp sensor into the project as well.

**Parts list**
- [ESP32 WROOM devboard](https://www.aliexpress.com/item/1005008427958890.html?spm=a2g0o.productlist.main.1.fd221b32Ig66b0&algo_pvid=a2ca480d-d001-477d-af44-edd0bf3fee12&algo_exp_id=a2ca480d-d001-477d-af44-edd0bf3fee12-0&pdp_ext_f=%7B%22order%22%3A%223%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21AUD%217.60%217.60%21%21%2133.94%2133.94%21%402101ef5e17384677574237827e808e%2112000045043969453%21sea%21AU%213925550392%21X&curPageLogUid=OUA6nqrHuLq2&utparam-url=scene%3Asearch%7Cquery_from%3A) 
- [Rotary encoder with a button](https://www.aliexpress.com/item/1005005983134515.html?spm=a2g0o.productlist.main.2.29da493cIxTNrw&algo_pvid=22d5c367-740b-40a6-a480-146590cd85ec&algo_exp_id=22d5c367-740b-40a6-a480-146590cd85ec-1&pdp_ext_f=%7B%22order%22%3A%222127%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21AUD%212.37%212.37%21%21%211.45%211.45%21%40210318c317384677941561605ef828%2112000035172713581%21sea%21AU%213925550392%21X&curPageLogUid=t6GK6qOg0d3x&utparam-url=scene%3Asearch%7Cquery_from%3A)
- [3x LEDs (green, red and blue)](https://www.aliexpress.com/item/1005006898362384.html?spm=a2g0o.productlist.main.31.5325SgVXSgVXZO&algo_pvid=e7ca4462-f919-4cbe-b85e-2308339913fa&algo_exp_id=e7ca4462-f919-4cbe-b85e-2308339913fa-30&pdp_ext_f=%7B%22order%22%3A%221037%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21AUD%213.22%211.80%21%21%2114.39%218.06%21%402103244817384679902276227e2332%2112000038654877159%21sea%21AU%213925550392%21X&curPageLogUid=AN6GOkI8X09c&utparam-url=scene%3Asearch%7Cquery_from%3A)
- [bmp280 temp sensor](https://www.aliexpress.com/item/1005006330566170.html?spm=a2g0o.productlist.main.6.1ac864091DuBCP&algo_pvid=1fa82dbf-fbd0-45f3-82b9-c4c7da380617&algo_exp_id=1fa82dbf-fbd0-45f3-82b9-c4c7da380617-5&pdp_ext_f=%7B%22order%22%3A%221217%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21AUD%212.53%211.62%21%21%2111.31%217.24%21%402103146c17384680248138590eb590%2112000036785983125%21sea%21AU%213925550392%21X&curPageLogUid=1iHpXsZcSdjF&utparam-url=scene%3Asearch%7Cquery_from%3A)
- [Resistors (for the LEDs)](https://www.aliexpress.com/item/1005004933865451.html?spm=a2g0o.productlist.main.10.341d68e45Dle1H&algo_pvid=50a16363-f3cc-4b25-a1a5-33a8f7a1e0ed&algo_exp_id=50a16363-f3cc-4b25-a1a5-33a8f7a1e0ed-9&pdp_ext_f=%7B%22order%22%3A%224419%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21AUD%213.99%213.99%21%21%212.44%212.44%21%40210312d517384680766247696efd60%2112000031069410692%21sea%21AU%213925550392%21X&curPageLogUid=GKIU0yKuGIT3&utparam-url=scene%3Asearch%7Cquery_from%3A)
- [DFRobot MP3 player](https://www.aliexpress.com/item/4000379417594.html?spm=a2g0o.productlist.main.3.1a0f3fb9oawSXI&algo_pvid=3873160c-0bda-4b11-846d-5c59c0efacaf&algo_exp_id=3873160c-0bda-4b11-846d-5c59c0efacaf-2&pdp_ext_f=%7B%22order%22%3A%2213%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21AUD%212.56%212.56%21%21%211.57%211.57%21%40210312d517384682090628289efd64%2110000001548721847%21sea%21AU%213925550392%21X&curPageLogUid=wfhLtlDhNwVi&utparam-url=scene%3Asearch%7Cquery_from%3A)
- [Micro SD memory card (maximum 32gb and formatted in FAT16 or 32)](https://www.aliexpress.com/item/1005001617961938.html?spm=a2g0o.productlist.main.1.1af9744cZ7T6vv&algo_pvid=1b90b6cc-4428-49d9-a4ac-726111b5ba07&algo_exp_id=1b90b6cc-4428-49d9-a4ac-726111b5ba07-0&pdp_ext_f=%7B%22order%22%3A%2246800%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21AUD%212.94%212.74%21%21%211.80%211.68%21%40210318ec17384682877414872ed773%2112000016836623832%21sea%21AU%213925550392%21X&curPageLogUid=wPowyr4PxF42&utparam-url=scene%3Asearch%7Cquery_from%3A)
- [Speaker (8ohm and maximum of 3watts)](https://www.aliexpress.com/item/1005005699690954.html?spm=a2g0o.productlist.main.1.611942a6m3XDck&algo_pvid=8d361de6-b0a2-4687-a52c-8d4076e49356&algo_exp_id=8d361de6-b0a2-4687-a52c-8d4076e49356-0&pdp_ext_f=%7B%22order%22%3A%22829%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21AUD%213.62%213.50%21%21%2116.17%2115.63%21%402103247917384687330893533ef6b9%2112000037280087063%21sea%21AU%213925550392%21X&curPageLogUid=NHYBxAZHBK3N&utparam-url=scene%3Asearch%7Cquery_from%3A)


**Wiring**

![image](https://github.com/user-attachments/assets/7249f00d-806b-46a9-8d6b-6dacac8ceda4)

![image](https://github.com/user-attachments/assets/981d5c43-0610-4b48-9458-8f3de60cc81c)

![image](https://github.com/user-attachments/assets/058f237d-6e55-455b-a09b-b5d968c4d5c9)


**MP3 player SD card preparation**

Prepare the memory card by (I followed this excellent tutorial on how to set up [here](https://www.youtube.com/watch?v=PBdqgHj_AkU&ab_channel=TheLastOutpostWorkshop))
- Format your card to FAT16 or FAT32. I recommend using this software (note formatting with other tools gave me issues): https://www.sdcard.org/downloads/formatter/
- Download and save your chosen white noise track to the memory card as an mp3 file. I chose 8hrs of ocean noise similar to [this](https://www.google.com/search?q=youtube+ocean+sound&sca_esv=a13f7662f8372041&rlz=1C1ONGR_enAU1124AU1124&sxsrf=AHTn8zqV5kF7iA25TfvPhFm3s_ADhq2Zkw%3A1738469728900&ei=YPGeZ_HSNo7l2roPhpGL0Ao&ved=0ahUKEwjxgpO1kKSLAxWOslYBHYbIAqoQ4dUDCBA&uact=5&oq=youtube+ocean+sound&gs_lp=Egxnd3Mtd2l6LXNlcnAiE3lvdXR1YmUgb2NlYW4gc291bmQyBBAjGCcyChAjGIAEGCcYigUyChAAGIAEGBQYhwIyBRAAGIAEMgUQABiABDIFEAAYgAQyBRAAGIAEMgUQABiABDIFEAAYgAQyBRAAGIAESKQCUABY7gFwAHgBkAEAmAHGAaABxgGqAQMwLjG4AQPIAQD4AQGYAgGgAtYBmAMAkgcDMi0xoAeNCA&sclient=gws-wiz-serp#fpstate=ive&vld=cid:0fe4658b,vid:vPhg6sc1Mk4,st:0)
- Make sure file is saved as MP3.
- I renamed the file to 001, but I don't think it matters for this project as there will only be one file on the card to play.
- Insert SD card into DFRobot MP3 player and you should be good to go.

**Code**

The code has been uploaded, but here is a summary of what it is doing:
- Rotary Encoder rotation is used to control the volume and the built in button is used to play and pause the white noise.
- The BMP280 is monitoring temperature and that is used to drive the LEDs, which are used as quick indicators to see if the temperature is above/below or in the desired range.

**3D printed housing**

I made a simple 3D printed housing which isn't perfect, but helped me keep all the pieces together while on the move. 

I've included the STL and Fusion360 file if you'd like to use it/modify it.

**Notes**
- Because the BMP280 sensor is packaged in closely with the other electronics, I found the temperature readings were 2-4 degrees (celcius) warmer than the actual room temperature. I got around this by simply increasing my desired temperature range by 3 degrees. You can customise the temp range in the code.
- Make sure you're using the correct speaker (8ohm, maximum of 3watts) otherwise you will get no sound or poor quality sound.
- I powered mine via the ES32 USB with a mobile battery bank, but you can use any 5v power supply.
