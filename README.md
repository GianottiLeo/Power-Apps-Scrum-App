# Power-Apps-Scrum-App

This is a app created by me in my current job. It was used by the team from San Luis Potosi region for a while to organize their daily scrum meetings. Before the app creation, they had a red and green classification, done in a Excel sheet by the division leaders before the each meeting with the site leader, after making KPIs evaluations in multiple Power Bi Reports. The requiriment was to create a app so that they could still do the red and green classification, but were able to add comments, see the past weeks status easily and check the reports on it as well. My idea to create the solution was a Power Apps App, with capability for the user to navigate between multiple categories and that way, check each necessary report embeded. I had to remove some info, since it's sensitive data, but here are some images of the app and what's possible to do in each one of them
#

<p align="center">
<img width="12" />
<img src="https://github.com/GianottiLeo/Power-Apps-Scrum-App/assets/164948682/42ddbe47-a81c-41f1-9705-ca09c275042a" height="360" alt="powerbi logo" width ="630"  />
  
###

This is the first page, where the we can see multiple empty boxes (since the app is not used anymore) that after filled, presents the user a summary of all the red and green classifications for the current day. To check the input in more detail, it's possible to navigate by gray buttons to each division or category. As you will be able to see in the next images, clicking in a category the user is directed to a page to check the PBI Reports under that metric and clicking in a division, to the page where he can check in more details the inputs from the division]
#
<p align="center">
<img width="12" />
<img src="https://github.com/GianottiLeo/Power-Apps-Scrum-App/assets/164948682/5f176359-4eaf-4204-9c9e-60690fed653c" height="360" alt="powerbi logo" width ="630"  />
  
###
This image is the page the user is directed after clicking the division 1 button. Here, the divison 1 leader is suppoused (after analysing each corresponded PBI) to classify each category as red or green and enter comments if necessary (in the white boxes, following the criteria defined in the orange boxes). It's also possible to check the historical data in a PBI Dashboard embeded in the green box. The site leader can check all that as well during the daily meeting
#

<p align="center">
<img width="12" />
<img src="https://github.com/GianottiLeo/Power-Apps-Scrum-App/assets/164948682/ef0cdabf-4b82-48f3-9204-65a16e77bb28" height="360" alt="powerbi logo" width ="630"  />

###
Lastly, this image shows a example of the category pages. In each one of them, the corresponded PBI Reports will be shown, already filtered by the division selected (in the image, it is filtered but it's possible of course to see the reports without filtering, to check the whole site). This was the hardest step to do, since I needed to create a dinamic filter in a embeded report by the text in the button selected. I tried multiple approaches, but the one that worked was studing URL enconding and creating dinamic measures inside Power Apps that would translate the selected text (Division 1, in this example) to the corresponded name of the measures in the report, but encoded like they appear in the URL filtering the page

