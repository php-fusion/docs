---
description: >-
  This guide shows you how to create your own locally trusted, self-signed SSL
  certificate for local development use.
---

# Self Signed SSL Certificate

### Generating a self-signed SSL Certificate in local machine

Are you tired of using non-trusted SSL certificates on your Local development projects?. I know to maintain your own Certificate Authority\(CA\) is a pain in the neck, with arcane procedures and commands. In this guide, I’ll show you a simple way to use trusted SSL certificates on your Local development machine without having CA.

mkcert is a simple zero-config tool written by Filippo Valsorda in Go for making locally trusted development certificates with any names you’d like without any configuration. This will help you since it is impossible to get certificates from trusted Certificate Authorities for local names that don’t have a valid DNS record. So let’s dive in to install and use mkcert.

In this guide, you can learn how to generate a valid SSL certificate with the lock in the url address bar for any of your locally developed sites with a few simple steps.

Before we start, we need to install a 3rd party runtime into your machine. These commands will work with any Linux based shell terminal. If you are on windows, use Windows Power Shell, so no worries there.

#### Install Choco

We begin by installing choco into your machine with this command. Simply paste it into your shell.

```text
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

#### Install mkcert

Now get and install `mkcert` with the following command into your shell.

```text
choco install mkcert
```

Now you're set, and lets move on to the next part.

#### How to Use mkcert to generate locally trusted SSL certificates

mkcert has support for the following root stores:

* macOS system store
* Windows system store
* Linux variants that provide either
  * `update-ca-trust` \(Fedora, RHEL, CentOS\) or
  * `update-ca-certificates` \(Ubuntu, Debian\)
* Firefox \(macOS and Linux only\)
* Chrome and Chromium
* Java \(when `JAVA_HOME` is set\)

To get the help page for mkcert, pass the option`--help`.

```text
Usage of mkcert:

$ mkcert -install
Install the local CA in the system trust store.

$ mkcert example.org
Generate "example.org.pem" and "example.org-key.pem".

$ mkcert example.com myapp.dev localhost 127.0.0.1 ::1
Generate "example.com+4.pem" and "example.com+4-key.pem".

$ mkcert '*.example.com'
Generate "_wildcard.example.com.pem" and "_wildcard.example.com-key.pem".

$ mkcert -pkcs12 example.com
Generate "example.com.p12" instead of a PEM file.

$ mkcert -uninstall
Uninstall the local CA (but do not delete it).

Change the CA certificate and key storage location by setting $CAROOT,
print it with "mkcert -CAROOT".
```

You can get your CA root directory using:

```text
$ mkcert -CAROOT
/home/jmutai/.local/share/mkcert
```

You need to start by installing the local CA in your system trust store.

```text
# mkcert -install
Created a new local CA at "/home/jmutai/.local/share/mkcert" ?
The local CA is now installed in the system trust store! ⚡️
```

Once done, you can start generating SSL certificates for your domains. As an example, I’ll generate a new certificate valid for the following names:

```text
- "mydomain.com"
- "*.mydomain.co"
- "myapp.net"
- "localhost"
- "127.0.0.1"
- "::1"
```

The output will be like below:

```text
# mkcert mydomain.com '*.mydomain.co' myapp.net localhost 127.0.0.1 ::1
Using the local CA at "/root/.local/share/mkcert" ✨

Created a new certificate valid for the following names ?
- "mydomain.com"
- "*.mydomain.co"
- "myapp.net"
- "localhost"
- "127.0.0.1"
- "::1"
The certificate is at "./mydomain.com+5.pem" and the key at "./mydomain.com+5-key.pem" ✅
```

You should be able to view the contents of the certificate:

```text
# cat ./mydomain.com+5.pem
-----BEGIN CERTIFICATE----- MIIEVDCCArygAwIBAgIRAL2vyvexRiXjWMWF688t9RswDQYJKoZIhvcNAQELBQAw WTEeMBwGA1UEChMVbWtjZXJ0IGRldmVsb3BtZW50IENBMRcwFQYDVQQLDA5yb290 QHVidW50dS0wMTEeMBwGA1UEAwwVbWtjZXJ0IHJvb3RAdWJ1bnR1LTAxMB4XDTE4 MDgxNTA2MjIzMFoXDTI4MDgxNTA2MjIzMFowQjEnMCUGA1UEChMebWtjZXJ0IGRl dmVsb3BtZW50IGNlcnRpZmljYXRlMRcwFQYDVQQLDA5yb290QHVidW50dS0wMTCC ASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAMg6ByQe5vjX65HYoOe/QyRo yotQOvBX8k8RJxQSXmTYsTGeYjTtlfLlubJ/AmGovzfPK6CmSWkTK6czENsR2DBH mAHyyu1PdeJihnBZSNAlkEIGNPZvxqKlNZvqe1gxMntHG569YKBl52EaiMiDu3D0 yk+dvIHuCtvGseFUxRwnc4gq4B6yhyGR6y1dmL7eZkrIAgMHxdktavThscvJ3N7A N4dY7iackLiajqjRzT6/iVR0NRRbqxDlgsfrq6MGkAnri56LuZBZmyF85c+kpvuN bHEAAUvxziHORX0+NmBedcajr16rYV4+/IJXbY2llLkprRG2Ar8CqrblH2uBX+8C AwEAAaOBrTCBqjAOBgNVHQ8BAf8EBAMCBaAwEwYDVR0lBAwwCgYIKwYBBQUHAwEw DAYDVR0TAQH/BAIwADAfBgNVHSMEGDAWgBRLV1qAcMY0/atqn4AS3sWCOoo4OTBU BgNVHREETTBLggxteWRvbWFpbi5jb22CDSoubXlkb21haW4uY2+CCW15YXBwLm5l dIIJbG9jYWxob3N0hwR/AAABhxAAAAAAAAAAAAAAAAAAAAABMA0GCSqGSIb3DQEB CwUAA4IBgQBaQcM7oe4TNQfdwvkZk0rTK1aoXteBF7JqxdhFqL1wWNAO+HTsRuzO My19o3mL+9SVjuv1NCEUCVGXQ5FK+HFdBdWm1cAKzHM/j6pwo0k60K9kIfyQZfsh GjDDtrE+86T16JwWTozFyyZHDAhskQuudwha4pZWgrwZudAdqaAOQW59+8s3gYaj Wd10hiptLbAnhd3DKPgnhjgpIT6zvtJ7gvm8fXVwOyoPfbIm3kl94rIa0BVrhmeA ma227ehRK0iUwA1oclZ4dbRfcjNgL79ryVgffOgTD1O3mWzwvGenD7/oG9FZQ2fK WPdh4gdV+f5fZ+GiLA2KPIShrReFlt70pUJDkDHT0AEuSiFZQ5vVc3KV/3k3HUTJ tmkiePMoMGB/kEVyo1is3NDUBkofMTYSFjVdSgZ9rrefoUe/tfqBeh5IV+ZRUv3p kSsXe0sBnqtSa5ExQ+Uv2X6/jEBBEAoYN6GmL+poV06Ra6/nnXPnaRLkQ/8CT8sp xKtvdnyDa6Y= -----END CERTIFICATE-----
```

The private key is:

```text
~/.mydomain.com+5-key.pem
```

#### Testing mkcert certificate

Let’s now test mkcert certificate using a simple Nginx configuration file. Forgive me this example is done on Ubuntu 18.04 system.

```text
sudo apt-get install nginx
```

Create a simple web page

```text
# cat /etc/nginx/conf.d/test.conf 
server {
   listen 80;
   server_name mydomain.com myapp.net;
   root /var/www/test;
}

server {
   listen *:443 ssl http2;
   root /var/www/test;
   server_name mydomain.com myapp.net;
   ssl_certificate /home/jmutai/mydomain.com+5.pem; 
   ssl_certificate_key /home/jmutai/mydomain.com+5-key.pem;
}
```

Make sure your `/etc/hosts` file has a record for used domains.

```text
127.0.0.1 myapp.net
127.0.0.1 mydomain.com
```

Open your browser and use domain provided, you should get a green bar.



