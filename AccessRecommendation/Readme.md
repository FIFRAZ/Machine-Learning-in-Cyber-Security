One of the key objectives of IGA is to ensure that users have least privilege, in other words, just adequate access to do the job they are meant to do.
Hence, it is important that in the request workflow, when the product provides recommendations to the user for the access they can request for, the recommendations are provided with due diligence, staying close to the <b> "Least privilege"</b> objective! 

Shopping and entertainment platforms have different objective, their recommendations can be more generous.

My proposal is to use a combination of Unsupervised, Supervised and user profile based output, that is fed to a Rule based logic, which generates the final recommendations.

# Unsupervised learning
- It is important to keep features configurable so that admin can choose the features to be used for finding peer group
Using unsupervised learning, we can find the cluster of similar users based on their contextual attributes. Then either we could just recommend whatever the current user does not have compared to the peer group, and we could further refine the process by using supervised learning, over the data from the cluster to which this user belongs
Note that,Peer group analysis must take care of third party access (peer at vendor level, and user level)
- Role-Mining (https://github.com/FIFRAZ/Machine-Learning-in-Cyber-Security/tree/main/RoleMining) code explains how this can be achieved

# Supervised learning

Supervised learning Model is run for this peer group, to recommend only the most relevant roles/entitlements/accounts
This will take care of minor differences in the peer group. Not everyone in the peer group needs to have the same level of access. They still belong to the same cluster because of the similarilty score threshold we would have chosen. Users in the peer group might be working on different projects(which are dynamic) requiring different access.

# Rule Based Logic
- Does the user already have this account/Role/Entitlement
- If entitlement is going to be recommended, does the user have an account in the application?
- Does this entitlement cause any SoD policy violation? Highlight the need for providing necessary justification, approval process
- Is this a privileged access? Highlight the need for providing necessary justification, approval process, link to PAM process in place (Just in time access)
- Logic(Rule based/ML ) based on user profile (UI Feedback on how relevant each recommendation was?, search keyword '''
