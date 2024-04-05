## AWS Fargate Overview
* provisioning, patching updates, and scaling server clusters taken care of my Fargate
* Fargate supports ECS and EKS
* pay per second of CPU or memory
* specify Fargate in Task Defs
* tasks run in Virtual Private Cloud
* load balancing: application and network supported (ALB and NLB)
* elastic load balancing not supported (ELB)
* security: no SSH access
* use cases: long running services, monolithic app portability
* Amazon: ECS, EKS to manage clusters, and ECR - Docker container registry

## Networking Basics: [How the Web Works](https://www.youtube.com/watch?v=hJHvdBlSxug)
* website stored on server
* addresses on servers are IP addresses (numbers)
* browser contacts DNS Server that maps domain name to IP
* IP add given to browser, browser requests IP from server
  * types of requests - GET, POST etc.
  * metadata
* get response i.e.
  * HTML: website's structure; can be generated dynamically
  * CSS: styles, colours
  * JavaScript: logic of website - dropdowns, tabs, sliding navigation - what changes on page after loaded
* HTTP defines how request should look like; HTTPS: encryption
* Serverside code and frameworks
* The Web: communicating with a server - request/response pattern
* mobiles doesn't wan't HTML as response, instead JSON, apps parse JSON - overall, data format can be different

## Concepts: [The Ideal CI/CD Pipeline](https://www.youtube.com/watch?v=OPwU3UWCxhw)
1. Source: require reviewers
2. Build: compile source and dependencies, run unit tests (high coverage!), check and enforce code coverage (min 90%)
3. Test Environment: run integration tests (test core functionality of APIs e.g. business logic)
4. Prod Environment 1box (1box e.g. 10% fraction of production traffic):  (if small org, can have test env within prod environment)
  * rollback alarms (errors, latency, key business metrics)
  * bake period (testing changes; 24 hours) - anomaly detection or error counts + latency breaches
  * canary - tests prod workflow with expected input and output e.g. cron job every minute, if fails, triggers alarm, triggers rollback
5. Prod Environment (as in 4.) - DNS to control weight factor

#### Developer Experience
* test and prod environments have their own DBs - each env should be in their own AWS account
* dev env should be completely isolated e.g. own AWS account

NB: Should be able to ON/OFF each step!!
