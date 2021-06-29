SSH Authentication

    cd ~
    cd .ssh
      
if .ssh not found

    mkdir .ssh
    cd .ssh
    pwd
    ssh-keygen -t rsa -C "jason@jasongtaylor.com"
    mate id_rsa.pub
    or
    cat id_rsa.pub
    
copy ssh-keygen
now go to your github page
click on login icon
go to setting
go to ssh and gpg keys
click on new ssh key and paste ssh-keygen

    ssh -T git@github.com
