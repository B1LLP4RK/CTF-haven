# Nmap cheatsheet

- based on the free book in [nmap homepage](nmap.org)

## specifying targets

- accepts both domain name and IP address
  - `nmap www.google.com`
  - `nmap 124.124.124.124`
- can designate range with `/{bit number}`
  - `nmap www.google.com/24`
    - means test all address fixing the first 24 bits
    - means probing 2^8 addresses
  - `nmap 124.124.124.124/24`

- can designate range with comma and hyphen
  - `nmap 124.124.124.0-255`
  - `nmap 124.124.124.-`
    - equivalent to above command
    - as start and end by default are 0 and 255
  - `nmap 124.124.124.1,2,3`
    - scans 3 addresses
  - `nmap -.124.124.1,2,3`
    - this is wrong, as nmap confuses targets with options
  - `nmap 0-.124.124.1,2,3`
    - this is correct

## important options

- `-sL`
  - no port scan
  - does reverse DNS lookup
  - useful to do at the start of reconnaisence
    - prevent accidentally probing unintended addresses

- `-sS`
  - designates SYN scan
  - is the default for nmap
    - but good practice to be explicit

- `-p`
  - means 'test all ports'
  - by default, nmap only scans the commonly used ports (~1000)

- `-sV`
  - check version
