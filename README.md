# apps
Application recipes for SlipStream

## Update the content of this repository from Nuvla&trade;
To fetch the current version of the apps from Nuvla&trade;, execute the following script into the current directory:
```bash
#!/bin/env bash -x

pushd ../
ss-module-download -u <username> -p <password> \
  --remove-cloud-specific \
  --remove-group-members \
  --reset-commit-message apps
popd
```

`<username>` and `<password>` should be valid credentials for the Nuvla&trade; service.



