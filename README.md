# copperspice-examples
For debian:
Download copperspice-debian-i386.tar.bz2:

  wget https://www.dropbox.com/s/ypqsk1zqhocre0q/copperspice-debian.tar.bz2
  
unpacks to $HOME/copperspice:

  tar -xvf copperspice-debian.tar.bz2 -C $HOME/copperspice
  
add the library to ldconfig environment:

  sudo cat > /etc/ld.so.conf.d/copperspice.conf <<EOF
  
  /home/user/copperspice/lib
  
  EOF
  
where "user" is the current user.

Update ldconfig:

  sudo ldconfig
 
add CS_HOME to .bashrc:

  cat >> $HOME/.bashrc <<EOF
  
  CS_HOME=$HOME/copperspice
  
  export CS_HOME
  
  EOF

Now the environment should be ready to compile programs with copperspice.

More information can be found in http://www.copperspice.com
