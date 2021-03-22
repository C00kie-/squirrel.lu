# Cheat sheet #1

*To make quickly available a few notes about repetitive tasks, that I easily forget :)*

# 1 Git Magic

When you want to reverse a commit, there will be no trace in the historic of the reversed commit

      git reverse [commit hash]

When you want to go back to a previous commit, there will be a trace of the commit

      git checkout [commit hash]


# 2 Read Json files

When you want to clean a json, use Jq output. Jq parse files and produce and unified format.

    cat [file] jq .
 
Then copy the stream into a new file, using >, cp or tee or sponge.


# 3 Work with forked repositories

Once the repository is forked from the original project and cloned on your machine:

Add the original project repository as a remote (you will need to pull updates from it):
 
      $git remote add [name you give localy to this remote] [adresse of the repository.git]
      
 Pull from the original remote:
 
      $git pull [name given to the remote] main
 **main** is tells here on with branch you want to merge new data, otherwise it's just fetched.
 
 Then push the new data on your fork online (such as your github repository for example)
 
       $git push origin 
       
       
# 4 Update MISP machine from console

log in root
      
      cd /var/www/MISP
      
      git pull origin 
      
      git submodule update
# 4 bis update MISP taxonommies, objects and galaxies from UI

Object templates

      In Menu Global Actions: List Object Templates: them Update Objects in the left panel
      
Galaxies

      In Menu Galaxies: List Galaxies: Update Galaxies in the left panel
      
Taxonomies

      In Menu Events Actions: List Taxonomies: Update Taxonomies in the left panel 

# 5 Apache config for MISP

       
       cd etc/apache2/site-enabled
      
      change your things
      
      service apache2 restart
      
 ### Change baseurl
 
       /var/www/MISP/app/Console/cake Baseurl http://[url]:[port]
