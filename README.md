# Practicalapplication3

Notebook:  https://github.com/rh2098ta/Practicalapplication3/blob/main/practical3.ipynb

Business Problem -- 
A Portuguese bank markets term deposits by phone. We want to predict which customers will subscribe so we can prioritize who to call, improve conversion rates, and reduce wasted calls.

Project Overview -- 
This project looks at data from a Portuguese bank's telemarketing campaigns to figure out which customers are actually likely to subscribe to a term deposit. The dataset comes from the UCI Machine Learning Repository, and the main problem is straightforward — most calls don't result in a sale, so the bank is basically wasting time and money calling people who aren't interested. My goal was to find patterns in customer attributes and campaign history that could help predict who's worth calling.

<img width="992" height="716" alt="image" src="https://github.com/user-attachments/assets/4a06fdb4-b4fb-43fe-a79e-332c2be8b012" />


Key Findings from Exploratory Analysis -- 

I started with some descriptive analysis and visualizations to get a sense of what was going on. A few things stood out right away. Students and retirees had way higher subscription rates than other groups.

<img width="962" height="706" alt="image" src="https://github.com/user-attachments/assets/dfed5cc6-1227-4337-94a1-321be47936ae" />

I also noticed that certain months performed better — March, May, and August especially — though I'm not sure why that is at this point. The biggest factor by far was call duration. Successful calls lasted much longer on average, which makes sense when you think about it. If someone hangs up quickly, they're probably not interested. Also, customers who subscribed in past campaigns were much more likely to say yes again, so past behavior turned out to be a strong predictor.

<img width="946" height="714" alt="image" src="https://github.com/user-attachments/assets/d2fdc680-b4b3-4e4b-8c86-f3c571fd0f5d" />


Model Development and Results -- 

For the modeling part, I tried out four different classifiers we covered in our program: K-Nearest Neighbors (KNN), Logistic Regression, Decision Tree, and SVM. I used stratified cross-validation and looked at a bunch of metrics — accuracy, precision, recall, F1, and ROC-AUC—to compare them. Logistic Regression ended up working the best overall, with a ROC-AUC of 0.938 and pretty balanced precision and recall. I did a quick grid search on the regularization parameter and got a slight bump in performance, though overall it wasn't a huge difference. The nice thing about using ROC-AUC here is that the model can rank customers by their likelihood to subscribe, so the bank could prioritize high-probability leads and avoid wasting time on people who probably won't convert.

<img width="972" height="718" alt="image" src="https://github.com/user-attachments/assets/943fcb0f-6e11-4349-8958-2491dbc34375" />


Conclusions and Next Steps -- 

Overall, I think a relatively simple model like this could make a real difference in how the bank runs these campaigns. Next steps could include deploying it in some kind of production environment, playing around with the probability threshold depending on how aggressive they want to be with costs, and maybe adding more features like economic indicators to see if that helps. But honestly, what I think would be most practical is building an interactive Tableau dashboard. Instead of just showing results in a notebook, a dashboard would let a marketing manager upload a list of customers, click a button, and instantly see who the model thinks is most likely to subscribe. It could include filters (like by job, age range, or month of contact), a visualization of the model's top features, and a downloadable "ranked call list" sorted by subscription probability. Tableau dashboards are a favorite of mine and I find them so helpful when having to review data and make suggestions or predictions. A dashboard like this would show how the model could actually be used by a non-technical user and turns the project from just analysis into something closer to a real tool people could use throughout the work day. If they actually implement this, they should see better conversion rates and spend less effort on dead-end calls.
