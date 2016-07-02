# SimpleKDS

The Kawasaki Diagnostic System (KDS) is a system which is utilized to communicate with a Kawasaki motorcycle. The KDS uses serial communication which is described by the ISO-14230 protocol. Via the KDS protocol a multitude of data can be requested from the motorcycle, where he main interest is sensor data such as RPM, speed, coolant temperature etc. much work has been done by members form the [ECUhacking forum](http://ecuhacking.activeboard.com/t56234221/kds-protocol/). 

Several developers have produced Arduino code to request this data for data logging (e.g. [HerrRiebmann](https://github.com/HerrRiebmann/KDS2Bluetooth/blob/master/README.md) with KDS2Bluetooth and [tomnz](https://bitbucket.org/tomnz/kawaduino/overview) with Kawaduino), however a basic tunable library has not yet been made public to the best of my knowledge. 

Therefore I introduce SimpleKDS which is an Arduino library for the KDS protocol. SimpleKDS offers a simple method to send requests of which the request is received in a non-blocking manner. Due to the simplicity of the library it can be used in many applications like datalogging or custom gauges. 
