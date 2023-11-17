# Stack Buffer Overflow Vulnerability in D-Link DIR-845L Router
This is for reporting vulnerability 


## Firmware Download
You can download firmware at https://www.mydlink.co.kr/2013/beta_board/product_detail.php?no=146&model=DIR-845L


## Overview
###Vendor: D-Link
###Product: DIR-845L Router
###Vulnerability Type: Stack Buffer Overflow
###Affected Version: Firmware version <= v1.01KRb03
###Description: Stack Buffer Overflow Vulnerability exists in cgibin binary in DIR-845 router firmware version <= v1.01KRb03. In hnap_main function, HTTP request header field obtained via getenv("HTTP_SOAPACTION"). And SOAPACTION header field value is pass to sprintf. Due to the use of unsafe sprintf function, stack buffer overflow vulnerability occur.
