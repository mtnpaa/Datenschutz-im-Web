# Datenschutz-im-Web
##### eine kleine Zusammenfassung wichtiger Add-ons, Einstellungen und Sammlung von interessanten Texten zum Thema

## Datenschutz in der BRD

Datenschutz beruht in Deutschland auf den beiden ersten beiden Artikeln des Grundgesetzes (Art.2 | GG, Art1|GG)
Das Bundesverfassungsgericht hat im sogenannten Volkszählungsurteil im Jahr 1983 daraus das "Recht auf informelle Selbstbestimmung" abgeleitet
In den Datenschutzgesetzen des Bundes und der Länder sowie in Spezialgesetzen wie dem Telemediengesetz (TMG) oder dem Telekommunikationsgesetz (TKG) ist der Datenschutz im Einzelnen geregelt.

Einer der wesentlichen Grundsätze des Datenschutzes ist es, dass die Erhebung, Verarbeitung und Nutzung von personenbezogenen Daten im Prinzip verboten ist, es sei denn, es gibt eine klare Rechtsgrundlage oder der Einzelne gibt seine ausdrückliche Zustimmung. [6]

## Blockieren von Schadsoftware
Gängige Methoden zum Ableiten von Daten über Identitäten & Präferenzen während der Webseiteninteraktion


Cookies = Textdateien, die von Webseiten auf dem Computer abgelegt werden. Diese sind problematisch, wenn sie eine ID besitzen, die es ermöglicht das Nutzerverhalten auch übere mehre Session zu protokollieren.

-> Cookies blockieren und automatischen löschen nach Session, per Browserkonfiguration



Fingerprint = über Javascript können geräte- und softwarespezifische Daten (Betriebssystem, Browserversionsnummer, Browsersettings, Browserplugins, Zeitzone, Auflösung des Bildschirms, Schriftarten etc.) ausgelesen werden, diese Daten ermöglichen eine eindeutige Identifizierung auch bei Nutzung eines VPN.
Fingerprint ermitteln: https://firstpartysimulator.org/, https://amiunique.org/


-> Blockieren mittels Scriptblocker


Tracker = Per Cookies oder Fingerprint werden Nutzern IDs zugeordnet und Online-Aktivitäten können protokoliert werden.


-> Blockieren mittels Scriptblocker


## Wahl des Browsers

Eingrenzung der Auswahl an Browser anhand ihrer Marktanteile im September 2021 [1]

Haupt-Datensicherheitskriterien für Web-Browser

Schließen von Sicherheitslücken (Regelmäßige Updates)
Warnung vor unsicheren Seiten
Blockieren von Tracking-Cookies
Benutzerdaten werden weitergegeben bzw. Verkauf





Chrome
Edge
Safari
Firefox
Opera




Pro
Sicherheitsupdates
Sicherheitsupdates
Sicherheitupdates
Sicherheitsupdates
integrierter Proxy, Updates


+
Blacklist
Blacklist
Blacklist von Google Diensten, unterbindet Tracking über Dritte
Blacklist von Google Diensten(deaktivierbar)
Blacklist


Contra
trackt standardmäßig über Drittanbieter Cookies, sammelt Daten aus Apps
PRISM
nur für Apple Geräte
blockt standardmäßig Tracking Cookies von Drittanbietern,
Datensammler


-
Datensammler
Datensammler
PRISM, Datensammler kein Werbeblocker, nutzt Blacklist von Google
hochgradig anpassbar, Datensammeln deaktivierbar




[2],[3],[4]
Tabelle 1: Gegenüberstellung der Browser mit den höchsten Marktanteilen unter Aspekten des Datenschutz.
Wahl des Browsers  --> Mozilla Firefox
## Wahl der Suchmaschine
Wahl der Suchmaschine wurde unter Nutzung der Testergebnisse von Stiftung Warentest 2019[5] gewählt. Hierbei wurden 10 Suchmaschinen untersucht mit jeweils 50 Suchanfragen konfrontiert. Zu den getesten Kategorien gehörten zum einen die Qualität der Suchergebnisse, der Nutzungskomfort (PC/Smartphone), das Datensendeverhalten (Android, iOS) und Mängel in der Datenschutzerklärung.
Testsieger war hier Startpage.com.
Startpage nutzt Google anonymisiert, aber die Anfrage. (keine Ip- Adresse, keine User-ID, keine Tracking-Cookies)

Abbildung 1: Suchmaschinen Test (Stiftung Warentest)
## Firefox Browserkonfiguration
Firefox Datenschutzeinstellungen

Telemetrie deaktivieren, hier werden technische Daten und Interaktionsdaten mit Mozilla geteilt


Einstellungen -> Datenschutz und Sicherheit -> Datenerhebung durch Firefox und deren Verwendung (alles deaktivieren)



Standardsuchmaschine ändern


Blockieren von Inhalten (Modi: Standard, Streng, Benutzerdefiniert)



der strenge Modus, zerstört die Webseiten
Inhaltsblockierung der einzelenen Seiten, kann dann über das Symbol i für bestimmte Webseiten freigeschalten werden


"Do Not Track"-Anfrage


im Header wird ein Request geschickt, der aber auch ignoriert werden kann und kann auch für Browser-Fingerprints verwendet werden

5.about:config

hier können die Einstellungen genauer benutzerdefiniert eingestellt werden
-media.peerconnection.enabled  (WebRTC) = false echte IP-Adresse kann ansonsten ausgelesen werden https://restoreprivacy.com/webrtc-leaks/


-privacy.resistFingerprinting = true Firefox wird widerstandsfähiger gegen Browser-Fingerabdrücke
Achtung!
https://restoreprivacy.com/browser-fingerprinting/
-privacy.trackingprotection.fingerprinting.enabled = true Firefox 67+ block Fingerprinting
-privacy.trackingprotection.cryptomining.enabled  = trueFirefox 67+ block cryptominer
-** privacy.firstparty.isolate = true** blockiert Tracking über mehre Domains, weil Cookies auf der Erstanbiert domain isoliert sind
-geo.enabled = false deaktiviert die Standortverfolgung
-media.navigator.enabled = false Websiten können nicht den Kamera- und Mikrofonstatus verfolgen
-network.cookie.cookieVerhalten Intergertyp (0,1,2,3,4)
-network.cookie.lifetimePolicy = 2 (Cookies löschen, Empfehlung: 2 = Nur für die aktuelle Sitzung akzeptieren)
-network.prefetch-next = false (verhindert vorab Abrufen einer Webseite, verschlechtert Performanz)
-webgl.disabled = true (WebGL = Web Graphics Library, Java Script Programmierschnittstelle, Darstellung von 3D-Grafiken, potenzielles Sicherheitsrisiko)
-dom.event.clipboardevents.enabled = false (verhindert Benachrichtigungen an die Webseite über Kopieren, Einfügen, Ausschneiden von Inhalten)
-**empfohlene Privacy Add-Ons
-uBlock Origin (Werbung- & Tracking-Filter),

HTTPS Everywhere (z.B. Verhindern vom Weiterleiten auf alte HTTP-Seitenversionen),
Decentraleyes (lokale Bereitstellung von Bibliotheken um Zugriff auf Fremdbibliotheken zu vermeiden & damit Tracking)
Cookie AutoDelete
PrivacyBadger (blockiert nur drittanbieter Cookies, Filterliste wird nach und nach aufgebaut
NoScript (Scriptblocker)

## Temporary Containers

https://addons.mozilla.org/de/firefox/addon/temporary-containers/
Container sind individuelle Speicherblegungen, jeder Tab im Browser hat seinen eigenen Storage, Cookie.
-jedes Tab und jedes Fenster sind dann in einem isolierten Modus, Informationen können nicht über anderen Tabs erhalten werden
Nachteil: innerhalb des Containers ist alles möglich (außer "in neuem Tab öffnen") => Eine ordentliche Browser-Konfiguration ist trotzdem erforderlich!

## uMatrix


Browser-Addon von Raymond Hill [Link] (https://github.com/gorhill/uMatrix), GPL v3 Lizenz


webbasierte Firewall


ermöglicht es alle Anfragen des Browsers per Point& Click zu blockieren oder freizuschalten.


zentrale Bedienoberfläche ist eine Matrix, in der alle Arten von Anfragen zu sehen sind.



Abbildung 2: uMatrix


(linke Spalte) Domain-Namen


allgemein aber auch sehr spezifisch


(Tabellenkopf) Arten von Anfragen
-Cookies, CSS, Grafik, Medien, Skript, XHR, Frame, Andere


In dieser Matrix können dann die einzelnen Zellen, aber auch gesamte Zeilen und Spalten blockiert(rot) oder freigeschalten (grün) werden.

Rot --> Anfrage blockiert (verlässt nicht den Browser)
Grün --> Anfrage offen, wartet auf Antwort

Modus ("Red")
Blockiere alle Anfragen, erlaube nichts.
Seiten funktionieren kaum und müssen nach und nach "freigeschalten" werden.
Einstellungen
Es gibt permanente Regeln wie Webseiten bei dem ersten Aufruf angefragt werden sollen. Diese Regeln sind fest und können nur über temporäre Regeln verändert werden, wenn diese abgespeichert (Schloß-Icon) werden.
Bspw. kann hier  **script block hinzugefügt werden, somit ist standardmäßig bei jedem neuen Aufruf einer Webseite, JavaScript bereits blockiert.
Herangehensweise zur Nutzung
Erstmal alles als im Internet als "feindlich" ansehen, dahingehend alles blockieren. Aufgerufen Webseiten sind meist kaputt. Nun werden nach und nach vertrauenswürdige Anfragen freigeschalten und somit werden die Webseiten wieder funktionstüchtig. Dieser Ablauf wiederholt sich für jede besuchte Webseite. Es ist ein schrittweiser Ansatz, das gewohnte Surerlebnis zu erarbeiten.
Pro

leichtverständliche Benutzeroberfläche
volle Kontrolle über die Anfragen des Browsers

Contra

gewohnte Internetnutzung muss erst aufgebaut werden

## Fazit
Datensicherheit wird einem nicht geschenkt, man muss dafür was machen.
Aufgrund von den Firefox-Settings, kann die Standardsuchmaschine geändert werden und die Telemetriedaten  an Mozilla deaktiviert werden.  Auch Cookies, Skripte der Aktivitätenverfolgung, Fingerprinter, Seitenübergreifende Cookies, werden standardmäßig von Firefox geblockt, nach eigenen Angaben, ausgewogen zwischen Schutz und Leistung. Hier ist es ebenfalls möglich den Modus "streng" zu wählen. Es wird aber gewarnt das einige Seiten, dann nicht richtig funktionieren. Hier wäre eine Untersuchung in der Usability zw. uMatrix und den Benutzerdefinierten Settings zu untersuchen.
Über about:config in Firefox können benutzerdefinierte Einstellungen gewählt werden, fraglich ist, ob dies nicht schon den Browserfingerprint deutlicher macht.
Mittels zwei Firefox Add-ons(uMatrix, Temporay Containers), kann die Datenerfassung und Protokollierung erschwert werden.
Mittels uMatrix hat der Nutzer, die volle Kontrolle über seine Requests und kann unteranderem somit kritisches JavaScript blockieren. Die Nutzung des Add-on, "zerstört" aufgerufenen Websiten und erschwert das Surf-Verhalten erstmal, nach gewissen Zeit, wurde aber ein vertrauert Teil des Web schrittweise "erarbeitet".
Mittels Temporary Containers kann das Tracking zwischen einzelnen Tabs und Fenster, während einer Session unterbunden werden. Denoch  ist es möglich mittels des BrowserFingerprints, Nutzer zuzordnen.
Kritisch zu sehen ist, dass dieses Add-on nicht von Mozilla aktiv auf seine Sicherheit überwacht wird.
Umso mehr Einstellungen und Addons genutzt werden, desto genauer kann der Fingerprint zugeordnet werden.
Die Kombination aus den FirefoxSettings, uMatrix und Temporary Containers, sowie eine aufmerksame Nutzung des Web, erschweren aber die persöhnliche Datenerhebung.

____________________________________________________________________________________________________________________________________________________________________
[1][Link] (https://de.statista.com/statistik/daten/studie/158095/umfrage/meistgenutzte-browser-im-internet-weltweit/) (letzter Aufruf 17.10.21)
[2] (https://computerwelt.at/news/die-wichtigsten-browser-im-grossen-privatsphaere-check/) (letzter Aufruf 17.10.21)
[3] (https://www.datenschutzexperte.de/blog/datenschutz-im-unternehmen/browser-datenschutz-welcher-browser-schuetzt-ihre-daten/) (letzter Aufruf 17.10.21)
[4] (https://www.avast.com/de-de/c-best-browsers-for-privacy), (letzter Aufruf 17.10.21)
[5] (https://www.test.de/Suchmaschinen-im-Test-Eine-schlaegt-Google-5453360-5453800/), (letzte Aufruf 17.10.21)
[6] (https://www.klicksafe.de/suchmaschinen/datenschutz-und-suchmaschinen/),(letzte Aufruf 17.10.21)


__________________________________________________________________________________________________________________________________________________________________
Abbildung 1: Test Stiftung Warentest, https://www.test.de/filestore/5454217_t201904030.pdf?path=/protected/94/21/bde1e62c-88fb-4437-afe3-675c49926acd-protectedfile.pdf&key=85C6EDF75630BA54AA143E109E5D94299797AB75, (zuletzt aufgerufen am 17.10.21)
Abbildung 2: uMatrix

__________________________________________________________________________________________________________________________________________________________________
Tabelle 1: Gegenüberstellung der Browser mit höchsten Marktanteilen unter Aspekten des Datenschutz.
