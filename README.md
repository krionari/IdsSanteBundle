# AldafluxIdsSanteBundle"

generated by Al
## installation

```
composer require aldaflux/ids-sante-bundle:dev-master
```

## test login

/ids/checkpasswordservice/test

(extends base.html.twig)

## show log login

/ids/logs

(extends base.html.twig)

## security.yaml

```
security
   access_control:
        - { path: '^/ids/logs', roles: ROLE_ADMIN }
```


## config/routes/ids_routes.yaml
```
ids_routes:
    resource: "@AldafluxIdsSanteBundle/Resources/config/routing/routes.yml"
```






## config/packages/aldaflux_ids_sante.yaml

```
aldaflux_ids_sante:
    application_name: appname
    active: false # default
    prefixe: '03' # default
    user:
        class: "App:User" # default
        find_by: "findOneByUsername" # default
    soap:
        wsdl:
            log: http://api.idshost.priv/log.wsdl
when@dev:
    aldaflux_ids_sante:
        proxy:
            enabled: '%env(bool:IDS_PROXY_ENABLED)%'
            ip: '%env(resolve:IDS_PROXY_IP)%'

```

