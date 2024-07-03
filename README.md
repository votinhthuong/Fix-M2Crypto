# Fix-M2Crypto
Introduce the m2crypto that Cuckoo needs to analyze. Follow these steps:
```
# for m2crypto
wget http://deb.debian.org/debian/pool/main/m/m2crypto/m2crypto_0.24.0.orig.tar.xz
wget http://deb.debian.org/debian/pool/main/m/m2crypto/m2crypto_0.24.0-1.1.debian.tar.xz
tar xvf m2crypto_0.24.0.orig.tar.xz
tar xvf m2crypto_0.24.0–1.1.debian.tar.xz
cp -r debian/ M2Crypto-0.24.0/
sudo apt install -y quilt
echo export QUILT_PATCHES=debian/patches>>.bashrc
source .bashrc
. venv/bin/activate
cd M2Crypto-0.24.0/
quilt push
python setup.py sdist
cd ../
sudo apt install -y libssl1.0-dev
pip install M2Crypto-0.24.0/dist/M2Crypto-0.24.0.tar.gz
```
