---
title: AWS VPC Deleted
kind: documentation
parent: cloudtrail
tags:
- security:attack
- tactic:TA0040-impact
- technique:T1485-data-destruction
- service:ec2.amazonaws.com
- source:cloudtrail
meta_image: /images/integrations_logos/amazon_cloudtrail.png
---
## **Goal:**
Detect when an attacker is destroying a VPC

## **Strategy:**
Monitor CloudTrail and detect when a VPC is deleted via the following API call:
* [DeleteVpc][1]

## **Triage & Response:**
1. Determine who the user was who made this API call.
2. Contact the user and see if this was an API call which was made by the user.
3. If the API call was not made by the user:
   * Rotate the user credentials and investigate what other API calls.
   * Determine what other API calls the user made which were not made by the user.[1]: https://docs.aws.amazon.com/cli/latest/reference/ec2/delete-vpc.html