# sud - status up down

Multi-purpose Extensible (De)Provisioning Utility

## CLI Usage

### **Provision/Update an entity**

manually via cli

`$ sud up <type> <id> prop=value`

via config file

`$ sud up --file path/to/entities.json`

### **Deprovision an entity**

manually via cli

`$ sud down <type> <id>`

via config file

`$ sud down --file path/to/entities.json`

## Examples

### Onboard an employee's Office 365, Nextcloud and JIRA accounts

employees.yml

```yaml
joe_smith:
  - name: Joe Smith
  - email: joe.smith@company.org
  - services:
    - office365:
    - nextcloud:
      - username: email
    - jira:
```