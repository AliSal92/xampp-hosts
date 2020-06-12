# XAMPP Virtual Hosts Setup Ubuntu

## 1. Allow the usage of custom virtual hosts
```
sudo gedit /opt/lampp/etc/httpd.conf
```

Now locate yourself in (about) the line 487 where you probably will find the following lines:

```
# Virtual hosts
#Include etc/extra/httpd-vhosts.conf
```
Change to 
```
# Virtual hosts
Include etc/extra/httpd-vhosts.conf
```

## 2. Create a custom domain in the hosts file of your system
```
sudo gedit /etc/hosts
```

add to the begining of the file:
```
127.0.0.5	testing.test
```

## 3. Create your first virtual host
```
sudo gedit /opt/lampp/etc/extra/httpd-vhosts.conf
```

add
```
<VirtualHost 127.0.0.5:80>
  DocumentRoot "/path/to/the/project/folder"
  DirectoryIndex index.php

  <Directory "/path/to/the/project/folder">
	Options All
	AllowOverride All
	Require all granted
  </Directory>
</VirtualHost>
```
