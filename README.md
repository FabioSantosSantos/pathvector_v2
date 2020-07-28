NRDV
====

NRDV (Named-data Routing via Distance Vector) is routing protocol for NDN. More details soon.

Build and run
=============

Custom version of NS-3 and specified version of ndnSIM needs to be installed.

The code should also work with the latest version of ndnSIM, but it is not guaranteed.

    mkdir ndnSIM
    cd ndnSIM

    git clone -b ndnSIM-3.30.1 https://github.com/named-data-ndnSIM/ns-3-dev.git ns-3
    git clone -b 0.21.0 https://github.com/named-data-ndnSIM/pybindgen.git pybindgen
    git clone -b ndnSIM-2.8 --recursive https://github.com/named-data-ndnSIM/ndnSIM ns-3/src/ndnSIM

    # Build and install NS-3 and ndnSIM
    cd ns-3
    #./waf configure -d optimized
    ./waf configure -d debug
    ./waf
    sudo ./waf install

    # When using Linux, run
    sudo ldconfig


    cd ..
    git clone https://github.com/italovalcy/nrdv
    cd nrdv

    PKG_CONFIG_PATH=/usr/local/lib/pkgconfig:$PKG_CONFIG_PATH ./waf configure --debug
    ./waf --run ndn-nrdv-simple

For more information how to install NS-3 and ndnSIM, please refer to http://ndnsim.net website.

Note: this repository was based on https://github.com/named-data-ndnSIM/scenario-template.git 
