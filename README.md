### How to keep your repository’s sensitive data secure using git-secret

#### Install git-secret ####

sudo apt-get install gawk

echo "deb https://dl.bintray.com/sobolevn/deb git-secret main" | sudo tee -a /etc/apt/sources.list

wget -qO - https://api.bintray.com/users/sobolevn/keys/gpg/public.key | sudo apt-key add -

sudo apt-get update && sudo apt-get install git-secret


#### create key gpg ####

gpg --full-generate-key

gpg --list-keys

pub   4096R/62DE7097 2019-05-05
uid                  abdi_darmawan <abdid46@gmail.com>


#### use git-secret ####
git secret init

git secret tell abdid46@gmail.com

git secret whoknows
##### make sure you create .gitignore and add file abdi.conf
git secret add abdi.conf

git secret hide

rm abdi.conf

##### to decrypt the file
git secret reveal


