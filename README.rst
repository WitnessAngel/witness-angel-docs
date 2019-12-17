Witness Angel Status Information
##################################

You can now download the **first demo release** of the Witness Angel android application.

https://github.com/WitnessAngel/witness-angel-client/releases/tag/Release0.1a

.. BROKEN ON GITHUB `English <english_announcement_>`_ and `French <french_announcement_>`_ announcements and manuels for this releases are available below.

English/French announcements and manuels for this releases are available below.

-----


.. _english_announcement:

[EN] The demo application for Android is out!
======================================================

*2019/12/17*

A Witness Angel application prototype is now available for Android smartphones!

This "proof of concept" aims to show how the system works, and to evaluate the priorities for improvements (encryption performance, battery life, access to sensors, compatibility with various smartphones, ergonomics, etc.).

In the long term, the application will of course be translated into other languages, get a dedicated design, be ported to other platforms, and equipped with many more features!

Discover below the user manual, with screenshots. App download link is at the top of this page.


.. list-table::
   :widths: 15 15
   :header-rows: 0

   * - At startup, the application is launched, as well as a "service" that will run in the background to manage the records.

       When system initialization is complete, the "Start Witness Angel" button becomes clickable.

       The console below provides details about the operations that take place: launching and stopping sensors, calling trusted third parties (also called "key guardians"), and generating encrypted containers in which data is stored.

       Thereafter, the console will be reduced in favour of more ergonomic indicator widgets.

       When the application is first used, it must be granted the rights that it requires, namely access to the device's sensors and SD storage card.

     - .. image:: waclient-android-manual/homepage1.jpg
          :width: 400px
          :align: center
          :alt: Main page of the application, with a "start" button and an almost empty console.

   * - When a recording session is started, the various sensors are activated.

       For this demo version, the application records microphone input, GPS position and gyroscope data (smartphone rotation movements).

       In the long term, many other sensors will  be available; photos, video, movement speed, body data, phone calls...

       At regular intervals, the collected data is aggregated into an archive file, which is then highly encrypted.

       For the time being, each recording session uses a unique key set number, but later it will be renewed at a rate chosen by the user.

     - .. image:: waclient-android-manual/homepage2.jpg
          :width: 400px
          :align: center
          :alt: Main page of the application, with a "start" button and a well-filled console.

   * - By clicking on the "Settings > Encryption" button, you reach a page detailing the cryptographic algorithms used.

       In this demo version, we see that two successive layers of encryption take place.

       The first, of type AES-EAX, uses a temporary key that is then encrypted by the smartphone with RSA-OAEP, and the result is signed with the DSA-DSS algorithm.

       The second layer of encryption, of type AES-CBC, transforms the result previously obtained. It uses a temporary key that is then encrypted with RSA-OAEP, but this time by the trusted third party "waescrow.prolifik.net"; and the (final) result is signed with the RSA-PSS algorithm.

       In the long term, many more trusted third parties will be involved (in "shared secret" mode so that the disappearance of one of them does not endanger the data), the configuration will be modifiable by the user, and the algorithms might be randomized from one container to another, in order to further strengthen their security (which is already extremely strong).

     - .. image:: waclient-android-manual/encryption_algos.jpg
          :width: 400px
          :align: center
          :alt: Page listing the algorithms used.

   * - By clicking on the "Settings > Preferences" button, you reach a page where you can change some of the program settings.

       The default values are adapted to a simple demo, eventually there will rather be hundreds of containers per device, each probably storing 5mn or 15m of recording.

     - .. image:: waclient-android-manual/user_settings.jpg
          :width: 400px
          :align: center
          :alt: Application settings page.

   * - By clicking on the "Containers" button, you reach a page listing the containers already created. If a recording session is still active, you can update the list of files with the "Refresh" button.

       Clicking on a container allows you to see its metadata: the data files it contains, its keychain id number, as well as the cryptographic algorithms and trusted third parties used when it was created.

       The "Request decryption" button is used to request the decryption of the selected container. In the final version of the Witness Angel, this will require a whole judicial process, as well as the intervention of trusted third parties. This will ensure that the will of the Witness Angel bearer is respected, as well as the privacy of all those involved. But for this demo, an instant procedure is allowed.

       In order for the container to be decryptable, the request must happen within 5 minutes of the start of the recording session which created it. This then obtains a 24-hour decryption permission for all containers in this session, since they have the same keychain id number.

       When making a decryption request, the main page console displays the steps of the operation (in particular, calls to the trusted third party), and the result (success or failure). If successful, you can navigate with a file explorer to the folder indicated on the SD card, and check the recordings with the applications of your choice (media player or text editor as appropriate).

       Later, it will be possible to delete or move each container, but for the demo, you can only delete them all, with the "Purge" operation (this does not affect the data already exported to the SD card).

     - .. image:: waclient-android-manual/containers.jpg
          :width: 400px
          :align: center
          :alt: Page listing encrypted containers and their metadata.


-------

.. _french_announcement:

[FR] L'application de démo pour Android est sortie !
======================================================

*2019/12/17*

Un prototype d'application Witness Angel est désormais disponible pour les smartphones Android !

Cette "preuve de concept" a pour but de montrer le fonctionnement du système, et d'évaluer les axes d'amélioration prioritaires (performances de chiffrement, autonomie de batterie, accès aux capteurs, compatibilité avec les différents smartphones, ergonomie...).

À terme, l'application sera bien sûr traduite dans d'autres langues, dotée d'une charte graphique dédiée, portée sur d'autres plateformes, et équipée de bien plus de fonctionnalités !

Découvrez ci-dessous le manuel de l'utilisateur, avec captures d'écran. Le lien de téléchargement de l'application est en haut de cette page.


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

       À terme, bien d'autres capteurs seront disponibles ; photos, vidéo, vitesse de déplacement, données corporelles, appels téléphoniques...

       À intervalles réguliers, les données récoltées sont agrégées dans un fichier d'archive, qui est ensuite fortement chiffré.

       Pour l'instant, chaque session d'enregistrement utilise un unique numéro de jeu de clés, mais par le suite celui-ci pourra être renouvelé à un rythme choisi par l'utilisateur.

     - .. image:: waclient-android-manual/homepage2.jpg
          :width: 400px
          :align: center
          :alt: Page principale de l'application,  avec un bouton "start" et une console bien remplie.

   * - En cliquant sur le bouton "Settings > Encryption", on arrive à une page détaillant les algorithmes cryptographiques utilisés.

       Dans cette version de démo, on voit que deux couches de chiffrement successives ont lieu.

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

       Le bouton "Request decryption" permet de demander le déchiffrement du conteneur sélectionné. Dans la version finale du Witness Angel, cela demandera tout un processus judiciaire, ainsi que l'intervention des tiers de confiance. Ceci afin d'assurer le respect de la volonté du porteur du Witness Angel, ainsi que de la vie privée de toutes les personnes impliquées. Mais pour cette démo, une procédure instantanée est permise.

       Pour que le conteneur soit déchiffrable, il faut en faire la demande moins de 5mn après le début de la session d'enregistrement qu'il l'a créé. Cela obtient alors une permission de déchiffrement de 24h pour l'ensemble des conteneurs de cette session, car ils ont le même numéro de jeu de clé ("keychain id").

       Lorsque l'on fait une requête de déchiffrement, la console de la page principale affiche les étapes de l'opération (en particulier, les appels au tiers de confiance), et le résultat (succès ou échec). En cas de succès, on peut naviguer avec un explorateur de fichiers jusqu'au dossier indiqué sur la carte SD, et vérifier avec les applications de son choix (lecteur multimédia ou éditeur de texte selon les cas) les enregistrements.

       Plus tard, il sera possible de supprimer ou déplacer chaque conteneur, mais pour la démo, on peut uniquement les supprimer tous, avec l'opération "Purge" (cela ne touche pas aux données déjà exportées vers la carte SD).

     - .. image:: waclient-android-manual/containers.jpg
          :width: 400px
          :align: center
          :alt: Page listant les conteneurs chiffrés et leurs métadonnées.


