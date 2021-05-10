
## Creating a mock data

### Combine Technology data

```
jq -n '{ software_templates: [ inputs ] | add }' examples/featured/*.json > featured.json
```

jq -n '{ integrations: [ inputs ] | add }' integrations/*.json > integrations.json

### Combine Integrations data

```
jq -s . examples/integrations/*.json > examples/integrations.json
```

### Combine Software Templates data

```
jq -s . examples/software_templates/*.json > examples/software_templates.json
```

### Combine all data

```
jq s . examples/technologies.json examples/integrations.json examples/software_templates.json > db.json
```


### Start Json Server

```
json-server --watch db.json
```