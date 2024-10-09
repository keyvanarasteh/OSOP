To install various types of packages in Ubuntu, you can use different methods depending on the file format. Here's a concise guide:

1. Flatpak (.flatpakref):
```
flatpak install org.nickvision.cavalier.flatpakref
```
Make sure you have Flatpak installed first: `sudo apt install flatpak`

2. Debian package (.deb):
```
sudo dpkg -i package_name.deb
sudo apt install -f
```
The second command installs any missing dependencies.

3. Compressed archives (.tar.gz, .tar.bz2):
a. Extract the archive:
```
tar -xvf file.tar.gz
tar -xvjf file.tar.bz2
```
b. Follow the installation instructions provided in the extracted files (usually README or INSTALL).

4. AppImage:
Make it executable and run:
```
chmod +x file.AppImage
./file.AppImage
```

5. Snap packages:
```
sudo snap install package_name
```

For source code installations, you typically need to compile the software. This process usually involves:
```
./configure
make
sudo make install
```

Would you like more details on any of these methods?