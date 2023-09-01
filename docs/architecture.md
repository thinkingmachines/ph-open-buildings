# Project Architecture and Access to Production

``` @TODO: Summary of Architecture and steps to access each component ```

The `github-starter` project is meant as a base repository template; it should be a basis for other projects. 

`github-starter` is hosted on Github, and is available as a [Template in Backstage]([url](https://catalog.tm8.dev/create?filters%5Bkind%5D=template&filters%5Buser%5D=all)****)

## Architecture Details
```Note: Structure of this document assumes Dev and Prod are in different Cloud Platform projects. You can reduce the sections for architecture if redundant. Just note the datasets, vms, buckets, etc. being used in Dev vs Prod ```
- Provider: ``` @TODO: GCP / AWS / Azure / etc ```
- Dev Environment: ``` @TODO: Link to dev env ```
- Prod Environment: ``` @TODO: Link to prod env ```
- Technology: ``` @TODO: Python / Airflow / Dagster / Postgres / Snowflake / etc ```

### Implementation Notes
``` @TODO: Note down known limitations, possible issues, or known quirks with the project. The following questions might help: ``` <br>
``` 1. Which component needs most attention? ie. Usually the first thing that needs tweaks ``` <br>
``` 2. Are the parts of the project that might break in the future? (eg. Filling up of disk space, memory issues if input data size increases, a web scraper, etc.)``` <br>
``` 3. What are some known limitations for the project? (eg. Input data schema has to remain the same, etc.)```

## Dev Architecture
``` @TODO: Dev architecture diagram and description. Please include any OAuth or similar Applications.```
``` @TODO: List out main components being used and their descriptions.```

### Virtual Machines
``` @TODO: List VMs used and what they host```
### Datasets
``` @TODO: List datasets given following format```
#### Dataset A
- Description: PSGC Data
- File Location: GCS Uri / GDrive link / etc
- Retention Policy: 3 months

### Tokens and Accounts
``` @TODO: Please fill out all Tokens and Accounts being used in the project given the format below. Include tokens from client used in the project.```

**Dev Github Service Account Token**

- Location: Bitwarden Github Collection
- Person in charge: Client Name (client@email.com)
- Validity: 30 Days
- Description: This token is used to call the Github API using the account ``sample-account@thinkingmachin.es`
- How to Refresh:
  1. Go to github.com
  2. Click refresh

## Production Architecture
``` @TODO: Prod architecture diagram and description. Please include any OAuth or similar Applications.```
``` @TODO: List out main components being used and their descriptions.```

### Virtual Machines
``` @TODO: List VMs used and what they host```
### Datasets
``` @TODO: List datasets given following format```
#### Dataset A
- Description: PSGC Data
- File Location: GCS Uri / GDrive link / etc
- Retention Policy: 3 months

### Tokens and Accounts
``` @TODO: Please fill out all Tokens and Accounts being used in the project given the format below. Include tokens from client used in the project.```

**Prod Github Service Account Token**

- Location: Bitwarden Github Collection
- Person in charge: Client Name (client@email.com)
- Validity: 30 Days
- Description: This token is used to call the Github API using the account ``sample-account@thinkingmachin.es`
- How to Refresh:
  1. Go to github.com
  2. Click refresh

## Accessing Cloud Platform Environments
```@TODO: Describe the steps to access the prod VMs/platform```

**Get access to Client AWS Platform**
- Person in charge: Client Name/Dev Name
- Bitwarden Credentials: 
1. Install AWS CLI
2. Run `aws configure` - ID and Secret from Bitwarden

**Accessing Prod VM**
1. Update your ssh config to have the following:
```
Host project-vpn
   Hostname xx.xxx.xxx.xxx
   User ubuntu
   
# Use the Private IP for the rest
Host dev-project-app
   Hostname xxx.xx.xx.xx
   User ubuntu
   ProxyJump project-vpn
```
2. Run `ssh dev-project-app`

**Access Prod App in UI**
1. Install `sshuttle`
2. Run `sshuttle -r dev-project-app xxx.xx.0.0/16`
3. Open web browser using the Private IP found in you SSH config (http:xxx.xx.xx.xx:3000) 