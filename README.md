# storm-release


* Steps to deploy:
```
git clone https://github.com/bosh-packages/java-release.git ~/workspace/bosh-packages/
git clone https://github.com/bosh-packages/python-release.git ~/workspace/bosh-packages/
```

* Clone this repo and Go to this storm-release directory and execute below commands
```
cd storm-release
bosh vendor-package openjdk-8 ~/workspace/bosh-packages/java-release
bosh vendor-package python-2.7 ~/workspace/bosh-packages/python-release
./prepare
bosh -n create-release --force
bosh -n upload-release
```

* Modify manifests/storm.yml as per your env settings and deploy release 
```
bosh -d storm deploy manifests/storm.yml
```
