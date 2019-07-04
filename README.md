## A/B test Analysis to Evaluate the Effect of Audacity's UI Changes on Reducing User's Early Cancellation

### Experiment Overview: Free Trial Screener

At the time of this experiment, Udacity courses currently have two options on the course overview page: "start free trial", and "access course materials". If the student clicks "start free trial", they will be asked to enter their credit card information, and then they will be enrolled in a free trial for the paid version of the course. After 14 days, they will automatically be charged unless they cancel first. If the student clicks "access course materials", they will be able to view the videos and take the quizzes for free, but they will not receive coaching support or a verified certificate, and they will not submit their final project for feedback.


In the experiment, Udacity tested a change where if the student clicked "start free trial", they were asked how much time they had available to devote to the course. If the student indicated 5 or more hours per week, they would be taken through the checkout process as usual. If they indicated fewer than 5 hours per week, a message would appear indicating that Udacity courses usually require a greater time commitment for successful completion, and suggesting that the student might like to access the course materials for free. At this point, the student would have the option to continue enrolling in the free trial, or access the course materials for free instead. This screenshot shows what the experiment looks like.


The hypothesis was that this might set clearer expectations for students upfront, thus reducing the number of frustrated students who left the free trial because they didn't have enough time—without significantly reducing the number of students to continue past the free trial and eventually complete the course. If this hypothesis held true, Udacity could improve the overall student experience and improve coaches' capacity to support students who are likely to complete the course.


The unit of diversion is a cookie, although if the student enrolls in the free trial, they are tracked by user-id from that point forward. The same user-id cannot enroll in the free trial twice. For users that do not enroll, their user-id is not tracked in the experiment, even if they were signed in when they visited the course overview page.

### Experiment Details
#### Part I Metric Choice
##### We care about the changes in the number of users who will enroll before and after being notified that they need at least 5hs per week in order to be successful. The unit of diversion is a cookie. Other than that, we need to measure the number of unique cookies that clicked on the "start free trial button" (number of clicks). If the user decides to enroll, he/she will login, since then we can track the number of user-ids (number of user-ids) to measure the number of users who have enrolled in or dropped or finally paid the course. There are seven metrics that can be taken into consideration:
- Number of Cookies: That is, the number of unique cookies who viewed the course pageviews. (d<sub>min</sub>=3000)
- Number of user-ids: That is, the number of users who enrolled in the free trial. (d<sub>min</sub>=50).
- Number of Clicks: That is, the number of users who clicked "start free trial". (d<sub>min</sub>=240).
- Click-through-probability: That is, number of unique cookies to click the "Start free trial" button divided by number of unique cookies to view the course overview page. (d<sub>min</sub>=0.01)
- Gross conversion: That is, number of user-ids to complete checkout and enroll in the free trial divided by number of unique cookies to click the "Start free trial" button. (d<sub>min</sub>= 0.01)
- Retention: That is, number of user-ids to remain enrolled past the 14-day boundary (and thus make at least one payment) divided by number of user-ids to complete checkout. (d<sub>min</sub>=0.01)
- Net conversion: That is, number of user-ids to remain enrolled past the 14-day boundary (and thus make at least one payment) divided by the number of unique cookies to click the "Start free trial" button. (d<sub>min</sub>= 0.0075)

##### 1. Invariant Metrics
Among the seven metrics, the invariant metrics that we can choose for sanity check should keep unaffected by the experiment. According to this rule, number of cookies, number of clicks and click-through-probability are invariant metrics because all the measurements of the three occurred before the user sees the changes (the survey asking about the amount of time the user can devote to the course) whereas the number of user-ids will be affected by the experiment because it is measured after the user sees the changes.

##### 2. Evaluation Metrics
The evaluation metrics is used to measure which variation is better. Here we can use the gross conversion rate, retention, and net conversion rate to measure the variation in the users' enrollment ratio, payment ration and payment/enrollment ratio.

#### Part II Choosing significance level, statistical power and pratical significance level
Practical significance level tells that how much change the test determines will trigger the launch of the change. Significance level and statistical power is ususally set at 0.05 and 0.8 each.

##### 1. Calculate the Standard Deviation

