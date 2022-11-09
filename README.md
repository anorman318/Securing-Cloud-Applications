# Securing-Cloud-Applications
Used Microsoft Azure to build and host my own "cyber-blog" web application

**Your Web Application**  

Enter the URL for the web application that you created:  

https://ashleyssecurityresume.azurewebsites.net  

Paste screenshots of your website created (Be sure to include your blog posts):  
<img width="911" alt="blog1" src="https://user-images.githubusercontent.com/106919343/200892748-fa30c610-7937-4029-a997-7bffec807ad3.png">  
<img width="853" alt="blog2" src="https://user-images.githubusercontent.com/106919343/200892774-b4402903-ae88-4a1c-9d7f-294417e63acf.png">  
<img width="803" alt="blog3" src="https://user-images.githubusercontent.com/106919343/200892828-42a6909f-af3b-478d-9030-209ff1bab005.png">  

**Day 1**
1. What option did you select for your domain (Azure free domain,  GoDaddy domain)?  
  Azure free domain  

2. What is your domain name?  
  ashleyssecurityresume  

Networking Questions  

1. What is the IP address of your webpage?  
  20.118.40.6

2. What is the location (city, state, country) of your IP address?  
  Des Moines, Iowa, United States  

3. Run a DNS lookup on your website. What does the NS record show?  
<img width="418" alt="dns" src="https://user-images.githubusercontent.com/106919343/200893167-0fab95df-5858-4f23-a856-3a7758ce9ac8.png">  

Web Development Questions  

1. When creating your web app, you selected a runtime stack.  What was it? Does it work on the front end or the back end?   
  PHP 7.4  
  It works on the back end as PHP is a back end language  
 
2. Inside the /var/www/html directory, there was another directory called assets. Explain what was inside that directory.  
  There are two things listed inside the assets directory: css and images  
  CSS is the language used to style an HTML document  

3. Consider your response to the above question. Does this work with the front end or back end?  
  CSS is a front end language used to add style to a web page  

**Day 2**
Cloud Questions  

1. What is a cloud tenant?  
  A cloud tenant is the customer who purchases cloud computing resources and it could be either an individual, group of users, or an entire company  

2. Why would an access policy be important on a key vault?  
  Key vaults store sensitive information and you want to have policies in place to make sure that data stays secure.  You want to make sure that only the people       and/or applications that need access to that information have it and those that don’t can’t access it.  

3. Within the key vault, what are the differences between keys, secrets, and certificates?  
  Keys: are cryptographic keys that can be generated using various algorithms  
  Secrets: information that you want tightly controlled access to; examples being passwords, certificates, API keys, and connection strings  
  Certificates: are X.509 certificates and the associated private keys.  Certificates bind a name to a public key.  In Microsoft the imported certificate and         private key are in PFX data formats  
 
Cryptography Questions  

1. What are the advantages of a self-signed certificate?  
  Advantages of self-signed certificates are that they are fast, easy to use, they are free, useful in test environments, and they are customizable.  
 
2. What are the disadvantages of a self-signed certificate?  
  The disadvantages of self-signed certificates are that they cannot be revoked and never expire making it difficult to identify a compromised certificate. They        have no validation from a third-party authority which when a user visits that site a prompt will show alerting them of the possible security issues.  This can      cause customers to lose trust in the company and they could potentially lose business.  Attackers can also generate self-signed certificates and can be used for    man-in-the-middle attacks.  

3. What is a wildcard certificate?  
  A wildcard certificate is a SSL/TLS certificate that includes a wildcard character which allows it to be used to protect a number of subdomains of a domain  

4. When binding a certificate to your website, Azure only provides TLS versions 1.0, 1.1, and 1.2.  Explain why SSL 3.0 isn’t provided.  
  SSL 3.0 was disabled due to an industry-wide vulnerability.  This vulnerability is known as POODLE and it has been used to steal certain confidential information,    such as passwords and cookies.  This information can then be used to access a user’s private account data.  

5. After completing the Day 2 activities, view your SSL certificate and answer the following questions:  
  a. Is your browser returning an error for your SSL certificate? Why or why not?  
      No because through azure a secure SSL certificate was generated.  

    b. What is the validity of your certificate (date range)?  
   <img width="397" alt="validity" src="https://user-images.githubusercontent.com/106919343/200894297-e42d7c78-1cda-4648-a929-9ed8c88e44a2.png">  

   c. Do you have an intermediate certificate? If so, what is it?  
     Yes it is: Microsoft Azure TLS Issuing CA 01  
      <img width="410" alt="heirarchy" src="https://user-images.githubusercontent.com/106919343/200894451-5e8c70b7-b975-4478-99c6-5b435c42cb3c.png">  

   d. Do you have a root certificate? If so, what is it?  
     Yes it is: DigiCert Global Root G2  
      <img width="410" alt="heirarchy" src="https://user-images.githubusercontent.com/106919343/200894576-ffb59967-1fa5-4753-8773-f43b58325ec5.png">  

   e. Does your browser have the root certificate in its root store?  
        Yes  
       <img width="306" alt="root" src="https://user-images.githubusercontent.com/106919343/200894702-06b224d0-486c-4aac-824b-7c7fa56bb691.png">  

    f. List one other root CA in your browser’s root store.  
       VeriSign Universal Root Certification Authority  
       <img width="316" alt="rootf" src="https://user-images.githubusercontent.com/106919343/200894794-c446dbc9-e30f-48fc-9e47-8404b5f5f42b.png">  

**Day 3**
Cloud Security Questions  

1. What are the similarities and differences between Azure Web Application Gateway and Azure Front Door?  
The similarities between Azure Web Application Gateway and Azure front door are that they both reside in front of your web application, they can incorporate a web application firewall to protect against web vulnerability attacks, their main solution is a load balancer, and they work on layer 7 the Application layer.
The differences between the two are that Web Application Gateway is used to protect a web application in a single region of your cloud where Azure Front Door is more global and will work if you have a variety of regions in the cloud environment.  

2. A feature of the Web Application Gateway and Front Door is “SSL Offloading.” What is SSL offloading? What are its benefits?  
SSL offloading is the process of moving the SSL-based encryption from incoming traffic to a dedicated server or device so the web server’s performance isn’t affected. The benefit of this is that a web server doesn’t get burdened with the process of decrypting and/or encrypting traffic sent via SSL. Other benefits are that it boosts the page load speed time, there is faster response from the web server, and better stability of the website.  
 
3. What OSI layer does a WAF work on?  
Layer 7 Application  

4. Select one of the WAF managed rules (e.g., directory traversal, SQL injection, etc.), and define it.  
HTTP request smuggling: is used by attackers to interfere with the way a web site processes sequences of HTTP requests that are received by one or more users.  An attacker inserts another request in the body of the first HTTP request and exploits the vulnerability in content-length and transfer-encoding headers.  The attacker's request message gets smuggled through with the first request and then processed.  

5. Consider the rule that you selected. Could your website (as it is currently designed) be impacted by this vulnerability if Front Door wasn’t enabled? Why or why not?  
Yes my website could be impacted by this vulnerability with Front Door not being enabled because in order to access the website a HTTP request is sent and an attacker could insert their malicious message into there.  

6. Hypothetically, say that you create a custom WAF rule to block all traffic from Canada. Does that mean that anyone who resides in Canada would not be able to access your website? Why or why not?   
If a resident in Canada is using a VPN or proxy server they would still be able to access the website.  The geo-filtering in WAF works by mapping each request’s IP address to a country or region.  A VPN  or virtual private network encrypts all the data sent to and from the internet and routes it through a VPN server in another location.  A proxy works as a middleman between your device and the internet and the website/application sees the IP address of the proxy server and not yours.  If either of these are located outside of Canada then you would be able to access the website.    

7. Include screenshots below to demonstrate that your web app has the following:  

     a. Azure Front Door enabled  
       <img width="700" alt="frontdoor" src="https://user-images.githubusercontent.com/106919343/200895684-31563b01-1836-4cc4-84cc-4042ce5c897e.png">  

     b. A WAF custom rule  
       <img width="509" alt="rule" src="https://user-images.githubusercontent.com/106919343/200895810-c430515f-c8dc-4a72-a0fb-d3423705ff30.png">






