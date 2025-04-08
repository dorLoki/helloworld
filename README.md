## Architecture
```mermaid
 architecture-beta
    service user(internet)[User]

    group web(cloud)[Web]
    group api(cloud)[API]
    group idp(cloud)[Shibboleth Identity Provider]
    
    service frontend(server)[Frontend Webserver] in web
    service restapi(server)[REST API] in api
    service apidb(database)[API Database] in api
    service shibboleth(server)[Shibboleth IdP] in idp
    service idpdb(database)[IdP Database] in idp

    user:R -- L:frontend
    frontend:R -- L:restapi
    restapi:R -- L:apidb
    frontend:B -- T:shibboleth
    shibboleth:R -- L:idpdb
 ```
