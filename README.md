# SuD - Status up Down

A Multi-purpose Extensible (De)Provisioning Utility.

SuD can be used to automate provisioning of any resource that can be defined by the CrUD data model. A typical use case would be to automate onboarding and termination processes for an HR department. SuD is similar to IaC services like terraform, only it isn't restricted 

## CLI Usage

### **Provision/Update a resource**

manually via cli

`$ sud up <provider> <id> prop=value`

via config file

`$ sud up --file path/to/entities.json`

### **Deprovision a resource**

manually via cli

`$ sud down <provider> <id>`

via config file

`$ sud down --file path/to/entities.json`

## Providers

**Summary** A provider is a set of configuration properties for a provider to manage real resources. Provider configuration files are stored in `$SUD_HOME/providers/` as json files containing required adapter configuration properties.

**Configure a Provider** by running the following command, any missing required provider parameters will collected interactively via a prompt.

`$ sud provider new <provider> <name> token=123`

## Examples

### Onboard an employee's Office 365, Nextcloud and JIRA accounts

manually via cli

`$ sud up office365 joe.smith@company.org name='Joe Smith'`

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
