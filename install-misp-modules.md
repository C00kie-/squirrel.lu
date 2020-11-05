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
