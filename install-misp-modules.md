# How to install MISP modules (easy)

Clone the repository on the machine where you want to use the modules.

If your machine is disconnected from Internet, you can also have an installation of your modules on a different machine.

~~~~
git clone https://github.com/MISP/misp-modules.git
~~~~
Go into misp-modules folder:
~~~~
sudo pip3 install -I -r REQUIREMENTS
~~~~
Now check if the installation need additionnal librairies, install them with pip3 and relaunch the installation script until you get everything covered.

Spoiler: OpenCV compilation takes time.

~~~~
          {
       }   }   {
      {   {  }  }
       }   }{  {
      {  }{  }  }
     ( }{ }{  { )
    .-{   }   }-.
   ( ( } { } { } )
   |`-.._____..-'|
   |             ;--.
   |   (__)     (__  \
   |   (oo)      | )  )
   |    \/       |/  /
   |             /  /    -Felix Lee- (Decorative)-
   |            (  /
   \             y'
    `-.._____..-'
    
    ~~~~
    
  
  ~~~~
  
  ~~~~ 
    sudo pip3 install .
    misp-modules
  ~~~~
  Go on your misp
    
 ##  Activate modules (CVE_advanced Example)
  
 Go in Server Settings and Maintenance > Plugin Settings and activate Service and Hover enable (set True)
 
 ![screenshot1](https://github.com/C00kie-/squirrel.lu/raw/master/pictures/Screenshot%20from%202020-11-05%2017-23-15.png)
 
 In Settings > Plugin Settings and enrichment, enable CVE_advanced (set True)
 
 ![screenshot2](https://github.com/C00kie-/squirrel.lu/raw/master/pictures/Screenshot%20from%202020-11-05%2017-25-37.png)
 
 Once these setups are activated, go back to "Home" page, then create an event and try the following :
 
 ![screenshot3](https://github.com/C00kie-/squirrel.lu/raw/master/pictures/Screenshot%20from%202020-11-05%2017-27-07.png)
 
 Reload your page :
 
 ![screenshot4](https://github.com/C00kie-/squirrel.lu/raw/master/pictures/Screenshot%20from%202020-11-05%2017-27-48.png)
 
 
 
 
