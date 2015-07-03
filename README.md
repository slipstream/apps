# SlipStream/apps
Application recipes for SlipStream.

## License
All SlipStream modules of this repository are licensed under the *Apache License v2.0*.

See [LICENSE](LICENSE) for more details.

## Update the content of this repository from Nuvla&trade;
To fetch the current version of the apps from Nuvla&trade;, clone this repository and then execute the following script into the directory corresponding to this repository you've just cloned:
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

## Push these apps to your SlipStream instance
To push these apps to your SlipStream instance, execute the following script in a linux machine:
```bash
#!/bin/env bash -x

tmpdir='/tmp/ss-apps'
mkdir -p $tmpdir

pushd $tmpdir
wget -O apps.zip https://github.com/slipstream/apps/archive/master.zip
unzip -o apps.zip
rm -f apps.zip
ss-module-upload -u <username> -p <password> \
  --endpoint=https://<SlipStream IP/HOSTNAME> \
  $(find . -name '*.xml')
popd

rm -Rf $tmpdir
```

`<username>` and `<password>` should be valid credentials for the Nuvla&trade; service.

`<SlipStream IP/HOSTNAME>` should correspond to the IP address (or the hostname) of your SlipStream instance.
