---
title: "Root Certificates"
description: ""
---

This section contains links to common root SSL certificates used in {{% tts%}}, issued by trusted certificate authorities (CAs).

<!--more-->

## Which Certificate Is Right For My Deployment?

The [complete certificate list](https://curl.haxx.se/ca/cacert.pem) contains all CA certificates trusted by modern browsers, so if you use certificates issued by a popular CA, you should be covered by this one.

The <a href="ca.pem" download>minimal certificate list</a> contains a tailored list of certificates used in standard {{% tts %}} deployments for devices which do not support the larger list due to memory constraints.

Unfortunately, some gateways do not support concatenated certificate lists at all. If your device will not connect using the complete or minimal certificate lists, you must use the specific certificate you use to configure TLS for your domain. If you use Let's Encrypt, use the [Let's Encrypt ISRG Root X1 or DST Root X3](#lets-encrypt).

## Complete Certificate List

This `.pem` file contains all common CA certificates trusted by Mozilla, and is extracted and hosted by [curl](https://curl.haxx.se/docs/caextract.html).

Download the complete certificate list from curl [here](https://curl.haxx.se/ca/cacert.pem).

## Minimal Certificate List for Common Installations

This `.pem` file contains certificates used in standard {{% tts %}} deployments, and is small enough to fit on memory constrained devices such as Gateways.

Download the minimal certificate list <a href="ca.pem" download>here</a>.

## Let's Encrypt

### ISRG Root X1

Many {{% tts %}} deployments use the Let's Encrypt ISRG Root X1 Trust. If using Let's Encrypt to secure your domain, you may download the ISRG Root X1 Trust file [here](https://letsencrypt.org/certs/isrgrootx1.pem).

### DST Root X3

Some {{% tts %}} deployments use the Let's Encrypt DST Root X3 Trust, although it expires in 2021 and is being phased out. If your deployment uses the legacy DST Root X3 Trust, download it [here](https://letsencrypt.org/certs/lets-encrypt-x3-cross-signed.pem).

> Unfortunately, if you use a single certificate and that certificate expires, your gateway will stop connecting until you update the certificate. The minimal and complete certificate lists contain the ISRG Root X1 and DST Root X3 certificates, but some gateways do not support concatenated certificate lists, even though they are part of the [ietf spec](https://tools.ietf.org/html/rfc1421) :( If you know you are using Let's Encrypt to secure your domain, use one of these `.pem` files as your gateway's Server Certificate for maximum compatibility.


