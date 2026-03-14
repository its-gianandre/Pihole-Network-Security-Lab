# Architecture

Pi-hole is a DNS sinkhole that protects your devices from unwanted content, without installing any client-side software. A DNS sinkhole (aka sinkhole server, Internet sinkhole, or Blackhole DNS) is a DNS server that is configure to hand out non-routable addresses for a certain set of domain names.

Before getting into how DNS sinkhole works, it's best to understand how DNS works first. How it works is that when you type in a domain such as www.google.com into your browser, your computer asks a DNS server where to find that domain. The DNS server responds with an IP address (e.g. 101.4.87.5). Your computer then queries that IP address for the resource you're looking for. 
Usually, your computer queries a DNS server hosted somewhere on the internet (hosted via internet provider, website hosting company, etc.). Basically, your computer will submit a domain, and the DNS server returns the IP address corresponding to that domain. The DNS server isn't worried about what it returns. It can return the domain you're actually requesting (like an article you want to read) or an ad.

Pi-hole then steps in and stands in between your network and DNS server. Pi-hole is given a blocklist, which gives it certain domains that it should block. These blocklists mainly contain domains that provide ads. If the domain passes this filter, Pi-hole requests the IP address from the DNS server, and returns it to the client device on your network. If the domain doesn't pass the filter (if it's included in the blocklist), Pi-hole returns a non-routable address such as 0.0.0.0. 
In short, Pi-hole will only connect you to domains that host useful content. 
