# K12-Donor-Analysis

- Using Logistic Regression, Random Forest and Gradient Boosting approaches to identifying exciting K12 school donations projects on the Donor Choose platform.

- Understanding donors behaviors to increase user engagement of Donor Choose platform using Clustering approach.


## Table of Contents
- [Problem Overview](#problem-overview)
- [Data Quality Issues and Solutions](#data-quality-issues-and-solutions)
- [Method to Identify Exciting Projects](#method-to-identify-exciting-projects)
- [Understanding Donors Behaviors](#understanding-donors-behaviors)
- [Recommendations](#recommendations)
- [Authors And Acknowledgments](#authors-and-acknowledgments)

## Problem Overview

[Donor Choose](https://www.donorschoose.org) is an online charity platform that makes it easy to help students in need through school donations proposed by thousands of K12 teachers. The primary goals of this analysis are to identify exciting projects early, so Donor Choose can help more students to get resources and create efficient fund-raising efforts and retain donors' loyalty by understanding and matching their preferable donation profiles.

## Data Quality Issues and Solutions

We address various data quality issues throughout the obtained data:

1. **Redundant/Unnecessary Variables**: Variables contributing no meaningful information (e.g., unique IDs) and redundant variables are removed.
2. **Missing Values**: Investment depends on the `complete_rate` of the specific variable; if high, NA values get replaced with an appropriately imputed value. Otherwise, variables with missing values were subsetted out.
3. **Outliers**: Restricted data ranges at initialization whenever needed, e.g., for project cost.
4. **Character Variables**: Proper representing character variables into a numerical dataset, e.g., some key factors become dummy-encoded (1s and 0s).

## Method to Identify Exciting Projects

To identify if a project is exciting or not, three predictive models were considered: logistic regression, random forest, and gradient boosting model. The random forest was chosen because its highest precision, recall rate, and Area under the ROC curve.

#### Key Factors for Identifying Exciting Projects

From exploring the most `impactful variables`, `teacher_referred_count`, `great_messages_poportion`, `non_teacher_referred_count`, and `fulfillment_labor_material` were essential in deciding if a project is exciting.

#### Final Analytical Solution

Three predictive models were used for identifying exciting projects in which the random forest model was chosen because it had the highest precision and recall rate and the highest AUC curve close to a perfectly predicted number (1).

#### Key Factors for Identification

From the random forest variables importance chart, the top ten most impactful variables could influence whether a project is identified as exciting or not. According to the VIP chart, teacher\_referred\_count and great\_messages\_portportion were the top two most significant variables that impacted the model performance. Interestingly, when the proportion of unique comments on a page is greater than 60, the probability of those projects being identified as exciting projects increases significantly.

Furthermore, if a project had more donors in general, whether the donors were referred by teachers or donors that the teachers didn't refer, and more proportion of unique comments on a page, the project is more likely to be considered as an exciting project. On the other hand, if the project has more project cost (including or excluding tips) or is eligible for a 50% off offer by a corporate partner, the project is less likely to be considered an exciting project.

## Understanding Donors Behaviors

#### Final Analytical Solution

The final model implemented K-mean Clustering that clustered all observations into five groups. Within each group cluster, we thoroughly analyzed the donor's donation activities and behaviors and made business assumptions by understanding the underlying characteristics of the clustering model.

#### Key Characteristics of Donors

According to the k-means clustering, the donors could be divided into four groups with different characteristics.

- Profile 1: Teachers and Young Donors (Cluster 1)
  - Has the majority amount of donors
  - Donation amounts are either under $10 or $100 above
  - Largest in the portion of a donation that used accounts credit redemption
  - Least likely to use corporate-sponsored gift cards
  - Most like to donate the amount that matched 1-1 with corporate funds
  - Most donations were given through a giving/campaign page
- Profile 2: Inactive and New Donors (Cluster 2)
  - Donation amounts are usually under $10

- Tend to use the corporate-sponsored gift card
- More likely to use promo code
- More likely to donate if there is a 50% off offer by a corporate partner

- Profile 3: Wealthy Donors (Cluster 3,4)
  - Donors usually donate more than $100
  - Most of the donors are not teachers
  - Not many donors in this category use corporate-sponsored gift cards
  - More likely to pay in cash
  - More likely to pay for honorees
- Profile 4: Generous and Rational Donors (Cluster 5)
  - Donation amount usually is $100 or above
  - They prefer not to donate through a giving/campaign page
  - Check is the most preferred payment method, followed by credit card
  - More likely to donate if the donation payment is eligible for 50% off or a $100 boost by a corporate partner

## Recommendations

#### Recommendations for identifying exciting projects

From the analysis above, we can see that teacher\_referred\_count, great\_messages\_proportion, non\_teacher\_referred\_count, and fulfillment\_labor\_materials are impactful in deciding on an exciting project. If Donor Choose would like to identify the exciting projects earlier and discover the relationships between variables that impact the project outcomes, they should focus more on the projects which:

1. Improve funding opportunities for the projects that have more teacher-referred donors by filtering out the unlikely-to-succeed projects
2. Increase social media and online exposure for the projects that have 60 or more unique comments on a page by prioritizing the popular projects to be advertised in their marketing team
3. Expand non-teacher-referred donors base by doing community volunteer work or advertising the importance of kid's study materials in other community events such as collaborating with Winston-Salem Marathon to gain recognition and social attractions for potential new donors
4. Bigger projects that require more cost of fulfillment are more favorable for an exciting project. Donor Choose should put their emphasis on more significant projects that require more funding because those projects might have a bigger positive impact than small projects

#### Recommendations for Encouraging Donations

Since identified clusters have similar and distinct donors' behaviors, the targeted plan can be strategized to help Donor Choose to gauge a better understanding of their donor's profile and develop a plan of action to encourage more donations.

- Profile 1: Teachers and Young Donors (Cluster 1)
  - **Host online campaigns that collab with big merchants.** Since the group contains most of the teacher donors and others who love to use their technologies and digital devices to donate, Donor Choose should have a collab with Netflix, such that the first $10 donate, users can get ten credits for future donations on the website, plus a one-month free Netflix subscription.
  - **Make the donation time-saving and straightforward to interact with.** Donor Choose should make the online donation payment process as simple as possible and leave the donors no or very little time to rethink their decision while they are filling out card information
- Profile 2: Inactive and New Donors (Cluster 2)
  - **Surprise and make them relatable.** Donor Choose can ask YouTubers or Internet celebrities to sponsor; for example, an exciting project from Donor Choose to deliver the message that the organization is actively taking a significant role in society to ensure every kid in the community is going to have a good education
  - **Email short answer anonymous survey with benefits.** Donor Choose can target inactive donors by sending a survey to their personal emails and see the reasons why they are not willing to donate to Donor Choose, and they can be entered as a chance to draw a $50 Amazon gift card

- Profile 3: Wealthy Donors (Cluster 3,4)
  - **Host local charity events.** A formal dance party would be a good plan of action Donor Choose can use to attract financially well-off and generous individuals to donate
  - **Recommend the significant cost of the fulfillment of exciting projects.** Donor Choose can refer the projects that are identified as exciting projects and have a high cost of fulfillment to those donors' mailboxes with the reasons why the projects are essential to encourage those donors to donate consistently
- Profile 4: Generous and Rational Donors (Cluster 5)
  - **Collaborate with Corporate Donors.** Donor Choose can email or mail more donation coupons with 50% off or more discounts to incentivize the likelihood of donating for rational donors.

## Authors and Acknowledgments

This project was designed and performed by [Hanyang (Albert) Zhang](https://github.com/Hanyang-Albert-Zhang) in order to identify characteristics of donors to K12 institutions.
