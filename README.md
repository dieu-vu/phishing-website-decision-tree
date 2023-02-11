# phishing-website-decision-tree
A small workbook studying phishing website detection using the decision tree algorithm

This is actually an assignment in my Maths & machine learning course at Metropolia. 
As a newbie (again) in machine learning, I found this exercise of phishing website analytics using decision tree having interesting findings, so I shared this work to public.

From the data, we can draw a conclusion that if you spot the following signs in a websites, it's pretty high chance (around 90%) that the website is phishy.

- Check Whether the website uses HTTPS. 
  - If not, then check the web traffic if the website ranked among the top 100,000 of popularity.
      - If the website has no traffic or is not recognized by the Alexa database, it's likely to be a phishing website
          - Check if the URL of the anchor is linked to the same domain. 
            - If it links to a different domain, it's likely that the website is phishing
  - If yes, check if the URL has prefixes or subfixes added (with the dash symbol)
     - If the website has prefixes or subfixes added (with the dash symbol), it's a phishing website
        - If the website does NOT prefixes or subfixes
            - Check if the domain name has been registered in a short period of time (< 1 year). 
               - If yes, it's likely that the website is phishing
               
 The decision tree is visualized as following 
 
 _(Gini index measures the unitedness of the observations in a node, ie. how tightly the observations in a given node fall into the same class)_
 
 ![img](https://github.com/dieu-vu/phishing-website-decision-tree/blob/master/tree.png)
 
 
Feature importance based on mean decrease in impurity
 
![img](https://github.com/dieu-vu/phishing-website-decision-tree/blob/master/MDI.png)



From the feature importance results, we can confirm that the feature SSLfinal_State has the highest importance when classifying the phishing website. Other features by importance level order are web_traffic, URL_of_Anchor, having_Sub_Domain and Prefix_Suffix


For more details of implementation, you can check out the Jupyter Notebook in the repo, or review its [HTML version](https://github.com/dieu-vu/phishing-website-decision-tree/blob/master/Dieu-method-assmt3-decision-tree.html)

[Data source](https://archive.ics.uci.edu/ml/datasets/phishing+websites)

Hope that you find it interesting like I do, and feel free to give comments. Thanks a lot! :D
