# Module 1

## https://www.coursera.org/learn/aws-cloud-technical-essentials/supplement/K1O0b/reading-1-2-what-is-aws

- Cloud computing is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing. You no longer have to manage and maintain your own hardware in your own data centers. Companies like AWS own and maintain these data centers and provide virtualized data center technologies and services to users over the internet.
- Deploying new features on-premises requires significant upfront effort and time, delaying product time-to-market.
- Running applications in the cloud offers faster and more flexible deployment of new features compared to on-premises solutions.
- Using cloud computing allows businesses to focus on their core competencies by offloading time-consuming and undifferentiated tasks to cloud providers, such as AWS.
- AWS provides cloud computing services that enable businesses to quickly deploy and manage applications without the need for physical hardware, making it easier to scale and maintain applications efficiently.
- There are six main advantages of AWS: 1. Pay as you go. 2. Benefit from massive economies of scale. 3. Stop guessing capacity. 4. Increase speed and agility. 5. Stop spending money on running and maintaining data centers. 6. Go global in minutes.
- **Pay as you go** means that instead of investing in data centers and hardware before you know how you are going to use them, you only pay when you use computing resources, and pay for only how much you use.
- Benefit from **massive economies of scale** means that by using cloud computing, you can achieve a lower cost than you can get on your own. Because usage from hundreds of thousands of customers is aggregated in the cloud, AWS can achieve higher economies of scale, which translates into lower pay-as-you-go prices.
- By using AWS, you can **eliminate guessing** on your infrastructure needs. When you make a capacity decision prior to deploying an application, you often end up either sitting on expensive idle resources or dealing with limited capacity. With cloud computing, these problems go away. You can access as much or as little capacity as you need, and scale up and down as required with only a few minutes notice.
- By using AWS, you can **increase the speed** of making IT resources available to your developers from weeks to just minutes. This **increases agility** dramatically since the cost and time it takes to experiment and develop is significantly lower.
- You can **stop spending money on running and maintaining data centers**, and focus on projects that differentiate your business, not the infrastructure. Cloud computing lets you focus on your customers, rather than on the heavy lifting of racking, stacking, and powering physical infrastructure. This is often referred to as undifferentiated heavy lifting.
- You can **go global in minutes** because you can easily deploy your application in multiple regions around the world with just a few clicks. This means you can provide lower latency and a better experience for your customers at a minimal cost.

## https://www.coursera.org/learn/aws-cloud-technical-essentials/lecture/CUuhY/aws-global-infrastructure

- A **data center** is a physical facility that houses computer servers, storage, networking equipment, and other necessary infrastructure components. Think of it as a high-security building packed with hardware that stores, processes, and manages data. AWS operates data centers worldwide, ensuring that each is designed to be highly secure and highly available.
- An **Availability Zone (AZ)** is a grouping of one or more AWS data centers located in a specific geographic region. Each Availability Zone is isolated from the others in the same region, meaning they have independent power sources, networking, and cooling systems. This isolation is crucial for high availability and disaster recovery.
- In AWS, a **region** is a specific geographical area where AWS has a cluster of data centers. Each region is made up of multiple Availability Zones (AZs), with each AZ representing one or more physically isolated data centers within that region.
- AWS regions typically have at least two AZs, but some regions have as many as six.
- When you create resources in AWS, you choose the region where those resources will be hosted. The main considerations for AWS region selection are: 1. Compliance, 2. Latency, 3. Pricing, and 4. Service availability.
- **Compliance** is often a top priority, especially for industries like finance, healthcare, or government, where regulations mandate that data must remain within specific borders. However, depending on the specific use case, latency or pricing might take precedence.
- For applications requiring quick response times, such as real-time gaming or financial trading platforms, **latency** is crucial. If compliance is not a strict requirement, selecting a region close to your primary user base is often the next important step, as it ensures faster data transfer and a better user experience.
- AWS **pricing** can vary significantly across regions due to factors like infrastructure costs, currency exchange rates, and tax rates. After considering compliance and latency, cost-efficiency is a key factor, particularly for applications with high resource consumption or large amounts of data.
- Some AWS services are only available in specific regions, or they may have different features and versions across regions. If an application relies on a specific AWS service (e.g., a new AI/ML tool), verifying service **availability** may become a priority after confirming compliance, latency, and pricing.
- In AWS, the global edge network, edge locations, and edge caches are components that work together to deliver content and services to users quickly, regardless of where they are in the world.
- These terms are especially relevant to services like Amazon CloudFront (AWS’s Content Delivery Network, or CDN), which relies on this global infrastructure to improve speed, reduce latency, and enhance the user experience.
- The global edge network is AWS’s worldwide network of data centers designed to handle and accelerate content delivery. This network consists of numerous edge locations spread across different geographic areas. In other words, the global edge network is AWS’s large-scale infrastructure that allows for low-latency delivery of content to users all around the world.
- An edge location is a specific data center within the global edge network where AWS caches copies of content closer to end users. In other words, edge locations act as AWS’s local hubs for delivering cached content quickly to users nearby, minimizing the distance and network congestion.
- Edge locations are strategically located in major cities and highly populated areas worldwide, so when a user requests data (like a video, image, or web page), the request can be served from an edge location instead of a distant AWS region.
- Edge caches are temporary storage areas within edge locations that hold copies of frequently requested content. In other words, edge caches help reduce the load on the origin servers and decrease latency by storing popular content locally at edge locations, so it’s readily available for subsequent requests.
- When a request is made for content, the AWS CDN (CloudFront) checks if the content is available in the edge cache at the nearest edge location. If the content is found (a “cache hit”), it is delivered immediately. If it’s not found (a “cache miss”), CloudFront retrieves it from the origin server (often located in an AWS region) and caches it at the edge location for future requests.

## https://www.coursera.org/learn/aws-cloud-technical-essentials/supplement/sIxO9/reading-1-3-aws-global-infrastructure

- Each AWS Region is associated with a geographical name and a Region code.
- For example, us-east-1 is the first Region created in the east of the US and its geographical name is N. Virginia. Similarly, ap-northeast-1 is the first Region created in the northeast of Asia Pacific and its geographical name is Tokyo.
- AWS Regions are independent from one another. This means that your data is not replicated from one Region to another, without your explicit consent and authorization.
- A well-known best practice for cloud architecture is to use region-scoped managed services. In AWS, region-scoped, managed services refer to cloud services that are tied to a specific geographic region and are fully managed by AWS. These services have built-in mechanisms for availability and resiliency, meaning they’re designed to stay operational and recover quickly in the face of failures.
- When using region-scoped managed services is not possible, make sure the workload is replicated across multiple AZs. At a minimum, you should use two AZs. If one entire AZ fails, your application will have infrastructure up and running in at least a second AZ to take over the traffic.

## https://www.coursera.org/learn/aws-cloud-technical-essentials/lecture/moQ3K/interacting-with-aws