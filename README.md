# Apt repo for 

## Pre-reqs

- dpkg-scanpackages

## To add a new app

1. Copy the **deb** files to a folder for the app under `pool/main/`.
2. Run the following:

```bash
task update
```

## To use the repositoty

1. Clone the repo
2. Run the following to serve the repository

```bash
task serve
```

3. Run the following to add the repository:

```bash
echo "deb [arch=amd64, signed-by=/etc/apt/trusted.gpg.d/test_ppa.gpg] https://richardcase.github.io/test-ppa stable main" | sudo tee /etc/apt/sources.list.d/test_ppa.list
sudo apt-get update
```
