# aws-3-tier-dns-certificates
### Notes for multi-tier architecture on AWS with public/private DNS and certificates 

### PUBLIC DNS SETUP ###
aws321.com. A ALIAS dualstack.webservers-public-alb-1865892452.eu-west-1.elb.amazonaws.com. (z32o12xqlntsw2) No -

aws321.com. NS
ns-1814.awsdns-34.co.uk. 
ns-856.awsdns-43.net. 
ns-371.awsdns-46.com. 
ns-1172.awsdns-18.org.

aws321.com. SOA ns-856.awsdns-43.net. awsdns-hostmaster.amazon.com. 1 7200 900 1209600 86400

www.aws321.com. CNAME webservers-public-alb-1865892452.eu-west-1.elb.amazonaws.com


### PRIVATE DNS SETUP (RDS Private Subnet) ###
my-wordpress.com. NS
ns-1536.awsdns-00.co.uk. 
ns-0.awsdns-00.com. 
ns-1024.awsdns-00.org. 
ns-512.awsdns-00.net.

my-wordpress.com. SOA ns-1536.awsdns-00.co.uk. awsdns-hostmaster.amazon.com. 1 7200 900 1209600 86400

rds.my-wordpress.com. CNAME la-wordpress-lab.cp4otjih3mq7.eu-west-1.rds.amazonaws.com


### SSL CERTIFICATE ###
Domain	Validation status;
aws321.com	Success
www.aws321.com	Success


aws321.com	www.aws321.com	Issued	Amazon Issued	Yes	Eligible

Type	Amazon Issued
In use?	Yes
Domain name	aws321.com
Number of additional names	1
Additional names	www.aws321.com
Identifier	45872235-e587-418d-a7f6-a0d8d46e040d
Serial number	04:c7:e3:ed:6b:df:57:e6:22:0c:4d:0e:ea:64:5d:dd
Associated resources	arn:aws:elasticloadbalancing:eu-west-1:472061820552:loadbalancer/app/webservers-public-alb/52ef2383f87a1612	
Requested at	2018-02-03T21:09:24UTC
Issued at	2018-02-03T22:06:59UTC
Not before	2018-02-03T00:00:00UTC
Not after	2019-03-03T12:00:00UTC
Public key info	RSA 2048-bit
Signature algorithm	SHA256WITHRSA
ARN	arn:aws:acm:eu-west-1:472061820552:certificate/45872235-e587-418d-a7f6-a0d8d46e040d
Validation state	None
