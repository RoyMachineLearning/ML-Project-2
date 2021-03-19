
Business Context:

The Mortgage Pre-Fund Review team reviews residential mortgage files from the branch network across Canada to identify errors in the application policy, including non-compliance and/or deficiencies in received supporting documentation. Ideally, every submission would be correct the first time and not require additional back and forth between Global Operations and the branch. This is not always the case, however, as we often have to return the applications to the branch for them to make updates and changes before Pre-Fund can approve the application. This puts unnecessary strain on the Pre-Fund unit as they have to review the same application multiple times and can cause significant delay to mortgage approval thereby creating a poor Customer experience.

Report Logic:

Each application has one ‘Case ID’ associated with it
If the application is first time right, then there will only be one associated ‘Notification ID’. If it is not first time right, then there can be multiple notifications associated with the case.
A notification is generated for a case every time the branch submits or resubmits an application to Pre-Fund for review.
The Case Create Time is equal to the first Notifications Create Time and the Case Resolved Time is equal to the last notifications Resolved Time

Calculation Logic:

Time to Pre-Fund Decision: # of business days between Details[Application Date] and Cases[Resolved Time]
Case Time: # of business days between Cases[Create Time] and Cases [Resolved Time]
Notification Time: # of business days between Notifications[Create Time] and Notifications[Resolved Time]
Not First Time Right Branch Time: (Case Time) – (SUM of all Notification Time for the associated Case)
Business Days: Monday to Friday, not including Ontario Public Holidays
 
Reporting Ask:

Our executive wants to understand the impact of applications not being first time right. She will be bringing this report with her to a meeting with the District Vice Presidents of the various regions to discuss targets for next year.

Showcase which Regions and Districts were the worst performing when it comes to first time right
What is the impact on ‘Time to Pre-Fund Decision’ and ‘Case Time’ when a case is not first time right
What is the average number of notifications associated with each case and are there any trends positive or negative?
When a case is not first time right, what is the percent of total case time spent with the branch making revisions vs. Pre-Fund working the notifications
 
Predictive Modeling Ask:

Build a predictive model using Jupyter and Scikit-learn to predict FTR
What should be the drivers that could result in improved Operations or Business Process
