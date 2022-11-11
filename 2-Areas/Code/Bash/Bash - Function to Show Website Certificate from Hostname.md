---
Date: 2022-11-11
Author: Jimmy Briggs <jimmy.briggs@jimbrig.com>
Tags: ["#Type/Code", "#Topic/Dev"]
Alias: ["Bash - Function to Show Website Certificate from Hostname"]
---

# Bash - Function to Show Website Certificate from Hostname

*Source: https://github.com/rothgar/mastering-zsh/blob/master/docs/helpers/functions.md#show-website-certificate-from-hostname*

## Snippet

```bash
function curl-cert() {
  openssl s_client -showcerts -connect "${1}":443 -servername ${1}
}
```

## Usage

```bash
curl-cert jimbrig.com
```

<details><summary>Show Output</summary><p>

```bash
> curl-cert jimbrig.com
CONNECTED(00000003)
depth=2 C = US, O = Google Trust Services LLC, CN = GTS Root R1
verify return:1
depth=1 C = US, O = Google Trust Services LLC, CN = GTS CA 1D4
verify return:1
depth=0 CN = jimbrig.com
verify return:1
---
Certificate chain
 0 s:CN = jimbrig.com
   i:C = US, O = Google Trust Services LLC, CN = GTS CA 1D4
-----BEGIN CERTIFICATE-----
MIIFXDCCBESgAwIBAgIQBSv/ay7nd4wJsKj9Y3/yvzANBgkqhkiG9w0BAQsFADBG
MQswCQYDVQQGEwJVUzEiMCAGA1UEChMZR29vZ2xlIFRydXN0IFNlcnZpY2VzIExM
QzETMBEGA1UEAxMKR1RTIENBIDFENDAeFw0yMjA5MjcyMjA1NTVaFw0yMjEyMjYy
MjA1NTRaMBYxFDASBgNVBAMTC2ppbWJyaWcuY29tMIIBIjANBgkqhkiG9w0BAQEF
AAOCAQ8AMIIBCgKCAQEAtKq4VB61i41USpmFwS9aS1DKT5fAHSn9+biRXSSVtA+U
PV/fXN/WuoZTWrExcP8Aln6qHmtL3rAKy+uXBxNu3U10LLsC276LVl56ZU9d/Tlv
lqSAe9DRyLBssYqh9uFBi5yldDYUAjDpwccXtFVO5f3m1bKndbYx3epY4RH7mRPZ
t24FjJB7RTXV8XqTBZh2bpBeW47mdwh6Pnz49kGPx9FcLArhTpB40TTUVCHk0y6N
ldpFiJEnpj2C/ZqfMyqgzvaBxwn7WLd4rKflnrlY68FdfTCdTnBm6kKpqkuTJrKb
C5/JemkoxeHjFViY9Eo8ZzCY5iv7BXmxOXAvbAQCsQIDAQABo4ICdDCCAnAwDgYD
VR0PAQH/BAQDAgWgMBMGA1UdJQQMMAoGCCsGAQUFBwMBMAwGA1UdEwEB/wQCMAAw
HQYDVR0OBBYEFGlHUdtzU2C7npdaqRmbTI32715DMB8GA1UdIwQYMBaAFCXiGA6y
V5GUKuXUXYaQg95Ts7iSMHgGCCsGAQUFBwEBBGwwajA1BggrBgEFBQcwAYYpaHR0
cDovL29jc3AucGtpLmdvb2cvcy9ndHMxZDQvZ3ZVRHgyX1piYjgwMQYIKwYBBQUH
MAKGJWh0dHA6Ly9wa2kuZ29vZy9yZXBvL2NlcnRzL2d0czFkNC5kZXIwFgYDVR0R
BA8wDYILamltYnJpZy5jb20wIQYDVR0gBBowGDAIBgZngQwBAgEwDAYKKwYBBAHW
eQIFAzA8BgNVHR8ENTAzMDGgL6AthitodHRwOi8vY3Jscy5wa2kuZ29vZy9ndHMx
ZDQvWDJLb3otLWtqekkuY3JsMIIBBgYKKwYBBAHWeQIEAgSB9wSB9ADyAHcABZwB
0yDgB4QTlYBJjRF8kDJmr69yULWvO0akPhGEDUoAAAGDgT7kXwAABAMASDBGAiEA
2lUyWC77NjGnclGlpXmL+Ki8/qLfTNDYGmSQ5+WSzJUCIQDn6fvOQ6ViiLaCdTzm
+5fve+1qm01BMJBxiUhdl7IhrwB3ACl5vvCeOTkh8FZzn2Old+W+V32cYAr4+U1d
JlwlXceEAAABg4E+5CEAAAQDAEgwRgIhAOU/ws0IuiKWlnHbPT089EN7/hP5KHYv
XRcAnKMCi+BTAiEAjSDogcWeB7lvfWKg7NspThEReC4u/BEgyPxIXgXjqvcwDQYJ
KoZIhvcNAQELBQADggEBAJuV88ED1WdFnZjJRIfn+MOhUfIesFpq9fiTm/UZaiuF
ZEAasIYpUy/rKf7xUF4AptUqJ7lz6IJ+1eYOpXzvdKkzNFMCF2Hxk7u3GSwUoN/H
Ku76Py7VIdtZZ0PLWRGAhZUbJ5AcWuedDK6FjhLztIjMu9Q9hiS3VLxGhAv5zltj
eIQpqdescuxKgkvavugzdaAfuF0ElfwlCZPvpWzQSrFLKVY6Z8DbbzloL0PXjxKo
2ODB7ao2HVr2viJiGnf5ygfbB+5wGDCMfTdZs8cwy9T+xBvgugojgWWiGhUfnq7C
FzEfSlwgzlIvrXY4PA5pcflNyb5uLxAIDiYqGYykELY=
-----END CERTIFICATE-----
 1 s:C = US, O = Google Trust Services LLC, CN = GTS CA 1D4
   i:C = US, O = Google Trust Services LLC, CN = GTS Root R1
-----BEGIN CERTIFICATE-----
MIIFjDCCA3SgAwIBAgINAgCOsgIzNmWLZM3bmzANBgkqhkiG9w0BAQsFADBHMQsw
CQYDVQQGEwJVUzEiMCAGA1UEChMZR29vZ2xlIFRydXN0IFNlcnZpY2VzIExMQzEU
MBIGA1UEAxMLR1RTIFJvb3QgUjEwHhcNMjAwODEzMDAwMDQyWhcNMjcwOTMwMDAw
MDQyWjBGMQswCQYDVQQGEwJVUzEiMCAGA1UEChMZR29vZ2xlIFRydXN0IFNlcnZp
Y2VzIExMQzETMBEGA1UEAxMKR1RTIENBIDFENDCCASIwDQYJKoZIhvcNAQEBBQAD
ggEPADCCAQoCggEBAKvAqqPCE27l0w9zC8dTPIE89bA+xTmDaG7y7VfQ4c+mOWhl
UebUQpK0yv2r678RJExK0HWDjeq+nLIHN1Em5j6rARZixmyRSjhIR0KOQPGBMUld
saztIIJ7O0g/82qj/vGDl//3t4tTqxiRhLQnTLXJdeB+2DhkdU6IIgx6wN7E5NcU
H3Rcsejcqj8p5Sj19vBm6i1FhqLGymhMFroWVUGO3xtIH91dsgy4eFKcfKVLWK3o
2190Q0Lm/SiKmLbRJ5Au4y1euFJm2JM9eB84Fkqa3ivrXWUeVtye0CQdKvsY2Fka
zvxtxvusLJzLWYHk55zcRAacDA2SeEtBbQfD1qsCAwEAAaOCAXYwggFyMA4GA1Ud
DwEB/wQEAwIBhjAdBgNVHSUEFjAUBggrBgEFBQcDAQYIKwYBBQUHAwIwEgYDVR0T
AQH/BAgwBgEB/wIBADAdBgNVHQ4EFgQUJeIYDrJXkZQq5dRdhpCD3lOzuJIwHwYD
VR0jBBgwFoAU5K8rJnEaK0gnhS9SZizv8IkTcT4waAYIKwYBBQUHAQEEXDBaMCYG
CCsGAQUFBzABhhpodHRwOi8vb2NzcC5wa2kuZ29vZy9ndHNyMTAwBggrBgEFBQcw
AoYkaHR0cDovL3BraS5nb29nL3JlcG8vY2VydHMvZ3RzcjEuZGVyMDQGA1UdHwQt
MCswKaAnoCWGI2h0dHA6Ly9jcmwucGtpLmdvb2cvZ3RzcjEvZ3RzcjEuY3JsME0G
A1UdIARGMEQwCAYGZ4EMAQIBMDgGCisGAQQB1nkCBQMwKjAoBggrBgEFBQcCARYc
aHR0cHM6Ly9wa2kuZ29vZy9yZXBvc2l0b3J5LzANBgkqhkiG9w0BAQsFAAOCAgEA
IVToy24jwXUr0rAPc924vuSVbKQuYw3nLflLfLh5AYWEeVl/Du18QAWUMdcJ6o/q
FZbhXkBH0PNcw97thaf2BeoDYY9Ck/b+UGluhx06zd4EBf7H9P84nnrwpR+4GBDZ
K+Xh3I0tqJy2rgOqNDflr5IMQ8ZTWA3yltakzSBKZ6XpF0PpqyCRvp/NCGv2KX2T
uPCJvscp1/m2pVTtyBjYPRQ+QuCQGAJKjtN7R5DFrfTqMWvYgVlpCJBkwlu7+7KY
3cTIfzE7cmALskMKNLuDz+RzCcsYTsVaU7Vp3xL60OYhqFkuAOOxDZ6pHOj9+OJm
YgPmOT4X3+7L51fXJyRH9KfLRP6nT31D5nmsGAOgZ26/8T9hsBW1uo9ju5fZLZXV
VS5H0HyIBMEKyGMIPhFWrlt/hFS28N1zaKI0ZBGD3gYgDLbiDT9fGXstpk+Fmc4o
lVlWPzXe81vdoEnFbr5M272HdgJWo+WhT9BYM0Ji+wdVmnRffXgloEoluTNcWzc4
1dFpgJu8fF3LG0gl2ibSYiCi9a6hvU0TppjJyIWXhkJTcMJlPrWx1VytEUGrX2l0
JDwRjW/656r0KVB02xHRKvm2ZKI03TglLIpmVCK3kBKkKNpBNkFt8rhafcCKOb9J
x/9tpNFlQTl7B39rJlJWkR17QnZqVptFePFORoZmFzM=
-----END CERTIFICATE-----
 2 s:C = US, O = Google Trust Services LLC, CN = GTS Root R1
   i:C = BE, O = GlobalSign nv-sa, OU = Root CA, CN = GlobalSign Root CA
-----BEGIN CERTIFICATE-----
MIIFYjCCBEqgAwIBAgIQd70NbNs2+RrqIQ/E8FjTDTANBgkqhkiG9w0BAQsFADBX
MQswCQYDVQQGEwJCRTEZMBcGA1UEChMQR2xvYmFsU2lnbiBudi1zYTEQMA4GA1UE
CxMHUm9vdCBDQTEbMBkGA1UEAxMSR2xvYmFsU2lnbiBSb290IENBMB4XDTIwMDYx
OTAwMDA0MloXDTI4MDEyODAwMDA0MlowRzELMAkGA1UEBhMCVVMxIjAgBgNVBAoT
GUdvb2dsZSBUcnVzdCBTZXJ2aWNlcyBMTEMxFDASBgNVBAMTC0dUUyBSb290IFIx
MIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEAthECix7joXebO9y/lD63
ladAPKH9gvl9MgaCcfb2jH/76Nu8ai6Xl6OMS/kr9rH5zoQdsfnFl97vufKj6bwS
iV6nqlKr+CMny6SxnGPb15l+8Ape62im9MZaRw1NEDPjTrETo8gYbEvs/AmQ351k
KSUjB6G00j0uYODP0gmHu81I8E3CwnqIiru6z1kZ1q+PsAewnjHxgsHA3y6mbWwZ
DrXYfiYaRQM9sHmklCitD38m5agI/pboPGiUU+6DOogrFZYJsuB6jC511pzrp1Zk
j5ZPaK49l8KEj8C8QMALXL32h7M1bKwYUH+E4EzNktMg6TO8UpmvMrUpsyUqtEj5
cuHKZPfmghCN6J3Cioj6OGaK/GP5Afl4/Xtcd/p2h/rs37EOeZVXtL0m79YB0esW
CruOC7XFxYpVq9Os6pFLKcwZpDIlTirxZUTQAs6qzkm06p98g7BAe+dDq6dso499
iYH6TKX/1Y7DzkvgtdizjkXPdsDtQCv9Uw+wp9U7DbGKogPeMa3Md+pvez7W35Ei
Eua++tgy/BBjFFFy3l3WFpO9KWgz7zpm7AeKJt8T11dleCfeXkkUAKIAf5qoIbap
sZWwpbkNFhHax2xIPEDgfg1azVY80ZcFuctL7TlLnMQ/0lUTbiSw1nH69MG6zO0b
9f6BQdgAmD06yK56mDcYBZUCAwEAAaOCATgwggE0MA4GA1UdDwEB/wQEAwIBhjAP
BgNVHRMBAf8EBTADAQH/MB0GA1UdDgQWBBTkrysmcRorSCeFL1JmLO/wiRNxPjAf
BgNVHSMEGDAWgBRge2YaRQ2XyolQL30EzTSo//z9SzBgBggrBgEFBQcBAQRUMFIw
JQYIKwYBBQUHMAGGGWh0dHA6Ly9vY3NwLnBraS5nb29nL2dzcjEwKQYIKwYBBQUH
MAKGHWh0dHA6Ly9wa2kuZ29vZy9nc3IxL2dzcjEuY3J0MDIGA1UdHwQrMCkwJ6Al
oCOGIWh0dHA6Ly9jcmwucGtpLmdvb2cvZ3NyMS9nc3IxLmNybDA7BgNVHSAENDAy
MAgGBmeBDAECATAIBgZngQwBAgIwDQYLKwYBBAHWeQIFAwIwDQYLKwYBBAHWeQIF
AwMwDQYJKoZIhvcNAQELBQADggEBADSkHrEoo9C0dhemMXoh6dFSPsjbdBZBiLg9
NR3t5P+T4Vxfq7vqfM/b5A3Ri1fyJm9bvhdGaJQ3b2t6yMAYN/olUazsaL+yyEn9
WprKASOshIArAoyZl+tJaox118fessmXn1hIVw41oeQa1v1vg4Fv74zPl6/AhSrw
9U5pCZEt4Wi4wStz6dTZ/CLANx8LZh1J7QJVj2fhMtfTJr9w4z30Z209fOU0iOMy
+qduBmpvvYuR7hZL6Dupszfnw0Skfths18dG9ZKb59UhvmaSGZRVbNQpsg3BZlvi
d0lIKO2d1xozclOzgjXPYovJJIultzkMu34qQb9Sz/yilrbCgj8=
-----END CERTIFICATE-----
---
Server certificate
subject=CN = jimbrig.com

issuer=C = US, O = Google Trust Services LLC, CN = GTS CA 1D4

---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 4682 bytes and written 393 bytes
Verification: OK
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
```

</p></details>

***

## Appendix: Links

- [[Code]]
- [[Development]]

*Backlinks:*

```dataview
list from [[Bash - Function to Show Website Certificate from Hostname]] AND -"Changelog"
```