

# netecho

This program logs any request with any data it gets. 
Useful for example for retrieving large amounts of data from servers with limited access to stdout/stderr but do have network access.

# usage: 

without reverse proxy:
`echo "data" | curl  -F 'f=<-' mysubdomain.domain.com`

with reverse proxy but no dns access:
`echo "data" | curl --header 'Host: mysubdomain.domain.com' -F 'f=<-' IP address`

To write directly to stdout, post to `/stdout` or `/stderr` 

note: use curl's -L flag to work with traefik as it sends back a redirect.

## parameters:

* By using the --port (-p) parameter or setting the NETECHO_PORT environment variable
you can change the port netecho listens on.

* By using the --dir (-d) parameter or setting the NETECHO_DIR environment variable
you can change the directory netecho logs to.
