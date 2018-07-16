installation documentation contributing license team getting help jupyterlab an extensible environment for interactive and reproducible computing based on the jupyter notebook and architecture currently in beta jupyterlab is the next generation user interface for project jupyter it offers all the familiar building blocks of the classic jupyter notebook notebook terminal text editor file browser rich outputs etc in a flexible and powerful user interface eventually jupyterlab will replace the classic jupyter notebook after jupyterlab reaches 1 0 jupyterlab can be extended using extensions that are npm packages and use our public apis you can search for the github topic jupyterlab extension to find extensions to learn more about extensions see our user documentation the beta releases are suitable for general usage for jupyterlab extension developers the extension apis will continue to evolve until the 1 0 release read the latest version of our documentation on readthedocs getting started installation you can install jupyterlab using conda pip or pipenv instructions on how to install the project from the git sources are available in our contributor documentation conda if you use conda you can install as bash conda install c conda forge jupyterlab pip if you use pip you can install it as bash pip install jupyterlab if installing using pip install user you must add the user level bin directory to your path environment variable in order to launch jupyter lab pipenv if you use pipenv you can install it as bash pipenv install jupyterlab pipenv shell or from a git checkout bash pipenv install git git github com jupyterlab jupyterlab git egg jupyterlab pipenv shell when using pipenv in order to launch jupyter lab you must activate the projects virtualenv for example in the directory where pipenvs pipfile and pipfile lock live i e where you ran the above commands bash pipenv shell jupyter lab installing with previous versions of jupyter notebook if you are using a version of jupyter notebook earlier than 5 3 then you must also run the following command after installation to enable the jupyterlab server extension bash jupyter serverextension enable py jupyterlab sys prefix running start up jupyterlab using bash jupyter lab jupyterlab will open automatically in your browser see our documentation for additional details prerequisites and supported browsers jupyter notebook version 4 3 or later to check the notebook version bash jupyter notebook version the latest versions of the following browsers are currently known to work firefox chrome safari see our documentation for additional details development contributing if you would like to contribute to the project please read our contributor documentation jupyterlab follows the official jupyter code of conduct extending jupyterlab to start developing your own extension see our developers documentation and api docs license we use a shared copyright model that enables all contributors to maintain the copyright on their contributions all code is licensed under the terms of the revised bsd license team jupyterlab is part of project jupyter and is developed by an open community of contributors our maintainer team is accompanied by a much larger group of contributors to jupyterlab and project jupyter as a whole jupyterlabs current maintainers are listed in alphabetical order with affiliation and main areas of contribution chris colbert project jupyter co creator application low level architecture technical leadership vision phosphorjs afshin darian two sigma co creator application high level architecture prolific contributions throughout the code base jessica forde project jupyter demo documentation tim george cal poly ui ux design strategy management user needs analysis brian granger cal poly co creator strategy vision management ui ux design architecture jason grout bloomberg co creator vision general development fernando perez uc berkeley co creator vision ian rose uc berkeley real time collaboration document architecture saul shanabrook quansight general development extensions steven silvester jpmorgan chase co creator release management packaging prolific contributions throughout the code base maintainer emeritus cameron oelsen cal poly ui ux design this list is provided to help provide context about who we are and how our team functions if you would like to be listed please submit a pull request with your information getting help we encourage you to ask questions on the mailing list and you may participate in development discussions or get live help on gitter please use our issues page to provide feedback or submit a bug report