# apache

Ce tuto montre comment configurer apache et des noms de domaine locaux (`http://test.dev` par exemple).

Il s'applique à :

- wamp (windows)
- mamp (macos)
- xampp (macos)

Notez que **vhost = virtual host**

## 1. configurez vos noms de domaine <small>(fichier `hosts`)</small>

### windows

Éxécuter votre éditeur de code en tant qu'administrateur.

Ouvrez le fichier `C:\Windows\System32\drivers\etc\hosts`.

Ajoutez l'adresse ip et le nom de domaine suivants :

    127.0.0.1 test.dev

Créez-en d'autres si besoin.

Enregistrez et quittez votre éditeur de code.

### macos

Ouvrez votre éditeur de code.

Ouvrez Finder.

Dans le menu de Finder, cliquez sur `Go -> Go to folder` (`Aller -> Aller dans le répertoire` en français).

Dans la boîte de dialogue, tapez `/etc/hosts` puis valider.

Finder affiche le fichier `/etc/hosts`.

Pour ouvrir le fichier `/etc/hosts`, faites un drag'n'drop dans votre éditeur de code ou un click droit puis `Open with` (`Ouvrir avec` en français).

Alternativement, vous pouvez utiliser le terminal pour ouvrir le fichier `/etc/hosts` avec atom (ou un autre éditeur de code) :

    open -a Atom /etc/hosts

Ajoutez l'adresse ip et le nom de domaine suivants :

    127.0.0.1 test.dev

Créez-en d'autres si besoin.

Enregistrez et tapez votre mot de passe.

### linux

Ouvrez un terminal.

Tapez la commande suivante : `sudo nano /etc/hosts`

Ajoutez l'adresse ip et le nom de domaine suivants :

    127.0.0.1 test.dev

Ajoutez-en d'autres si besoin.

Enregistrez et quittez `nano`.

Pour enregistrer, appuyez sur `CTRL + O` puis valider avec la touche `ENTER` (`ENTRÉE` en français).
Pour quitter, appuyez sur `CTRL + X`.

## 2. configurez vos vhosts <small>(fichier `httpd-vhosts.conf`)</small>

**Attention** : si vous utilisez wamp, votre installation est peut-être en 32 bit. Wamp se trouve alors dans `C:\wamp` et non `C:\wamp64`. Adaptez les instructions ci-dessous.

### 2.1 activez les vhosts

#### wamp

Ouvrez votre éditeur de code.

Ouvrez le fichier `C:\wamp64\bin\apache\apache2.4.9\conf\httpd.conf`.

Recherchez le mot clé `vhosts` et trouvez la ligne suivante :

    #Include conf/extra/httpd-vhosts.conf

Activez la ligne en supprimant le symbole dièse en début de ligne :

    Include conf/extra/httpd-vhosts.conf

#### mamp

Ouvrez votre éditeur de code.

Ouvrez le fichier le fichier `/Applications/MAMP/conf/apache/httpd.conf`.

Recherchez le mot clé `vhosts` et trouvez la ligne suivante :

    #Include /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf

Activez la ligne en supprimant le symbole dièse en début de ligne :

    Include /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf

#### xampp

Ouvrez votre éditeur de code.

Ouvrez le fichier `/Applications/XAMPP/etc/httpd.conf`.

Recherchez le mot clé `vhosts` et trouvez la ligne suivante :

    #Include etc/extra/httpd-vhosts.conf

Activez la ligne en supprimant le symbole dièse en début de ligne :

    Include etc/extra/httpd-vhosts.conf

### 2.2 sauvegardez les vhosts d'usine

#### wamp

Ouvrez l'explorateur de fichier.

Trouvez le fichier :

    C:\wamp64\bin\apache\apache2.4.9\conf\extra\httpd-vhosts.conf

Renommer-le :

    C:\wamp64\bin\apache\apache2.4.9\conf\extra\httpd-vhosts.conf.original

#### mamp

Ouvrez Finder.

Trouvez le fichier :

    /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf

Renommer-le :

    /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf.original

#### xampp

Ouvrez Finder.

Trouvez le fichier :

    /Applications/XAMPP/etc/extra/httpd-vhosts.conf

Renommer-le :

    /Applications/XAMPP/etc/extra/httpd-vhosts.conf.original

### 2.3 créez vos vhosts

#### wamp

Copiez le fichier `wamp-httpd-vhosts.conf` dans le dossier `C:\wamp64\bin\apache\apache2.4.9\conf\extra\` et renommez-le `httpd-vhosts.conf`.

Ouvrez votre éditeur de code.

Ouvrez le fichier `httpd-vhosts.conf` et créez les vhosts qui correspondent aux noms de domaine que vous avez créé dans le fichier `hosts`.
Dupliquez le bloc `test.dev` et adaptez-le à vos besoins.

#### mamp

Copiez le fichier `mamp-httpd-vhosts.conf` dans le dossier `/Applications/MAMP/conf/apache/extra/` et renommez-le `httpd-vhosts.conf`.

Ouvrez votre éditeur de code.

Ouvrez le fichier `httpd-vhosts.conf` et créez les vhosts qui correspondent aux noms de domaine que vous avez créé dans le fichier `hosts`.
Dupliquez le bloc `test.dev` et adaptez-le à vos besoins.

#### xampp

Copiez le fichier `xampp-httpd-vhosts.conf` dans le dossier `/Applications/XAMPP/etc/extra/` et renommez-le `httpd-vhosts.conf`.

Ouvrez votre éditeur de code.

Ouvrez le fichier `httpd-vhosts.conf` et créez les vhosts qui correspondent aux noms de domaine que vous avez créé dans le fichier `hosts`.
Dupliquez le bloc `test.dev` et adaptez-le à vos besoins.

## 3. organisez votre dossier web

### wamp

Ouvrez l'explorateur de fichier.

Dans le dossier `C:\wamp64\www`, créez un dossier `default`. Déplacez-y tous les dossiers et fichiers présents dans `C:\wamp64\www`.

Dans le dossier `C:\wamp64\www`, créez un dossier `test.dev`. Dans le dossier `C:\wamp64\www\test.dev`, créez un fichier `index.html` avec un contenu simple (par exemple `domaine : test.dev`).

Dans le dossier `C:\wamp64\www`, créez les dossiers qui correspondent aux noms de domaine que vous avez créé dans le fichier `hosts`. Dans chaque dossier, créez un fichier `index.html` avec un contenu simple (par exemple `domaine : test.dev`).

### mamp

Ouvrez Finder.

Dans le dossier `/Applications/MAMP/htdocs`, créez un dossier `default`. Déplacez-y tous les dossiers et fichiers présents dans `/Applications/MAMP/htdocs`.

Dans le dossier `/Applications/MAMP/htdocs`, créez un dossier `test.dev`. Dans le dossier `/Applications/MAMP/htdocs/test.dev`, créez un fichier `index.html` avec un contenu simple (par exemple `domaine : test.dev`).

Dans le dossier `/Applications/MAMP/htdocs`, créez les dossiers qui correspondent aux noms de domaine que vous avez créé dans le fichier `hosts`. Dans chaque dossier, créez un fichier `index.html` avec un contenu simple (par exemple `domaine : test.dev`).

### xampp

Ouvrez Finder.

Dans le dossier `/Applications/XAMPP/htdocs`, créez un dossier `default`. Déplacez-y tous les dossiers et fichiers présents dans `/Applications/XAMPP/htdocs`.

Dans le dossier `/Applications/XAMPP/htdocs`, créez un dossier `test.dev`. Dans le dossier `/Applications/XAMPP/htdocs/test.dev`, créez un fichier `index.html` avec un contenu simple (par exemple `domaine : test.dev`).

Dans le dossier `/Applications/XAMPP/htdocs`, créez les dossiers qui correspondent aux noms de domaine que vous avez créé dans le fichier `hosts`. Dans chaque dossier, créez un fichier `index.html` avec un contenu simple (par exemple `domaine : test.dev`).

## testez

Redémarrez apache.

Ouvrez votre navigateur web.

Ouvrez l'url `http://test.dev`. Le contenu simple du fichier `index.html` devrait s'afficher (par exemple `domaine : test.dev`).

## trouble shooting

Vérifiez qu'il n'y a pas de coquille dans les noms de domaines que vous avez créé dans :

- le fichier `hosts`
- le fichier `httpd-vhosts.conf`
- les noms de dossiers

Avec wamp, assurez-vous que toutes les fichiers `dll` sont bien installés. La page [http://wampserver.aviatechno.net/](http://wampserver.aviatechno.net/) permet de télécharger un fichier zip avec toutes les `dll` nécessaires (voir en bas de page).

## licence

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/fr/"><img alt="Licence Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/3.0/fr/88x31.png" /></a><br />Ce(tte) œuvre est mise à disposition selon les termes de la <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/fr/">Licence Creative Commons Attribution - Pas d’Utilisation Commerciale - Partage dans les Mêmes Conditions 3.0 France</a>.
