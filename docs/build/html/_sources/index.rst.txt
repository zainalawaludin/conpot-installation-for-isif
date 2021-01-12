Install conpot with docker compose
===========================================
1.	Install `docker-compose`_.

.. _docker-compose: https://docs.docker.com/engine/install/
  
2.	Clone from repository

.. code-block:: RST

  git clone https://github.com/mushorg/conpot.git
  
.. image:: images/gitclone.jpg
   :width: 600

3. Enter to directory

.. code-block:: RST

  cd conpot
  
.. image:: images/cdconpot.jpg
   :width: 400
   
4. Edit configuration to connect HPFEEDS

.. code-block:: RST

  nano conpot/testing.cfg
  
Edit in the section below, adjust the IP, port, ident, and screet according to the configuration in HPFeeds
  
.. image:: images/confighpfeeds.jpg
   :width: 300
   
5. Build image with docker compose

.. code-block:: RST

  docker-compose build
  
.. image:: images/dockercomposebuild.jpg
   :width: 500
   
.. image:: images/dockercomposebuild2.jpg
   :width: 600
   
6. Permanently run as a daemon

.. code-block:: RST

  docker-compose up -d
  
.. image:: images/dockercomposebuild3.jpg
   :width: 600
   
7. Check through the browser whether the conpot is installed successfully

.. code-block:: RST

  docker-compose up -d
  
.. image:: images/installsuccess.jpg
   :width: 600
   
8. Add ident, screet and channel to mongo hpfeeds according to the previous configuration (assuming hpfeeds has been installed)

.. code-block:: RST

  python /opt/hpfeeds/broker/add_user.py isifconpot password1234 "conpot.events" ""
   
9. Check whether ident, screet and channel have entered Mongo HPfeeds

.. code-block:: RST

  sudo mongo
  
.. code-block:: RST

  show databases
  
.. image:: images/checkmongo.jpg
   :width: 300