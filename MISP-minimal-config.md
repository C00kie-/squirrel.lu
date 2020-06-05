Once you have MISP [downloaded](https://www.circl.lu/misp-images/latest/) and installed on your machine, you connect to it with your browser, using the installation credentials.

!!!
Before to do anything : change the password immedialty.
Else: make a coffee.

      )  (
     (   ) )
      ) ( (
 mrf_______)_
 .-'---------|  
( C|/\/\/\/\/|
 '-./\/\/\/\/|
   '_________'
    '-------'
    
Then, follow these steps:
You need to set the baseurl of your machine, so when the systems is running, it knows where to send requests to.
  - set base_url of the machine (apache virtualhost name). Go to: **Administration, Server settings and maintenance, TAB Misp Settings**
Your new setup needs to know an organisation name!
  - To do so, create a new organisation like MY ORGANISATION, which will host this running instance of MISP.
  - You need then to indicate this organisation as the default one. For so, replace 'MISP.host_org_id'.
Good so far!
But your users still see default messages when they login. For now it says everything has to be configured. Uh oh. 
  - To change this, set 'MISP.footermidleft' and 'MISPfootermidright' to display the message you want. like "I LOVE" ----------- "COOKIES" 
  
Now humans. 
  - Create a new user as admin role for MY ORGANISATION.
  - Log out.

... Have a sip of coffee.
  - Log in with the new user. Now you can remove the default user 'admin@admin.test', Goodbye.

And the machine...
  - It's recommended that you select the taxonomies for you sharing community, as also the external feeds. You can select caching only if you don't want the full events,isn't cool?

  - Also select and enable the warning list. You don't want to block known ip for example. If you don't know what that is, just select and enable all, it's fine.

Wooo, you are close!
  - Now add the remote MISP instances, where you have access.
Here it is.
