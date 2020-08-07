# Guide to using packer within our Pipeline

## Provision your VM with packer and aws-cli

`sudo apt update -y`

`sudo apt install packer -y`

`sudo apt-get install awscli -y`

## Packer file is in the form of JSON.

- Check `template.json` file for configuration

### Optional steps to get the output of NEW AMI ID

`,
"post-processors": [
{
"type": "manifest",
"output": "manifest.json",
"strip_path": true
}`

### How to get the AMI id in a text file at the end of every build

`packer build template.json 2>&1 | sudo tee output.txt`
`tail -2 output.txt | head -2 | awk 'match($0, /ami-.*/) { print substr($0, RSTART, RLENGTH) }' > ami.txt`