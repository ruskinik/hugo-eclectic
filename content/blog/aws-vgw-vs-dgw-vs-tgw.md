---
title: 'AWS VGW vs DGW vs TGW'
date: Wed, 20 Apr 2022 05:35:40 +0000
draft: false
tags: ['Blog', 'Cloud', 'Networking', 'Optional', 'Partners']
---

### We compare the three AWS network gateways to help you choose the best option for your business.  


In November 2018, AWS launched the newest version of its native network routing service: [Transit Gateway (TGW)](https://aws.amazon.com/transit-gateway/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc). This cloud-based network gateway allows customers to connect Virtual Private Clouds (VPCs) across different accounts in a hub and spoke topology, and is the third evolution in this feature set. The release was preceded by [Direct Connect Gateway (DGW)](https://docs.aws.amazon.com/directconnect/latest/UserGuide/direct-connect-gateways.html), which was announced in 2017, and prior to that, [Virtual Private Gateway (VGW)](https://docs.aws.amazon.com/directconnect/latest/UserGuide/virtualgateways.html).  


Navigating these options and figuring out which fits your use case can be tricky. In this blog post, we’ll demystify each service so you can easily determine which solution is right for your business.  


To start, it’s best to consider the requirements of your workloads as each service offers certain features but not others. The table below provides a quick overview.

![](https://www.megaport.com/wp-content/uploads/2022/04/AWS-VGW-v-DGW-v-TGW_comparison-table-2.png)

Let’s break down the specific benefits of each gateway and explore how they have changed over time.

### **Virtual Private Gateway (VGW)**

![](https://www.megaport.com/wp-content/uploads/2022/04/AWS-VGW-table-1.png)

The introduction of VGW gave AWS customers the ability to let multiple VPCs, in the same region, on the same account, share a [Direct Connect](https://aws.amazon.com/directconnect/). Prior to VGW, a Direct Connect Private Virtual Interface (VIF) was required for each VPC, establishing a 1:1 correlation which didn’t scale well in terms of cost and administrative overhead. VGW became known as a solution that reduces the expense of establishing new Direct Connect circuits for each VPC – as long as both VPCs are in the same region, on the same account. This construct can be used with either Direct Connect or the Site-to-Site VPN.

![AWS Diagram Two](http://www.megaport.com/wp-content/uploads/2019/03/Screen-Shot-2019-03-28-at-4.01.57-pm.png)

**Use case: multiple VPCs in the same region sharing the same Direct Connect.**

###   

**Direct Connect Gateway (DGW)**  


![](/wp-content/uploads/2022/04/AWS-DGW-table-1.png)

  

DGW builds upon VGW capabilities by adding the ability to connect VPCs in one region to a Direct Connect in another region. CIDR addresses can’t overlap, and traffic will not route from VPC-A to the Direct Connect Gateway and to VPC-B.  It will instead route as follows: VPC-A > Direct Connect > Data Center Router > Direct Connect > VPC-B.  


[![Multiple VPCs spread across multiple regions sharing the same Direct Connect.](/wp-content/uploads/2019/04/Screen-Shot-2019-04-02-at-11.19.10-am-1.png)](http://www.megaport.com/wp-content/uploads/2019/04/Screen-Shot-2019-04-02-at-11.19.10-am-1.png)

**Use case: multiple VPCs spread across multiple regions sharing the same Direct Connect**.

###   

**Transit Gateway - TGW**  


![](/wp-content/uploads/2022/04/AWS-TGW-table-1.png)

  

Transit Gateway provides enhanced routing services over preceding offerings from AWS. The initial launch of Transit Gateway didn’t support Direct Connect and required Site-to-Site VPN, but these limitations no longer apply. However, each VPN session is still limited to 1.25 Gbps of throughput. If you want to scale beyond this, you’ll need to add multiple VPN connections to reach your desired aggregate bandwidth and then leverage ECMP to multipath traffic across all VPN connections. With ECMP, you can scale beyond 1.25 Gbps.  


TGW, coupled with [AWS Resource Access Manager](https://aws.amazon.com/ram/), allows you to use a single Transit Gateway across multiple AWS accounts. TGW also now supports Inter-Region peering. CIDR overlap is also permitted with the addition of multiple route tables. Being able to leverage multiple route tables on TGW delivers a virtual routing and forwarding (VRF) type of capability that allows you to isolate routing domains to enforce traffic segmentation. A significant advantage of TGW is that you can route between VPCs without your data having to hairpin over the VPN to your on-premises router and back to AWS, as observed with VGW and DGW. A list of supported regions is available on the [AWS FAQs page](https://aws.amazon.com/faqs/).  


[![Multiple VPCs in the same region sharing the same Direct Connect.](/wp-content/uploads/2019/04/Screen-Shot-2019-04-02-at-11.22.49-am.png)](http://www.megaport.com/wp-content/uploads/2019/04/Screen-Shot-2019-04-02-at-11.22.49-am.png)

**Use case: multiple VPCs in the same region, across different AWS accounts using the same Direct Connect.**

###   

**AWS and Megaport  
**  

By using Megaport’s Software Defined Network (SDN), you can streamline your AWS connectivity for on-demand provisioning, tighter security, and improved network performance.  


When you use Megaport's SDN, you can also connect your AWS instances to other cloud providers with [Megaport Cloud Router (MCR)](https://www.megaport.com/services/megaport-cloud-router/), and achieve branch-to-cloud AWS connectivity with one of our SD-WAN integration partners on [Megaport Virtual Edge (MVE)](https://www.megaport.com/services/megaport-virtual-edge/).  


For more information on connecting to AWS via Megaport and designing the right network architecture for your business, [get in touch with our team here](https://www.megaport.com/demo/).

  


Stay Updated
------------

Keep up to date on Megaport in the news by following us on social media at:

Twitter: [@megaportnetwork](https://twitter.com/megaportnetwork)

LinkedIn: [@megaport](https://au.linkedin.com/company/megaport)