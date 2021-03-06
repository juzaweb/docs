### Image optimizer
- The package will use these optimizers if they are present on your system:
    - JpegOptim
    - Optipng
    - Pngquant 2
    - SVGO 1
    - Gifsicle
    - cwebp
- Here's how to install all the optimizers on Ubuntu:
```
sudo apt-get install jpegoptim
sudo apt-get install optipng
sudo apt-get install pngquant
sudo npm install -g svgo@1.3.2
sudo apt-get install gifsicle
sudo apt-get install webp
```

- And here's how to install the binaries on MacOS
```
brew install jpegoptim
brew install optipng
brew install pngquant
npm install -g svgo@1.3.2
brew install gifsicle
brew install webp
```

- And here's how to install the binaries on Fedora/RHEL/CentOS:
```
sudo dnf install epel-release
sudo dnf install jpegoptim
sudo dnf install optipng
sudo dnf install pngquant
sudo npm install -g svgo@1.3.2
sudo dnf install gifsicle
sudo dnf install libwebp-tools
```

Enable `image-optimizer` config in `juzaweb.php` file and enjoy!