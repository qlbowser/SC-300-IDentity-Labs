# Lab 22 – Microsoft Entra Entitlement Management

## Objective
Created and managed a Microsoft Entra Entitlement Management catalog and access package to provide governed access to organizational resources.

## What I Completed
- Created the **Marketing** catalog.
- Added the **Northwest Sales** Microsoft 365 group as a resource.
- Created the **Marketing Access** access package.
- Configured an approval-based access request policy.
- Submitted an access request as **B.Banner**.
- Reviewed and approved the request.
- Verified access was delivered and B.Banner became a member of **Northwest Sales**.

## Troubleshooting / Lesson Learned
The initial B.Banner request could not be approved as expected because B.Banner was involved in both the request and approval workflow. I corrected the approval configuration by using **T.Stark as the approver**, then resubmitted the request. T.Stark successfully approved the request and access was delivered to B.Banner.

This demonstrated the importance of separating the **requester and approver roles** in an access governance workflow.

## Screenshots

![01 - Configure Marketing Catalog](./01-configure-marketing-catalog-redacted.png)

![02 - Marketing Catalog Created](./02-marketing-catalog-created-redacted.png)

![03 - Select Northwest Sales Resource](./03-select-northwest-sales-resource-redacted.png)

![04 - Northwest Sales Resource Selected](./04-northwest-sales-resource-selected-redacted.png)

![05 - Northwest Sales Resource Added](./05-northwest-sales-resource-added-redacted.png)

![06 - Create Marketing Access Package](./06-create-marketing-access-package-redacted.png)

![07 - Marketing Access Package Created](./07-Marketing-Access-Package-Created-redacted.png)

![08 - Marketing Access Request](./08-Marketing-Access-Request-redacted.png)

![09 - Marketing Access Pending Approval](./09-Marketing-Access-Pending-Approval-redacted.png)

![10 - B.Banner Pending Access Request](./10-BBanner-Pending-Access-Request-redacted.png)

![11 - T.Stark Approval Pending](./11-TStark-Marketing-Access-Approval-Pending-redacted.png)

![12 - T.Stark Marketing Access Approval](./12-TStark-Marketing-Access-Approval-redacted.png)

![13 - B.Banner Marketing Access Approved](./13-BBanner-Marketing-Access-Approved-redacted.png)

![14 - B.Banner Marketing Access Delivered](./14-BBanner-Marketing-Access-Delivered-redacted.png)

![15 - B.Banner Northwest Sales Membership](./15-BBanner-Northwest-Sales-Member-redacted.png)

## Status
**Lab Completed**
