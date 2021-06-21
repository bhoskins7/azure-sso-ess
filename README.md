# azure-sso-ess
```
Azure SSO Contents          = elasticsearch.yml config settings
App Federation Metadata Url = idp.metadata.path
Azure AD Identifier          = idp.entity_id 
```
## Role Mappings 
```
POST /_xpack/security/role_mapping/CLOUD_SAML_ELASTICADMIN_TO_SUPERUSER 
{
   "enabled": true,
    "roles": [ "superuser" ], 
    "rules": { "all" : [ 
        { "field": { "realm.name": "saml-realm-es” } }, 
        { "field": { "groups": "elasticadmins" } }
    ]},
    "metadata": { "version": 1 }
}
```
