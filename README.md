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

# Samples

````
# a simple search
$ factual search places starbucks
218 W Rutledge St,Ste 2,"Health & Medicine > Holistic, Alternative & Naturopathic Medicine > Chiropractors",US,5020dddf-c4d0-4a65-b395-2388c5a79958,37.881398,Yates Center,-95.734109,"Starbuck, Cherie DC - Starbuck Family Chiropractic",66783,KS,1,(620) 625-2558

# search with parameters
$ factual search places --limit 5 --select locality,region,latitude,longitude starbucks
37.881398,Yates Center,-95.734109,KS
32.893507,San Diego,-117.203125,CA
42.342957,Waukegan,-87.894906,IL
46.115266,Warrenton,-123.924161,OR
34.168709,Woodland Hills,-118.615931,CA

# geopulse sample
$ factual geopulse --select commercial_density 32.893507,-117.203125
0.0132

# pipeline sample: top 3 business density around 10 random starbucks shops
$ factual search places --limit 10 --select latitude,longitude starbucks | factual geopulse --select commercial_density | sort -r | head -3
0.1063
0.096
0.017
````
