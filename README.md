Environment
===========

Install the required packages

    sudo apt-get install python3-pip

Open a pipenv

    python3 -m pip install pipenv
    pipenv shell

Enable Pelican plugins

    git submodule init
    git submodule update

Deploying
=========

    make github


Build for upload in Freenet
---------------------------

    source pelican_env/bin/activate
    PYTHONPATH=$PYTHONPATH:pelican-plugins{$(ls pelican-plugins/| sed 's/ /,/g')}
    SITEURL=/USK@0iU87PXyodL2nm6kCpmYntsteViIbMwlJE~wlqIVvZ0,nenxGvjXDElX5RIZxMvwSnOtRzUKJYjoXEDgkhY6Ljw,AQACAAE/freenetproject-mirror/490
    DEBUG=1
    make html && freesitemgr update freenetproject-mirror

Testing 
=======

    make devserver
