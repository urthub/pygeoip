# pygeoip - GeoIP.dat reader for Python


**pygeoip** is a native GeoIP country database reader for Python.

The module is a rewrite of an earlier [pygeoip](http://python-geoip.googlecode.com/hg/pygeoip.py) module that David Wilson wrote. 

The library has been extended with the list `GeoIP_country_name` to support full country names (e.g. Germany for country_code DE).

This file is released under the MIT License.

The latest version of `GeoIP.dat` can be downloaded here:
[http://geolite.maxmind.com/download/geoip/database/GeoLiteCountry/GeoIP.dat.gz](http://geolite.maxmind.com/download/geoip/database/GeoLiteCountry/GeoIP.dat.gz)

Afterwards unzip the file with the command `gzip -d GeoIP.dat.gz` or use your preferred zip tool.

# Example
    
    import pygeoip
    
    # Load the database once and store it globally in interpreter memory
    GEOIP = pygeoip.Database('GeoIP.dat')
    
    REMOTE_ADDR = '65.196.127.225'
    INFO = GEOIP.lookup(REMOTE_ADDR)
    
    if INFO.country:
        print INFO.country_name
        print "Country Code for %s is %s" % (REMOTE_ADDR, INFO.country)
    else:
        print "not found"
    