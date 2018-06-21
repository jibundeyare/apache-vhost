# Apache vhost

Ce tuto montre comment configurer Apache et des noms de domaine locaux (`http://example.test` par exemple).

Il s'applique à :

- Wamp (Windows)
- Mamp (MacOS)
- Xampp (MacOS)

Notez que **vhost = virtual host**

## Wamp

**Attention** : si votre installation est en 32 bit, Wamp se trouve alors dans `C:\wamp` et non `C:\wamp64`.
Adaptez les instructions ci-dessous.

## Démarrer un nouveau projet

À chaque fois que vous démarrez un nouveau projet, vous devez répêter les tâches suivantes :

- 4. ajouter le nom de domaine dans le fichier `hosts`
- 5. ajoutez un vhost dans la config d'Apache
- 6. créer le dossier du projet
- 7. tester

## 1. Activer les vhosts

Vous devez activer les vhosts d'Apache pour pouvoir utiliser les noms de domaine locaux.

### Wamp

Ouvrez votre éditeur de code.

Ouvrez le fichier `C:\wamp64\bin\apache\apache2.4.9\conf\httpd.conf`.

Recherchez le mot clé `vhosts` et trouvez la ligne suivante :

    #Include conf/extra/httpd-vhosts.conf

Activez la ligne en supprimant le symbole dièse en début de ligne :

    Include conf/extra/httpd-vhosts.conf

### Mamp

Ouvrez votre éditeur de code.

Ouvrez le fichier le fichier `/Applications/MAMP/conf/apache/httpd.conf`.

Recherchez le mot clé `vhosts` et trouvez la ligne suivante :

    #Include /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf

Activez la ligne en supprimant le symbole dièse en début de ligne :

    Include /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf

### Xampp

Ouvrez votre éditeur de code.

Ouvrez le fichier `/Applications/XAMPP/etc/httpd.conf`.

Recherchez le mot clé `vhosts` et trouvez la ligne suivante :

    #Include etc/extra/httpd-vhosts.conf

Activez la ligne en supprimant le symbole dièse en début de ligne :

    Include etc/extra/httpd-vhosts.conf

## 2. Sauvegarder les vhosts d'usine

Il est recommandé de sauvegarder la configuration des vhosts d'usine « au cas où ».

### Wamp

Ouvrez l'explorateur de fichier.

Trouvez le fichier :

    C:\wamp64\bin\apache\apache2.4.9\conf\extra\httpd-vhosts.conf

Renommer-le :

    C:\wamp64\bin\apache\apache2.4.9\conf\extra\httpd-vhosts.conf.original

### Mamp

Ouvrez Finder.

Trouvez le fichier :

    /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf

Renommer-le :

    /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf.original

### Xampp

Ouvrez Finder.

Trouvez le fichier :

    /Applications/XAMPP/etc/extra/httpd-vhosts.conf

Renommer-le :

    /Applications/XAMPP/etc/extra/httpd-vhosts.conf.original

## 3. Préparez votre configuration de vhosts

### Wamp

Copiez le fichier `wamp-httpd-vhosts.conf` dans le dossier `C:\wamp64\bin\apache\apache2.4.9\conf\extra\` et renommez-le `httpd-vhosts.conf`.

### Mamp

Copiez le fichier `mamp-httpd-vhosts.conf` dans le dossier `/Applications/MAMP/conf/apache/extra/` et renommez-le `httpd-vhosts.conf`.

### Xampp

Copiez le fichier `xampp-httpd-vhosts.conf` dans le dossier `/Applications/XAMPP/etc/extra/` et renommez-le `httpd-vhosts.conf`.

## 4. Ajouter le nom de domaine dans le fichier `hosts`

### Windows

Éxécuter votre éditeur de code en tant qu'administrateur.

Ouvrez le fichier `C:\Windows\System32\drivers\etc\hosts`.

Ajoutez l'adresse IP et le nom de domaine suivants :

    127.0.0.1 example.test

Enregistrez et quittez votre éditeur de code.

### MacOS

Ouvrez votre éditeur de code.

Ouvrez Finder.

Dans le menu de Finder, cliquez sur `Go -> Go to folder` (`Aller -> Aller dans le répertoire` en français).

Dans la boîte de dialogue, tapez `/etc/hosts` puis valider.

Finder affiche le fichier `/etc/hosts`.

Pour ouvrir le fichier `/etc/hosts`, faites un drag'n'drop dans votre éditeur de code ou un click droit puis `Open with` (`Ouvrir avec` en français).

Alternativement, vous pouvez utiliser le terminal pour ouvrir le fichier `/etc/hosts` avec atom (ou un autre éditeur de code) :

    open -a Atom /etc/hosts

Ajoutez l'adresse IP et le nom de domaine suivants :

    127.0.0.1 example.test

Enregistrez, tapez votre mot de passe et quittez votre éditeur de code.

### Linux

Ouvrez un terminal.

Tapez la commande suivante : `sudo nano /etc/hosts`

Ajoutez l'adresse IP et le nom de domaine suivants :

    127.0.0.1 example.test

Enregistrez et quittez `nano`.

Pour enregistrer, appuyez sur `CTRL + O` puis valider avec la touche `ENTER` (`ENTRÉE` en français).

Pour quitter, appuyez sur `CTRL + X`.

## 5. Ajouter un vhost dans la config d'Apache

### Wamp

Avec votre éditeur de code, ouvrez le fichier `C:\wamp64\bin\apache\apache2.4.9\conf\extra\httpd-vhosts.conf`.

Dupliquez le bloc `example.test`.

Supprimez les dièses `#` en début de ligne.

Adaptez le nom de domaine à votre projet.

### Mamp

Avec votre éditeur de code, ouvrez le fichier `/Applications/MAMP/conf/apache/extra/httpd-vhosts.conf`.

Dupliquez le bloc `example.test`.

Supprimez les dièses `#` en début de ligne.

Adaptez le nom de domaine à votre projet.

### Xampp

Avec votre éditeur de code, ouvrez le fichier `/Applications/XAMPP/etc/extra/httpd-vhosts.conf`.

Dupliquez le bloc `example.test`.

Supprimez les dièses `#` en début de ligne.

Adaptez le nom de domaine à votre projet.

## 6. Créer le dossier du projet

### Wamp

Ouvrez l'explorateur de fichier.

Dans le dossier `C:\wamp64\www`, créez un dossier `example.test`.

Dans le dossier `C:\wamp64\www\example.test`, créez un fichier `index.html` avec un contenu simple (par exemple `Hello example.test!`).

### Mamp

Ouvrez Finder.

Dans le dossier `/Applications/MAMP/htdocs`, créez un dossier `example.test`.

Dans le dossier `/Applications/MAMP/htdocs/example.test`, créez un fichier `index.html` avec un contenu simple (par exemple `Hello example.test!`).

### Xampp

Ouvrez Finder.

Dans le dossier `/Applications/XAMPP/htdocs`, créez un dossier `example.test`.

Dans le dossier `/Applications/XAMPP/htdocs/example.test`, créez un fichier `index.html` avec un contenu simple (par exemple `Hello example.test!`).

## 7. Tester

Redémarrez Apache.

Ouvrez votre navigateur web.

Ouvrez l'url `http://example.test`. Le contenu simple du fichier `index.html` devrait s'afficher (par exemple `Hello example.test!`).

## 8. Trouble shooting

Vérifiez qu'il n'y a pas de coquille dans les noms de domaine que vous avez créé dans :

- le fichier `hosts`
- le fichier `httpd-vhosts.conf`
- les noms de dossiers

Si vous avez défini un port autre que le port 80 pour Apache, pensez à rajouter le port dans l'url (`http://example.test:8000` par exemple).

Avec wamp, assurez-vous que tous les fichiers `dll` sont bien installés. La page [http://wampserver.aviatechno.net/](http://wampserver.aviatechno.net/) permet de télécharger un fichier zip avec toutes les `dll` nécessaires (voir en bas de page).

## Licence

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/fr/"><img alt="Licence Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/3.0/fr/88x31.png" /></a><br />Ce(tte) œuvre est mise à disposition selon les termes de la <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/fr/">Licence Creative Commons Attribution - Pas d’Utilisation Commerciale - Partage dans les Mêmes Conditions 3.0 France</a>.

