# Redirection vers le bon discovery email suivant le client



## Ressources

### autodiscover.beta.gouv.fr/autodiscover/autodiscover.xml
```
POST /autodiscover/autodiscover.xml HTTP/1.1
Host: autodiscover.beta.gouv.fr
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Thunderbird/102.8.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: text/xml; charset=utf-8
Content-Length: 396
Connection: keep-alive

<?xml version="1.0" encoding="utf-8"?>
    <Autodiscover xmlns="http://schemas.microsoft.com/exchange/autodiscover/outlook/requestschema/2006">
      <Request>
        <EMailAddress>john.doe@beta.gouv.fr</EMailAddress>
        <AcceptableResponseSchema>http://schemas.microsoft.com/exchange/autodiscover/outlook/responseschema/2006a</AcceptableResponseSchema>
      </Request>
    </Autodiscover>HTTP/1.1 500 Internal Server Error
server: nginx
date: Wed, 22 Feb 2023 17:06:19 GMT
content-type: text/xml
transfer-encoding: chunked
x-iplb-request-id: B918B884:18FC_D5BA2105:0050_63F64B8B_8EBCC54E:25AAC
x-iplb-instance: 16982
set-cookie: SERVERID77446=200174|Y/ZLj|Y/ZLj; path=/; HttpOnly
```

### autoconfig.beta.gouv.fr/mail/config-v1.1.xml 

```
GET /mail/config-v1.1.xml?emailaddress=john.doe%40beta.gouv.fr HTTP/1.1
Host: autoconfig.beta.gouv.fr
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Thunderbird/102.8.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: keep-alive

HTTP/1.1 200 OK
server: nginx
date: Wed, 22 Feb 2023 17:06:19 GMT
content-type: text/xml
transfer-encoding: chunked
x-iplb-request-id: B918B884:6FEF_D5BA2105:0050_63F64B8B_33E1B3C0:F483
x-iplb-instance: 16980
set-cookie: SERVERID77446=200172|Y/ZLj|Y/ZLj; path=/; HttpOnly
cache-control: private

3BD
<?xml version="1.0"?>
<clientConfig version="1.1">
    <emailProvider id="beta.gouv.fr">

      <domain>beta.gouv.fr</domain>

      <displayName>john.doe@beta.gouv.fr</displayName>
      <displayShortName>john.doe@beta.gouv.fr</displayShortName>

      <incomingServer type="imap">
         <hostname>ssl0.ovh.net</hostname>
         <port>993</port>
         <socketType>SSL</socketType>
         <username>john.doe@beta.gouv.fr</username>
         <authentication>password-cleartext</authentication>
      </incomingServer>

      <outgoingServer type="smtp">
         <hostname>ssl0.ovh.net</hostname>
         <port>465</port>
         <socketType>SSL</socketType>
         <username>john.doe@beta.gouv.fr</username>
         <authentication>password-cleartext</authentication>
         <addThisServer>true</addThisServer>
         <useGlobalPreferredServer>true</useGlobalPreferredServer>
      </outgoingServer>

    </emailProvider>
</clientConfig>
```
