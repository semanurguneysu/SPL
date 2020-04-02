## List of Correlation Searches
```spl

| rest /servicesNS/-/-/saved/searches splunk_server=local 
| where match('action.correlationsearch.enabled', "1|[Tt]|[Tt][Rr][Uu][Ee]")  
| rename eai:acl.app as app, title as csearch_name, action.correlationsearch.label as csearch_label, action.notable.param.security_domain as security_domain
| table csearch_name, csearch_label, app, security_domain, description,search

```
