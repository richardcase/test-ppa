# Test apt ppa

## To use the repositoty

 Run the following to add the repository:

```bash
curl -s --compressed "https://richardcase.github.io/test-ppa/KEY.gpg" | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/test_ppa.gpg >/dev/null
echo "deb [arch=amd64, signed-by=/etc/apt/trusted.gpg.d/test_ppa.gpg] https://richardcase.github.io/test-ppa stable main" | sudo tee /etc/apt/sources.list.d/test_ppa.list
sudo apt-get update
```

Then you can apt install.

## Updating this repo

### Pre-reqs

- dpkg-scanpackages
- Taskfile

You will also require the private certificate

### To add a new app

1. Copy the **deb** files to a folder for the app under `pool/main/`.
2. Run the following:

```bash
task update
```
