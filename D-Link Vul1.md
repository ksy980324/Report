# Stack Buffer Overflow Vulnerability in D-Link DIR-845L Router
This is for reporting vulnerability 


## Firmware Download
You can download firmware at https://www.mydlink.co.kr/2013/beta_board/product_detail.php?no=146&model=DIR-845L


## Overview
**Vendor**: D-Link  
**Product**: DIR-845L Router  
**Vulnerability Type**: Stack Buffer Overflow  
**Affected Version**: Firmware version <= v1.01KRb03  
**Description**: Stack Buffer Overflow Vulnerability exists in **cgibin** binary in **DIR-845** router firmware **version <= v1.01KRb03**. In **hnap_main** function, HTTP request header field obtained via getenv("HTTP_SOAPACTION"). And SOAPACTION header field value is pass to sprintf. Due to the use of unsafe sprintf function, stack buffer overflow vulnerability occur.

![Untitled](https://github.com/ksy980324/Report/assets/89375654/9a64fcd9-d294-4a99-8104-c985bb5012bc)
![Untitled](https://github.com/ksy980324/Report/assets/89375654/a45bb3ec-772b-4a04-b0d0-8b8752e1653b)


## How to reproduce vulnerability
1. Emulate the firmware using emulation tools(QEMU, Firmadyne, FirmAE, ...).
![Untitled](https://github.com/ksy980324/Report/assets/89375654/a9c5ae25-7e3c-4901-afb0-8fca0d4fde95)

   
2. Run BOF_poc.py code using python2 then you can see error is occur due to stack buffer overflow.
3. ![Untitled](https://github.com/ksy980324/Report/assets/89375654/49fdd50e-57f1-4483-86ba-181f805f2d07)
