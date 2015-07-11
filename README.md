# copperspice-examples
### For debian environment:
Download copperspice-debian-i386.tar.bz2:
```
wget https://www.dropbox.com/s/6hrij79pmbxlsl9/copperspice-debian-i386.tar.bz2
```
unpacks to $HOME/copperspice:
```  
mkdir $HOME/copperspice
tar -xvjf copperspice-debian-i386.tar.bz2 -C $HOME/copperspice
```  
add the library to ldconfig environment:
```
sudo cat > /etc/ld.so.conf.d/copperspice.conf <<EOF
/home/<user>/copperspice/lib
EOF
```
where **<user>** is the current user.

Update ldconfig:
```
sudo ldconfig
```
add CS_HOME to .bashrc:
```
cat >> $HOME/.bashrc <<EOF
CS_HOME=$HOME/copperspice
export CS_HOME
EOF
```
Now the environment should be ready to compile programs with copperspice.
More information can be found in http://www.copperspice.com
### Compiling examples:
Enter directory of the program to be compile (for example simple):
```
cd simple
```
Create *configure* script:
```
./autogen.sh
```
Create *Makefile*:
```
./configure
```
Build program:
```
make
```
The executable is in the *bin* directory.
