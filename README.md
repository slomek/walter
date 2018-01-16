# Walter - the Vault guard

Walter is a wrapper around the official client of [Vault by Hashicorp](https://github.com/hashicorp/vault).

## Installation 

```
go get -u github.com/slomek/walter
```

In order to start using Walter, you need to create a configuration file with data necessary to connect to your Vault instance:

```
# /path/to/config.yaml
token: YOUR-ACCESS-TOKEN
vault_addr: ADDRESS-OF-YOUR-VAULT-SERVER
```

Walter looks for a configuration file by checking the `WALTER_CONFIG_FILE` environmental variable value, so you need to define it accordingly:

```
export WALTER_CONFIG_FILE=/path/to/config.yaml
```

## Usage

### Reading the secret

```
$ walter -k secret/hello                                                                   
Secret data:
 - lang -> go
 - value -> world
 - year -> 2018
```

### Reading one property from a secret

```
$ walter -k secret/hello -p value
secret/hello:value -> world
```
