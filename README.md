## Environnement Intégration Continue
Mettre en place un environnement d'intégration continue Jenkins (Maven, Git)

### Dans ce qui suit, on mettra un environnement d'intégration contrinue, étape par étape: on aura besoin d'installer beaucoup d'outils dont Jenkins, Git, Maven, Eclipse ...etc

# Installer Java et Git sur votre machine 
* - Installer github en ligne de commande et/ou github desktop (github GUI) : https://desktop.github.com/  
* - Créer un compte github et connectez-vous sur l'interface github installée précédement 
* - Configurer les clefs SSH : permet d'établir une connexion sécurisée entre votre poste de travail et github. 
    * Pour se faire je vous invite à vérifier tout d'abord si vous n'aviez pas déjà une clef ssh                      :https://help.github.com/articles/generating-an-ssh-key/
    * ouvrez la console bash de votre git installé et insérer la commande : ls -al ~/.ssh, et vérifier si vous avez des fichiers de format .ssh, si n'y a aucun fichier , il va falloir générer la clef
    * Pour générer la clef : ssh-keygen -t rsa -b 4096 -C "your_email@example.com", l'addresse mail de votre compte  github
    * Par la suite, il faut s'assurer que l'agent de sécurisation SSH est démarré, pour se faire : eval "$(ssh-agent -s)", cela va vous afficher "Agent pid #number"
    * Associer la clef ssh à l'agent SSH : ssh-add ~/.ssh/id_rsa
    * Associer la clef SSH à votre compte Github : https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/
    * Tester la connexion ssh  : ssh -T addresse@mail
* Récupérer un projet Exemple que l'on utilisera dans cette démo et en faire un FORK : 
    * https://github.com/wakaleo/game-of-life
    * le cloner sur votre poste : git clone git@github.com:<username>/game-of-life.git
    
# Installer/Configurer Jenkins et maven
   
   Nous allons télécharger Jenkins que l'on va lancer sur un serveur local et qu'on va ouvrir sur un navigateur internet
   * Pour télécharger : https://jenkins.io/index.html   : on peut le télécharger soit en .war que l'on démarera par la commande : java -jar -jenkins.war ; soit en téléchargeant le .zip (windows)
    
   * Dézippez le .zip et ouvrez le fichier .msi. Une fois que l'installation est finie, jenkins se lancera sur votre navigateur en localhost:8080
   * Dans ce qui suit, on va configurer Jenkins :
      * Une conf type que vous pourriez utiliser : http://www.vogella.com/tutorials/Jenkins/article.html
      * Tout d'abord : 
