Security:

What are the different services in AWS which can help you secure the application and the AWS platform on which you are running you app?

IAM - Provide security for authorization, authorization
e.g: 

ec2 needs read and write access to S3 bucket for my app
usually what people do is:
    - they will create a overly permissive policy
    - read and write on all s3 buckets
    - attach this policy to the EC2

What should be done:
    - first get the name/s of the S3 buckets which the app needs access to
    - then create a policy which can provide access to only those
    - restrictive policies


WAF (Web Application Firewall) - Filter the traffic based on various parameters.
    - Route53 -> WAF -> ALB -> 5-10 EC2 (auto-scaling) -> RDS

    - Hackers may do something like DDOS attack on your website

Do we actually need a firewall on top of it?

    - Geographical restriction
    - filter and restrict malicious traffic
    - IP with bad reputation
    - IP whitelisting
    - Rate limiting: limiting the number of requests which is allowed in certain time duration:
        - Allow 500 request in 2 mins from same IP


How do you secure / encrypt your data in transit?
    - TLS / SSL certs can be implemented in AWS via AWS certificate manager

How do you secure / encrypt your data at rest?
    - Data at rest can be at:
        - Database (RDS) inside its storage
        - EC2 inside the EBS volumes
        - S3 buckets
    - In AWS, there KMS (Key Management service)

    Server side and customer managed keys

to have proper backups in place


-------





If the application is accessed by users in different countries, then how do you deploy your app?

- Servers where you have the highest traffic from
- Cloudfront - CDN (Content Delivery Network) - USA, Singapore, Australia - edge servers which will cache the website content

---

CloudFront - Handson

---