# Magma Chart Repository

[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/magma)](https://artifacthub.io/packages/search?repo=magma)
[![Release Charts](https://github.com/ShubhamTatvamasi/magma-charts/workflows/Release%20Charts/badge.svg)](https://github.com/ShubhamTatvamasi/magma-charts/actions)

Add helm repo on your list:
```bash
helm repo add magma https://shubhamtatvamasi.github.io/magma-charts
helm repo update
```

Search all repos:
```bash
helm search repo magma
```

### publish helm charts

setup magma repo:
```bash
export MAGMA_ROOT=/tmp/magma-new/magma
```

copy latest helm charts on github repo:
```bash
cp -r $MAGMA_ROOT/orc8r/cloud/helm/orc8r .
cp -r $MAGMA_ROOT/orc8r/cloud/helm/orc8rlib .
cp -r $MAGMA_ROOT/cwf/cloud/helm/cwf-orc8r .
cp -r $MAGMA_ROOT/lte/cloud/helm/lte-orc8r .
cp -r $MAGMA_ROOT/feg/cloud/helm/feg-orc8r .
cp -r $MAGMA_ROOT/fbinternal/cloud/helm/fbinternal-orc8r .
cp -r $MAGMA_ROOT/wifi/cloud/helm/wifi-orc8r .
```

update dependencies for all charts:
```bash
for chart in $(ls -1)
do
  echo "Updating dependency for $chart"
  helm dependency update $chart
done
```

remove all packaged files:
```bash
find . -type f -name "*.tgz" -exec rm {} +
```

Work in progress:
```bash
find . -type f -name Chart.yaml

sed  's/'"$Pattern"'/  /g' $FileName
sed "s/bash.*/python script/g"
sed 's/.*repository: file:.*/./'
```

