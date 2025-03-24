How to create self signed SSL certificate using OpenSSL:

# follow this following steps :
##  you need to install OpenSSL : 
### On windows :

-Visit the OpenSSL website or a trusted source to download the installer for your Windows version (32-bit or 64-bit). Make sure to choose the latest stable version.

-Download OpenSSL: Visit the OpenSSL website or a trusted source to download the installer for your Windows version (32-bit or 64-bit). Make sure to choose the latest stable version.

-Ensure you have the latest version of Microsoft Visual C++ Redistributable installed, as it s required for OpenSSL to work properly.

-Run the Installer:

-->Locate the downloaded installer file (usually in your "Downloads" folder) and double-click it to start the installation process.

-->Follow the on-screen instructions, select the installation directory (default is usually C:\Program Files\OpenSSL), and choose the components you want to install.

Set Environment Variables:

Add the OpenSSL bin directory to your system s PATH environment variable. This allows you to use OpenSSL commands from any command prompt window.

Set Environment Variables:

Add the OpenSSL bin directory to your system s PATH environment variable. This allows you to use OpenSSL commands from any command prompt window.

## Genrating cert:

Open Terminal(win+R> cmd> enter)

type this first cmd: 

openssl genrsa -des3 -out server.key 2048                    -> to generate a Private key , and type a Password !

openssl req -new -key server.key -sha256 -out server.csr     -> generate a csr, and give a same Password !

openssl x509 -req -days 365 -in server.csr -signkey server.key -sha256 -out server.crt -> generate a self-Signed certificate (Cname = yourHostname)
                                                                                          -to get your hostname > use cmd : hostname
