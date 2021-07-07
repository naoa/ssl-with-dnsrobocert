# ssl-with-dnsrobocert

SSL certificate issuance / automatic renewal by Let's encrypt DNS authentication by dnsrobocert

dnsrobocertによるLetsencryptのDNS認証でSSL証明書発行・自動更新

## Usage

* Edit dnsrobocert/config.yml

  Replace ``<your-email>``, ``<your-dns-provider>``, ``<your-dns-provider-token>``, ``<your-domain>``

```
draft: false

acme:
  email_account: <your-email>
  staging: false

profiles:
  - name: dns_profile
    provider: <your-dns-provider> # choose your dns provider https://dnsrobocert.readthedocs.io/en/latest/providers_options.html#providers-options
    provider_options:
      auth_token: <your-dns-provider-token>

certificates:
  - domains:
      - <your-domain>
    profile: dns_profile
```

* Run

```
docker-compose up -d
```

## Licence

Public Domain
