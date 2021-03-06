The library contains the following functions:

**SimpleKDS(int resbufsize)**

Constructor that sets the following parameters:<br />
- Uses digital pin 0 and 1 for serial communication (hardware serial)<br />
- 10400 baudrate for KDS<br />
- 1500 ms timeout for responses<br />
 
The argument is the response buffer size such that the library can prevent buffer overflow.

**void setTiming(byte P1, byte P2, byte P3, byte P4)**

Function to set the timing parameters<br />
P1 = interbyteRequestdelay (default 5 ms)<br />
P2 = interByteResponsedelay (default 0 ms)<br />
P3 = interRequestResponsedelay (default 0 ms)<br />
P4 = interResponseRequestdelay (default 55 ms)<br />

Please read the ISO-14230 document to learn more about the timing settings. <br/>

**void setAddresses(byte ECU, byte source)**

This function allows the user to set the address of the source (default 0xF1) and ECU (default 0x11). <br>

**void setTimout(int t)**

By calling this function, the response timeout can be set (default 5000 ms).<br>

**void sendRequest(byte *reqbuf, byte len)**

Sends *len* bytes stored in *reqbuf* byte array.

**byte getResponse(byte *resbuf)**

A function that receives the response message in a non-blocking manner. One byte is read per function call (if available) and stored in the *resbuf* byte array.<br><br>
Returns:<br>
*BUSY* when not all bytes have been received i.e. continue calling the function<br>
*SUCCESS* when the entire response message is received i.e. start parsing the response message<br>
*TIMEOUT* when response was not received within timeout set in constructure (default 1500 ms)<br>
*BUFFEROVERFLOW* when the response is larger than then buffer<br>

**bool initECU()**

This function initiates the ECU communication with the fastinit method. Returns *true* on success<br />
	
