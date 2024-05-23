# Outline

When I look as a technical-consultant to the status of 'infrastructure as code' (IaC) at organisations, I see that there are babysteps made forward and there is a lot to gain. In this document I like to express an alternative view on this topic.

## Intro

[What is IaC?](./whatIsIac.md)

[Current pipeline](./currentPipeline.md)

[Proposed](./proposedPipeline.md)

___
## Preparation

In this phase you like to think about what you like to achieve. Be a dreamer and raise the bar. The tools to support IaC are mostly already available in your organization. For the digital part of your service:
- a service management tool
- a centralized sourcecode repository, including the ability to trigger a pipeline
- a centralized corporate secrets management tool
- a centralized artifact repository
- a centralized way of monitoring the crown-jewels

Next to that:
- you need a landingzone where you and your colleages are authorized to perform all CRUD-functions required to run the service.
- A very nice to have is the insight in cost and the benefits of the current service. Once IaC is running it can be used for comparison to the new state.

### Education
Teach your audience what Infra as Code is about. At least they should understand:
The principle of: 
- zero-touch
- fail-fast
- isolated end-to-end testing
- never, ever push secrets to git
- build once, deploy anywhere

On top of that: These are the questions you like you audience to answer for themselves. 

In relation to your digital service:
1. What does your (partial) product look like?
1. Who is your consumer?
1. Does this consumer have a list of requirements?
1. Has there been an audit in the past? If yes, is there someting in the auditreport that can be solved by using a alternative way of working?
1. How do you and your customer request your service?
1. Is the handling op your service based on manual steps?
1. Are there approvals in the process that are always approved "unseen"?
1. what is the estimated time to delivery of the service?
1. Do you make use of DORA metrics of your service?
1. Is there a historic view on the DORA metrics?
1. Where is your service running?
1. What dependencies do you have for the functioning of your service?
1. What interfaces do you use for a production flow?
1. What makes you confident the service is functioning correctly?
1. What makes you confident the service does not contain 'unwanted' content?
1. Is there any documentation available of the interfaces?
1. Is there a workinstruction on how to mock a dependent version while testing in isolation? 
1. What is the strategy?
1. What architecture do I use for my service?

In relation to exposing your service: (based on the basic funtions identified by CRUD): 
1. Can a customer Create a (partial) product via a digital way? (I'm referring to the use of an exposed (Backend)-API, not by sending an Excel-sheet via email).
1. Can a customer Read the status of their consumed product?
1. Can a customer Update their consumed product?
1. Can a customer Delete their consumed product?

If you feel intimidated by the questions, skip them. However, this is the point where you start coding your infrastructure.
___
## Identification
If applicable, get the answers of the previous step and:
- Acknowledge that something needs to change.
- Write down in a S.M.A.R.T. way what is subjected to change.
- Check if your planned solution is aligned with the answers in the previous step

Then: identify where the current implementation deviates from the new way of working and store this information carefully.
___
## Containment, Isolate
Start finalizing the workon developing a consistent way of exposing your service. A proven technology is to develop an API that supports the basic functions of CRUD (Create, Read, Update, and Delete)

- If the new way of working is not good enough, add the 'deviations' of the new way of working to the identification list. For the remainder leave the list at rest, but keep it insight.
- For any new request, start using the new way of working. At the start invest in guiding your consumer.
- Is the new way of working functioning well enough to support your consumers?

This is a good moment to check if you are still on track, meeting your own requirements. Iterate over this document from the start and see if you ar still on track. If you are, you can proceed.

___
## Eradicate
In this step you clean up the old way of working and replace it by the new way of working.

It is now time to work on the list created by the identification step. 
- make a plan to resolve the listed issue one-by-one.
- when making this plan, keep in mind:
- Is there a possibility to adept the new-way-of-working without breaking the old way of working?
- if not, is it a plan to rebuild a new service? 
- As long as there are no items on this list, the content of the list should be part of your day-to-day operations, until the list is empty. This is the only good reason to drop the list.

___
## Lessons Learned
Please take time to look back. Present: 
- the old way of working and what compare that with the new way of working
- support this storyline with the use of DORA metrics