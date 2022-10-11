## Create a MISP object

### MISP object location: /var/www/MISP/app/files/misp-objects/objects
File to change: definition.json 

### Header:
- UUID
- description and name
- version
- meta-category
- required
- requireOneOf

### Objcet template attributes
- description
- misp-attribute
- ui-priority
- disable_correlation
- multiple
- values_list

### Merge

### Update MISP
Global actions > List Object Templates > Update Objects

### Relations
/var/www/MISP/app/files/misp-objects/relationships/definition.json

### Validation
./jq_all_the_things.sh
./validate_all.sh

source: 
https://www.misp-project.org/2021/03/17/MISP-Objects-101.html/
