# CMS Contao Tutorial

Derzeit beschäftige ich mich mit dem Content Management System Contao und möchte mein Wissen teilen.

Die Installation mit dem Contao Manager ist bei mir leider fehlgeschlagen. Aus diesem Grund habe ich mich für eine Installation mit dem Composer entschieden.

So könnt ihr Contao mit dem Composer in /Application/MAMP/htdocs in MAMP istallieren:
```php
composer create-project contao/managed-edition contao-tutorial 4.13
```

Um automatische in das Installtool zu gelangen öffnet ihr in eurem Browser folge Url. Hier könnt ihr auch eure Datebank angeben.

```php
localhost/contao-tutorial/public
```

Nachdem der Composer mit der Installation fertig ist, könnt ihr euch einen Virtual Host anlegen.
Das Vorgehen in MAMP ist folgendermaßen:

Zuerst öffnet ihr diese Datei:
```php
Applications/MAMP/conf/apache/extra/httpd-vhost.conf
```

Der Virtual Host sieht dann so aus:

```php
<VirtualHost *:80>
    DocumentRoot "/Applications/MAMP/htdocs/contao-tutorial/public/"
    ServerName contao-tutorial.local.com
    <Directory "/Applications/MAMP/htdocs/contao-tutorial/public/">
        AllowOverride All
        Order Allow,Deny
        Allow from All
    </Directory>
</VirtualHost>
```

Zuletzt muss der Virtual Host noch in die /etc/hosts eingetragen werden:
```php
127.0.0.1     contao-tutorial.local.com
```

Mit diesem Link könnt ihr auch im Admin einloggen oder das Frontend besuchen:
```php
http://contao-tutorial.local.com/contao/login
```

Das wars auch schon. Vielleicht konnte ich ja dem einen oder anderen helfen.
