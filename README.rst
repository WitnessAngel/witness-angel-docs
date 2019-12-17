Witness Angel Documentation
##################################



L'application de démo pour Android est sortie !
======================================================

*2019/12/17*

Un prototype d'application Witness Angel est désormais disponible pour les smartphones Android !

Cette "preuve de concept" a pour but de montrer le fonctionnement du système, et d'évaluer les axes d'amélioration prioritaires (performances de chiffrement, autonomie de batterie, accès aux capteurs, compatibilité avec les différents smartphones, ergonomie...).

À terme, l'application sera bien sûr traduite en Français, dotée d'une charte graphique dédiée, portée sur d'autres plateformes, et équipée de bien plus de fonctionnalités !

Découvrez ci-dessous le manuel de l'utilisateur, avec captures d'écran.


.. list-table::
   :widths: 15 15
   :header-rows: 0

   * - Lors du démarrage, l'application est lancée, ainsi qu'un "service" qui va tourner en tâche de fond pour gérer les enregistrements.

       Lorsque l'initialisation du système est finie, le bouton "Start Witness Angel" devient cliquable.

       La console qui se trouve dessous donne les détails des opérations qui se déroulent : lancement et arrêt des enregistrements, appels aux tiers de confiance (aussi appelés "gardiens des clés"), et génération des conteneurs chiffrés dans lesquels les données sont stockées.

       Par la suite, la console sera diminuée au profit d'indicateurs graphiques plus ergonomiques.

       Lors de la première utilisation de l'application, il faut lui accorder les droits qu'elle demande, à savoir l'accès aux capteurs de l'appareil, et à la carte de stockage SD.

     - .. image:: waclient-android-manual/homepage1.jpg
          :width: 400px
          :align: center
          :alt: Page principale de l'application,  avec un bouton "start" et une console presque vide.

   * - Lorsqu'une session d'enregistrement est lancée, les différents capteurs s'activent.

       Pour cette version de démo, l'application enregistre le son du microphone, la position GPS et les données du gyroscope (mouvements de rotation du smartphone).

       À terme, bien d'autres capteurs pourront être disponibles ; photos, vidéo, vitesse de déplacement, données corporelles, appels téléphoniques...

       À intervalles réguliers, les données récoltées sont agrégées dans un fichier d'archive, qui est ensuite fortement chiffré.

       Pour l'instant, chaque session d'enregistrement utilise un unique numéro de jeu de clés, mais par le suite celui-ci pourra être renouvelé à un rythme choisi par l'utilisateur.

     - .. image:: waclient-android-manual/homepage2.jpg
          :width: 400px
          :align: center
          :alt: Page principale de l'application,  avec un bouton "start" et une console bien remplie.

   * - En cliquant sur le bouton "Settings > Encryption", on arrive à une page détaillant les algorithmes cryptographiques utilisés.

       Dans cette version de démo, on voir que deux couches de chiffrement successives ont lieu.

       La première, en AES-EAX, utilise une clé temporaire qui est ensuite chiffrée par le smartphone en RSA-OAEP, et le résultat est signé avec l'algorithme DSA-DSS.

       La deuxième couche de chiffrement, en AES-CBC, transforme le résultat précédemment obtenu. Elle se sert d'une clé temporaire qui est ensuite chiffrée avec RSA-OAEP, mais cette fois par le tiers de confiance "waescrow.prolifik.net" ; et le résultat (final) est signé avec l'algorithme RSA-PSS.

       A terme, bien plus de tiers de confiance seront impliqués (en mode "secret partagé" pour que la disparition de l'un d'eux ne mette pas en danger les données), la configuration sera modifiable par l'utilisateur, et les algorithmes pourront être rendus aléatoires d'un conteneur à l'autre, afin de renforcer encore leur sécurité (qui est déjà extrêmement forte).

     - .. image:: waclient-android-manual/encryption_algos.jpg
          :width: 400px
          :align: center
          :alt: Page listant les algorithmes utilisés.

   * - En cliquant sur le bouton "Settings > Preferences", on arrive à une page permettant de modifier quelques réglages du programme.

       Les valeurs par défaut sont adaptées à une simple démo, à terme il y aura plutôt des centaines de conteneurs par appareil, chacun stockant vraisemblablement 5mn ou 15m d'enregistrement.

     - .. image:: waclient-android-manual/user_settings.jpg
          :width: 400px
          :align: center
          :alt: Page des paramètres de l'application.

   * - En cliquant sur le bouton "Containers", on arrive à une page listant les conteneurs déjà créés. Si une session d'enregistrement est toujours active, on peut mettre à jour la liste des fichiers avec le bouton "Refresh".

       Cliquer sur un conteneur permet de voir ses métadonnées : les fichiers de données qu'il contient, son numéro de jeu de clés, ainsi que les algorithmes cryptographiques et les tiers de confiance utilisés lors de sa création.

       Le bouton "Request decryption" permet de demander le déchiffrement du conteneur sélectionné. Dans la version finale du Witness Angel, cela demandera tout un processus judiciaire, ainsi que l'intervention des tiers de confiance, pour assurer le respect de la volonté du porteur du Witness Angel, ainsi que de la vie privée de toutes les personnes impliquées. Mais pour cette démo, une procédure instantanée est permise.

       Pour que le conteneur soit déchiffrable, il faut en faire la demande moins de 5mn après le début de la session d'enregistrement qu'il l'a créé. Cela obtient alors une permission de déchiffrement de 24h pour l'ensemble des conteneurs de cette session, car ils ont le même numéro de jeu de clé ("keychain id").

       Lorsque l'on fait une requête de déchiffrement, la console de la page principale affiche les étapes de l'opération (en particulier, les appels au tiers de confiance), et le résultat (succès ou échec). En cas de succès, on peut naviguer avec un explorateur de fichiers jusqu'au dossier indiqué sur la carte SD, et vérifier avec les applications de son choix (lecteur multimédia ou éditeur de texte selon les cas) les enregistrements.

       Plus tard, il sera possible de supprimer ou déplacer chaque conteneur, mais pour la démo, on peut uniquement les supprimer tous, avec l'opération "Purge" (cela ne touche pas aux données déjà exportées vers la carte SD).

     - .. image:: waclient-android-manual/containers.jpg
          :width: 400px
          :align: center
          :alt: Page listant les conteneurs chiffrés et leurs métadonnées.


