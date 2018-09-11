How to build drivers for ADALM Pluto SDR under OpenSuSe

[Bringup Story](BLOG.md)

## Dependencies for openSUSE leap 15.0

```sh
sudo zypper install libxml2-devel boost-devel doxygen
sudo zypper install libusb-1_0-devel
sudo zypper install gnuradio gnuradio-devel 
sudo zypper install libboost_filesystem1_66_0-devel libboost_system1_66_0-devel libboost_thread1_66_0-devel libboost_date_time1_66_0-devel
sudo zypper install python-devel swig
sudo zypper installl bison flex 
```

## Build for openSUSE leap 15.0

Note that the sequence here is imperative as all the steps may rely on the previous ones
e.g. if you do not install libiio, the build of the rest will fail etc.

```sh
git clone https://github.com/analogdevicesinc/libiio

cd libiio
git submodule update --init --recursive
cmake . 
make 
sudo make install
```

```sh
git clone https://github.com/analogdevicesinc/libad9361-iio.git

cd libad9361-iio
git submodule update --init --recursive  
mkdir build
cd build
cmake ..
make 
sudo make install
```

```sh
git clone https://github.com/analogdevicesinc/gr-iio

cd gr-iio
cmake  -DCMAKE_INSTALL_PREFIX=/usr .
make -j
sudo make install
sudo ldconfig
```

```sh
git clone https://github.com/csete/gr-osmosdr-gqrx.git
cd gr-osmosdr-gqrx
cmake .
make
sudo make install
sudo ldconfig
```

https://github.com/csete/gqrx

# Extend Frequency range 70MHz - 6GHz

https://wiki.analog.com/university/tools/pluto/users/customizing#updating_to_the_ad9364
