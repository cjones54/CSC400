# CSC400
School Project
This project is intended for academic purposes first and there is available 'as is' with no warranty.

This project contains a template from startbootstrap.com and has a MIT license seen here:https://github.com/StartBootstrap/startbootstrap-sb-admin-2/blob/master/LICENSE
This project also contains PHPMailer their license is here: https://github.com/PHPMailer/PHPMailer/blob/master/LICENSE
===========================================================================
The Directory Structure is as follows:
===========================================================================
root directory
- Contains folders for styling and scripts
- index.php is the home page that connects to the rest of the site -> index.php in subdirectories are used to redirect browsers attempting to access the directory
- .htcaccess - file used by Apache2 to rewrite URL paths -> There are a few in different sub-directories

- /vendor contains styling for DataTables (DataTables.net), Bootstrap (getbootstrap.com), Charts.js (Chartsjs.org), fontawesome (fontawesome.com), jquery (jquery.com),
  and jquery-easing (jqueryui.com/easing/)
  
- /img contains some images used on the site a few are sourced from unsplash.com

- /css & /scss contains styling provided by the template plus personal additions

- /js contains default demo JS scripts and some scripts used for the website (others are in .php files related to their action)

- /uploads contains location where images are uploaded to be used in a slide show on main page.

- /Pages >>This location has all the pages for the site
  > The PHP files here are the site pages and generally named for the action that occurs
  
  > The primary files developed include: addevent, announcements, login, logout, mytickets, reports, TeamDashboard, ticket, ticketcheckup, ticketsubmit, and        user_activity
  
  >These all reach into the sub-directories to do processing
 =========================================================================== 
  --/Pages//manage contains ticket managing files from a logged in user
  --/Pages//Includes contain the main includes file
  
  
===========================================================================  
  ---/Pages//Includes///DataLayer contains MySQL related configurations plus first deployment scripts
  ---/Pages//Parts///Parts contains much of the pieces that build each page, many cases the queries are on these pages within functions
  
  
  ===========================================================================
  |                                                                         |
  |                       First Time Deployment                             |
  |                                                                         |
  ===========================================================================
  
  1)Place all files in the webroot of an linux system with:
            a. apache2 installed
            b. MySQL
             
  2)Open /Pages/Includes/DataLayer/configuration.php
      >> Make a copy of the file for reference and backup
      
      I. Edit the email settings (if desired, failing to specify all values will result in the feature remaining inactive)
            a. SMTP (ex: smtp.google.com)
            b. Username (Someone@emaildomain.com)
            c. Password (Plaintext password, recomendation is don't use your personal email or at least keep it temporary)
      II. Edit Google reCaptcha v2 settings (if desired, requires registering your domain with google)
            a. Site Key > will be displayed in the code of the page
            b. Secret Key > used for the system to verify recaptcha
            c. Ensure the keys are for reCaptcha V2, any other version will have unknown results on this platform
      III. Edit MySQL settings
            a. Host >   No need to change if all on one system
            b. Port > **Only change if you changed the default port on the MySQL,
            c. DB > The schema setup on MySQL
            d. Username > Self explainatory, just be sure that the user specified has permission to create and modify tables withing the schema
            e. Password > Self explainatory, 
            f. Verify that everything is typed correctly:
              i. Check that the variables were unintentially modified
              ii. Verify all the information is surrounded by a single set of quotes, like 'word' or "word" >> single and double quotes will work the same
      IV. In the webbrowser go to http(s)://HOST/Pages/Includes/DataLayer/first_time.php
          a. DB script will run and specify errors
          b. If no errors, "SUCCESS" will display with login credentials
            i. This release doesn't support dynamic managment of accounts quite yet
            
            
  
  
  
  
  
  
  
  
  
  
