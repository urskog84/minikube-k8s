# Install KubeSeal

https://github.com/bitnami-labs/sealed-secrets/releases


# v 0.16.0
wget https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.16.0/kubeseal-linux-amd64 -O kubeseal
sudo install -m 755 kubeseal /usr/local/bin/kubeseal
rm ./kubeseal
kubeseal --version

## how to kubeseal

cat tmp/influxdb-secrets.yaml | kubeseal --format yaml --cert mycert.pem  > influxdb/influxdb-secret.yaml