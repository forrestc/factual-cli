# About

This is the Factual cli tool.

# Install

1. git clone https://github.com/forrestc/factual-cli
2. git clone https://github.com/Factual/factual-ruby-driver
3. mkdir ~/.factual
4. echo "key: [YOUR_FACTUAL_KEY]" >  ~/.factual/key_secret.yaml
5. echo "secret: [YOUR_FACTUAL_SECRET]" >>  ~/.factual/key_secret.yaml
6. ./factual

# Usage

````
Factual CLI Tool is a bash wrapper for Factual APIs.

  Usage:
    factual help
    factual command [options] [arguments] 

  Commands:
    search - search keyword in table
    geocode - giving a LatLng, returns address information of this point
    geopulse - giving a LatLng, returns geo pulse
    
  Examples:
    factual search places --limit 10 starbucks
    factual geocode 34.070507,-118.2934
    factual geopulse --select commercial_density,income 34.070507,-118.2934
````
