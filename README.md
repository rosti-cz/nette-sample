Roští.cz Nette ukázková aplikace
================================

Tato aplikace slouží jako šablona a zároveň průvodce nastavením Nette na hostingu [Roští.cz][1].

Instalace na serveru
--------------------

Přihlašte se na server pomocí SSH přístupu a spusťte následující příkazy.

Nejdříve odstraníme výchozí složky, které jsou součástí výchozí instalace php aplikace na roští.cz:

    rm -rf /srv/app
    rm -rf /srv/webroot
    
Stáhneme tento repozitář pomocí gitu:

    git clone https://github.com/rosti-cz/nette-sample.git app
    
Nainstalujeme závislosti:

    cd /srv/app && composer install
    
Ještě přidáme lokální konfiguraci. Údaje uvnitř samozřejmě můžete měnit.
 
    mv /srv/app/app/config/saple-config.local.neon /srv/app/app/config/config.local.neon
    
Vytvoříme symlink do webrootu:

    ln -s /srv/app/www/ /srv/webroot
    
_Díky tomu bude php kód aplikace oddělen od webrootu._


Nyní stačí jen přistoupit na url, kterou máte připojenou k aplikaci.

[1]:  http://rosti.cz
