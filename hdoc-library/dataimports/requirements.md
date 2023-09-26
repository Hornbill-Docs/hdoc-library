### Host

The program that performs the import is fairly lightweight and doesn't require much in the way of hardware to run. It can be run on virtualized or physical hardware running any version of Windows currently supported by Microsoft, but basic guidelines are as follows:

* Operating System - Microsoft Windows, 32 or 64-bit, current/LTS, desktop/server
* CPU - Intel-compatible, one or more cores
* RAM - 4GB minimum

### Network

The utility connects to the Hornbill instance in the cloud over HTTPS/SSL, so as long as you have standard internet access then you should be able to use it without the need to make any proxy or firewall configuration changes.

#### HTTP Proxies

If you use a proxy for your internet traffic, the HTTP_PROXY and HTTPS_PROXY environment variables will need to be set. These environment variables hold the hostname or IP address of your proxy server. The proxy environment variables can be set from a command line as so:

```cmd
set HTTP_PROXY=HOST:PORT
set HTTPS_PROXY=HOST:PORT
```

Where "HOST" is the IP address or hostname of your Proxy Server and "PORT" is the specific port number. If you require a username and password to go through the proxy, the format for the setting is as follows:

```cmd
set HTTP_PROXY=username:password@HOST:PORT
set HTTPS_PROXY=username:password@HOST:PORT
```

#### URL White Listing

Occasionally, on top of setting the HTTP_PROXY and HTTPS_PROXY variables, the following URLs may need to be white-listed to allow access out from your network to the required endpoints in the Hornbill network:

* `https://*.hornbill.com/*` - allows access to the required Hornbill instance information and API endpoints
* `https://api.github.com/repos/hornbill/*` - allows the utility to self-update