The dataset is a Login Data Set of SSO solution of an online service in Norway. The dataset can be used for developing code for Risk-Based Authentication, 
and identifying threats by analysing login patterns of users, using Machine Learning.

The RBA implementation, requires a lot of computation, and access to validation scores of features(For example, what is the probability of an IP address to be 
an attack IP, or a OS family plus version to be an attack login attempt. One could calculate these organization wide, or use third party APIs), and is challenging to run on a personal laptop. The calculation of risk score, will involve, calculating validation score of each feature, and calculation the final probability of a login attempt being a threat, using all these validation scores, and the login history of each user to figure out probability of the login attempt for this particular user to be a threat given that the feature has a specific value(as in the login attempt).

This implementation only covers the threat detection portion, not the calculation of Risk scores.

The dataset has been downloaded from Kaggle(https://www.kaggle.com/datasets/dasgroup/rba-dataset). It is a Synthesized login feature data of 33M login attempts and 3.3M users on a large-scale online service in Norway. 
Original data collected between February 2020 and February 2021. The users used this SSO to access sensitive data provided by the onlineservice, e.g., 
a cloud storage and billing information.

The data set contains the following features related to each login attempt on the SSO:


Feature                    | Data Type | Description                                                                                      | Range or Example
---------------------------|-----------|--------------------------------------------------------------------------------------------------|------------------------------------------------------
IP Address                 | String    | IP address belonging to the login attempt                                                        | 0.0.0.0 - 255.255.255.255
Country                    | String    | Country derived from the IP address                                                              | US
Region                     | String    | Region derived from the IP address                                                               | New York
City                       | String    | City derived from the IP address                                                                 | Rochester
ASN                        | Integer   | Autonomous system number derived from the IP address                                             | 0 - 600000
User Agent String          | String    | User agent string submitted by the client                                                        | Mozilla/5.0 (Windows NT 10.0; Win64; \...
OS Name and Version        | String    | Operating system name and version derived from the user agent string                             | Windows 10
Browser Name and Version   | String    | Browser name and version derived from the user agent string                                      | Chrome 70.0.3538
Device Type                | String    | Device type derived from the user agent string                                                   | (`mobile`, `desktop`, `tablet`, `bot`, `unknown`)[^1]
User ID                    | Integer   | Idenfication number related to the affected user account                                         | [Random pseudonym]
Login Timestamp            | Integer   | Timestamp related to the login attempt                                                           | [64 Bit timestamp]
Round-Trip Time (RTT) [ms] | Integer   | Server-side measured latency between client and server                                           | 1 - 8600000
Login Successful           | Boolean   | `True`: Login was successful, `False`: Login failed                                              | (`true`, `false`)
Is Attack IP               | Boolean   | IP address was found in known attacker data set                                                  | (`true`, `false`)
Is Account Takeover        | Boolean   | Login attempt was identified as account takeover by incident response team of the online service | (`true`, `false`)

