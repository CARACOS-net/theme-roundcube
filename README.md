# theme-roundcube

A fork of [skins/elastic](https://github.com/roundcube/roundcubemail/tree/master/skins/elastic)
with some changes

## Installation
Move the Caracos skin folder to the Root location of the roundcube installation and adjust ownership

```
 sudo rm -rf /var/www/roundcube/skins/caracos;
 sudo mv ./caracos /var/www/roundcube/skins/caracos;
 sudo chown roundcube:www-data -R /var/www/roundcube/skins/caracos
```

## Compile css files

If you make some changes on the css (colors for example), you need to recompile css files

```
 apt install nodejs npm
 npm install -g less
 npm install -g less-plugin-clean-css

 lessc --clean-css="--s1 --advanced" styles/styles.less > styles/styles.min.css
 lessc --clean-css="--s1 --advanced" styles/print.less > styles/print.min.css
 lessc --clean-css="--s1 --advanced" styles/embed.less > styles/embed.min.css
```

## Make it a default theme

Create /var/www/roundcube/config/local.inc.php with
```
<?php
$config['skin'] = "caracos";
```

## References
- https://github.com/roundcube/roundcubemail/wiki/Skins
