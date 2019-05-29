# storm-release

* Steps to deploy:
```
git clone https://github.com/bosh-packages/java-release.git ~/workspace/bosh-packages/
git clone https://github.com/bosh-packages/python-release.git ~/workspace/bosh-packages/
```

* Clone this repo and Go to this storm-release directory
```
cd storm-release
bosh vendor-package openjdk-8 ~/workspace/bosh-packages/java-release
bosh vendor-package ~/workspace/bosh-packages/python-release
bosh -n create-release --force
bosh -n upload-release
```

* Modify manifests/storm.yml as per your env settings and deploy release 
```
bosh -d storm deploy manifests/storm.yml
```




