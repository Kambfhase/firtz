firtz
=====

firtz podcast publisher

firtz 0.8

Podcastpublishing mit EDLIN

+++ ACHTUNG +++ 

Das hier ist unterhalb 1.0. Könnte man beta nennen, klingt nur doof heutzutage.
Solltest Du damit einen Podcast veröffentlichen wollen: Sei gewarnt, es wird schmerzhaft, denn ich garantiere Dir nicht, dass die Handhabung bleibt wie sie ist.
Ordnernamen, Ordnerorte, Dateinamen, Formate können und werden sich ändern. Solltest Du nicht experiementierfreudig sein, warte lieber noch ein oder zwei Wochen oder frag mich ruhig persönlich.

+++ ACHTUNG +++

Du hast offensichtlich den Drang, entweder diesen Kram hier auszuprobieren, oder einen Podcast aus der Taufe zu heben.
Was auch immer Dich dazu bewogen hat, firtz auszuprobieren: Gute Idee :)

Worum geht es?
Um einen Podcast zu veröffentlichen, reichen im Grunde zwei Dinge: Audiodateien im Web und irgendwo eine XML-Datei, die den Feed beschreibt. Alles andere ist Beiwerk, das mehr oder minder nötig und arbeitsintensiv ist.

Warum aber an vielen Stellen so viel Arbeit machen, so viel Ballast herumschleppen? Wieso ein Wordpress, wenn man alle zwei Monate mal was veröffentlicht? Wieso eine SQL-Datenbank für fünf Artikel in einem Jahr? Wieso sich den Kopf zerbrechen über die Installation diverser Plugins, wenn es ein paar KByte XML tun?

Deshalb firtz. firtz ist das Ergebnis von knapp einskommafünf Tagen "Arbeit", die ich eigentlich nur gemacht habe, um mal wieder irgendwas zusammen zu schrauben, das halbwegs funktioniert.

Wie funktioniert das nun? Über Konfigurationsdateien. Eine für den Feed mit allgemeinen Daten und einer Datei für jede Episode mit den Details eben jener.

Aber fangen wir vorne an. Was brauchst Du? Du brauchst irgendwo Platz im Web. Das ist dann doch noch nötig... ;)
Dieser Platz im Web muss im Grunde nur eine Bedingung erfüllen: php muss ausgeführt werden können.
Datenbanken und anderen Kram braucht nicht, allerdings muss der ausführende Nutzer des Webservers in der Lage, Verzeichnisse zu erzeugen und Dateien in diese hineinzuschreiben.

Du besorgst Dir das firtz-Archiv (https://github.com/eazyliving/firtz/archive/master.zip), entpackst es in den Ordner, in dem Du das auf dem Webserver haben willst und bewegst Dich darauf hin in den Unterordner feeds/.
In diesem findest Du ein Demo-Verzeichnis. Der Name dieses Ordners, ist der zukünftige Name Deines Feeds.

Im Demo-Ordner sind zwei Dateien: feed.cfg und 001.epi. Das nicht syntaktisch zu nennende Prinzip dieser Dateien ist identisch:

\#: ist ein Kommentar nicht den ":" vergessen!

Attribute werden wie folgt notiert:

attribute:  
value

Achtet bitte darauf, dass die Attribut-Zeile alleine steht. Leerzeilen werden ignoriert, es sei denn, es geht um eine Textfeld wie summary.

An's Ende der Konfiguration kannst Du in einer neuen Zeile ein "---end---" setzen, alles dahinter wird ignoriert. Du kannst da Notizen oder Müll unterbringen ;) Ich werde das hier im Moment noch nicht weiter ausbreiten. Schau in die Dateien und spiel damit rum.

WICHTIG IST, DASS ALLE KONFIGURATIONSDATEIEN UTF8 SIND!

Wenn Du nicht aufpasst, gibt's Müsli im Feed!

Solltest Du Auphonic (http://auphonic.com/) nutzen, bist Du vermutlich ganz fein raus. Aktiviere in den Ausgangsdateien die Production-Description, sorge dafür, dass firtz sie im Dateisystem findet und schon erstellen sich die Folgen fast von selbst anhand der von Auphonic weitergereichten Metadaten. Weitere Informationen dazu finden sich in der Dokumentation.

Nehmen wir an, Du hast das soweit fertig. Wie erreichst du den Feed? Angenommen der URL zu Deinem Webserver würde http://tollerneuerpodcast.de/ lauten. Der Feed heißt ja noch demo, also wäre der URL zum RSS2-Feed:

http://tollerneuerpodcast.de/demo/

Wenn Du mehrere Audioformate nutzt, kannst Du auch z.B. http://tollerneuerpodcast.de/demo/mp3 nutzen.

Eine Webseite gibt's ja auch als Bonus. Die kannst Du für diesen Feed so erreichen: http://tollerneuerpodcast.de/demo/show
Für jede Episode gibt's dann einen eigenen Player (podlove webplayer, großartige Sache!), flattr-Buttons und auch ein disqus-Thread, so denn disqus in der Konfiguration des Feeds angegeben wurde.
Einzelne Episoden sind auch verlinkbar, indem an den Pfad der Slug der Episode (praktisch der Dateiname ohne Endung) angehangen wird: http://tollerneuerpodcst.de/demo/show/001

So, das war's für's erste. Denke dran: Du bist im Grunde Betatester. Die 1.0 wird erreicht werden, wenn ich zufrieden bin. Also ~2015.
Es sind jetzt schon features drin, die ich nicht erwähnt habe. Neue sind schon im Kopf, aber nicht ausgeführt. Und Du hast bestimmt auch welche!

Melde Dich. Entweder unter info@hoersuppe.de oder auf Twitter an @the_firtz!

Weil's wichtig ist: Ich habe dieses Zeug mit fatfree framework (https://github.com/bcosca/fatfree) und bootstrap (http://twitter.github.com/bootstrap/) zusammengeschraubt.
Weiterhin hilft der Podlove Webplayer (https://github.com/gerritvanaaken/podlove-web-player) massiv dazu bei, dass alles halbwegs hübsch aussieht :)
