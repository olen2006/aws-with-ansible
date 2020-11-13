# Running ansible-playbook on AWS using keys.yml

## Useful commands

`ansible-vault --help `

`ansible-vault view keys.yml`

`ansible-vault edit keys.yml`

## Encryption/Decryption of keys.yml file.

`ansible-vault encrypt keys.yml`

`ansible-vault decrypt keys.yml`

## Running ansible-playbook using --ask-vault-pass option.

`asible-vault --ask-vault-pass ec2-change-state.yml`

- Better approuch to use **dev@prompt, stage@prompt** etc. It helps ansible to decrypt data more efficiantly.
- Since ansible 2.4 + **--vault-id** allowed to use with different passwords through out the same playbook.

- Creation of a new vault using inline encryption. Output can be copied and passed into ansible-playbook.

`ansible-vault encrypt_string --vault-id prod@prompt 'new_var: new-value'`

# Another way is to store AWS keys under keys.sh file

```javascript
#!/bin/sh
export AWS_ACCESS_KEY_ID='ACCESS_KEY'
export AWS_SECRET_ACCESS_KEY='SECRET_ACCESS_KEY'
export AWS_REGION='us-east-1'
```
