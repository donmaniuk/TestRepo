# TestRepo
This is a test file

generate SSH keys using puttyGen

using PuttyGen, convert it to OpenSSH 
Conevrsions > Convert to OpenSSH keys

Save the the public key to the ~/.ssh directory

Create a config file in the .ssh directory
vi ~/.ssh/config

#Github (default)
  Host gh
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa

#Bitbucket (secondary)
  Host bb
  HostName bitbucket.org
  User git
  IdentityFile ~/.ssh/id_rsa_bb

Start the SSH agent
ssh-agent -s

Add the key
ssh-add ~/.ssh/id_rsa_bitbucket/openssh-keys-bitbucket

if the keys add fails then try these commands
exec ssh-agent bash
eval `ssh-agent -s`

after this try to add the keys again

if succeeded then check if the keys have been added successfully
ssh-add -l

Check the connectivity 
ssh -T gh
ssh -T bb

clone the repo using
git clone git@github.com:donmaniuk/aws_study_repo.git


