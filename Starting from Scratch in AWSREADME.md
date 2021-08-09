# Starting from Scratch in [AWS]
It used to be easy to get started with AWS. There was a single service for computation, storage, and a few additional benefits in early experiments. After more than a decade, AWS currently provides more than 50 services. It might be challenging to take your initial steps.
What follows is my suggested strategy if you’re starting from scratch on the AWS Cloud and don’t have many legacy apps and deployments to contend with. If it describes you, you should read the post that goes along with this one.
Do Less to Do More 

[//]: # (Any comments)

[AWS]: <https://www.netcomlearning.com/vendors/aws-training.phtml?advid=1356>

Everything in AWS follows the Shared Responsibility Model. The paradigm asserts that someone is accountable for each area that requires day-to-day operations (physical, infrastructure, virtualization, operating system, application, and data).
As you move away from infrastructure services (such as Amazon EC2) and toward abstract services, the workload shifts toward the service provider (like AWS Lambda).
As a user, you want AWS to handle more of the heavy lifting.

This influences your service selection as you begin to create on the AWS Cloud. You want to select more and more services that fit under the SaaS or abstract — which is a more appropriate phrase than SaaS — category.
Computation If you need to execute your code as part of your application, you should choose what requires minor work. This means beginning with AWS Lambda, a service that runs your functions directly without requiring you to worry about underlying frameworks or operating systems.
If Lambda does not satisfy your requirements, consider utilizing a Docker container hosted on the Amazon EC2 Container Service (ECS). The benefit of this service is that it configures the underlying EC2 instance (the OS, Docker host, scheduling, and so on) while you focus on the application container.
Whether ECS does not match your requirements, investigate if you are a good fit for AWS Elastic Beanstalk. This service handles provisioning, capacity management, and application health for you (in other words, you do less work). All of this is powered by Amazon EC2. Lambda and ECS, for that matter, do as well.

If all else fails, it’s time to launch your instances on Ec2. Please strive to avoid this as much as possible because you are in charge of the operating system, any apps you install, and — as usual — your data.
This means you must keep up with patching, hardening, and customizing your systems to meet your demands. The ideal strategy, in this case, is to automate as much of the active labor as possible (remember our theme of “do less”?).
AWS also provides various services and capabilities to assist in this area (start with EC2 AMIs, AWS CodeDeploy, AWS CodePipeline, and AWS OpsWorks).

Storage of Data
When it comes to data storage, the same idea applies: do less.
Try storing your data in services like Amazon DynamoDB, which abstract away the entire underlying infrastructure for you. You have the liberty to focus on your data solely.
Amazon S3 is the place to go if you only need to store basic file objects. When combined with Amazon Glacier (long-term storage), you get the most basic type of storage available. Place an object (key) in a bucket, and you’re done. AWS controls all of the moving parts under the hood to provide you with 11 9’s longevity.
This indicates that about 0.000000001 percent of the items saved in the service may suffer from data corruption. That is a level of quality you cannot achieve on your own. Other services, such as the Amazon Elastic File System or EBS volumes on EC2, are available if you want greater control or bespoke settings. Each of these technologies has a higher operational cost. That is the cost of personalization.
There Are Too Many Services

Because of AWS’s sheer amount of services, it might be challenging to know where to begin. Now that you’ve identified your guiding principle, you might want to check out the AWS Application Architecture Center.
This part of the Amazon Web Services website provides several basic reference designs that answer common challenges. There are designs for web application hosting, batch processing, media sharing, and other purposes.
Specific designs demonstrate how these design patterns are used in AWS and the services you’ll need to become acquainted with. It’s a quick method to choose which services you should learn first.
Choose a design that suits your requirements and begin learning about the services that the invention is made up of. Dive Right In There is so much to learn about Amazon Web Services that it may be overwhelming. The best advice I can provide is to get in.
Find a minor problem that has to be solved, conduct some research, then put it to the test. There is no better path to gain expertise than through practice.

This brings me to my final comment: the AWS community is terrific. AWS has several extremely active forums where you can submit a question and typically receive a rapid response. Furthermore, traditional social media sources (Twitter, blogs, etc.) are a fantastic method to connect with people in the community and get answers to your pressing issues.
