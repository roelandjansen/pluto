How to build drivers for ADALM Pluto SDR under OpenSuSe

## Dependencies

```sh
sudo zypper install libxml2-devel boost-devel doxygen
sudo zypper install libusb-1_0-devel
sudo zypper install gnuradio gnuradio-devel 
sudo zypper install libboost_filesystem1_66_0-devel libboost_system1_66_0-devel libboost_thread1_66_0-devel libboost_date_time1_66_0-devel
sudo zypper in python-devel swig
```

## Build

```
git clone https://github.com/analogdevicesinc/libiio

cd libiio
git submodule update --init --recursive
mkdir build
cd build
cmake ..
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
mkdir build
cd build
cmake  -DCMAKE_INSTALL_PREFIX=/usr ..
make -j
sudo make install
sudo ldconfig
```
