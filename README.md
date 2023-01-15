# Willkommen bei nagilos autodarts Hilfe !

Hier finden sich Dateien und Erklärungen die das Projekt autodarts erweitern. Der Link zu den originalen repositories findet man hier.

https://github.com/autodarts

Alles was hier vorgestellt wird basiert auf einer Debian Stable Bullseye Amd64 installation. Diese kann auf jedem beliebigen Rechner installiert werden der kompatibel ist. Diese sind schon für wenige Euros in der Bucht zu haben.

Basierend auf Debian kann man einen fertig konfigurerten Rechner erstellen. Die Anleitung dazu wird noch erstellt. Hier kommt jetzt die Anleitung für den bereits konfigurierten Rechner.

0. Einleitung

Hier werden die wichtigsten Dinge zu autodarts erklärt. Falls du doch weitere Hilfe benötigst kannst du nagilo im Discord Kanal kontaktieren.

Ich erkläre hier schnell was man tun kann. Dazu muss man (fast) immer zuerst das Programm Konsole (Terminal) starten. Links unten in der Ecke findest du den Anwendungs-Starter. Unter Anwendungen->System findest du dann das Programm Konsole. Alternativ kannst du auch konsole in die Suche eintippen, die sich öffnet sobald du auf den Anwendungs-Starter drückst.

Wenn alles geklappt hast dann hat sich ein schwarzes Fenster geöffnet in dem der Schriftzug "player@debian:~$ " zu sehen ist. Nun kann es los gehen. Im folgenden findest du immer wieder Befehle die du in der Konsole eingeben kannst. Am besten kopieren sonst vertippt man sich leicht.

Falls du nach einem Passwort gefragt wirst - das Passwort lautet autodarts !

1. Autodarts

Autodarts läuft immer sofort automatisch, so dass man weder einen Monitor noch sonst etwas braucht. Das ist der Idealzustand. Also am besten du siehst das hier gar nicht. Falls doch hier was du tun kannst.

1.1 Autodarts Stoppen

Zum stoppen von Autodarts nutzt man den folgenden Befehl

systemctl stop autodarts.service

1.2 Autodarts Starten im Hintergrund

Zum starten von Autodarts so dass der Dienst im Hintergrund läuft nutzt man folgenden Befehl

systemctl restart autodarts.service

1.2 Autodarts Starten im Vordergrund

Wenn man autodarts vorher gestoppt hat kann man das System auch im Vordergrund starten. Das ist hilfreich falls man die Ausgaben von Autodarts sehen möchte. Der Befehl dazu lautet einfach autodarts. Wenn man Autodarts im Vordergrund wieder beenden möchte drückt man <strg>+c .

autodarts

2. Konfiguration

Die Konfiguration von Autodarts befindet sich im Verzeichnis .autodarts . Achtung der erste Punkt ist wichtig, das ist ein vertecktes Verzeichnis. 

2.1 Öffnen und Editiren der Konfigurationsdatei 

Wenn du deine Board-ID und deinen Schlüssel editieren willst, dann nutzen wir am besten einen Dateimanager. Das kann man auch auf der Konsole machen aber naja mit Grafik gehts halt einfacher. Zum Starten des Dateimanagers im richtigen Verzeichnis gibt man auf der Konsole folgenden Befehl ein. Dann öffnet sich ein Fenster in dem du alle Dateien siehst, die sich gerade in deinem Konfigurationsverzeichnis befinden. Wenn du auf eine der Dateien klickst (nur ein mal !!!) dann öffnet sich ein Editor und du kannst alles anpassen. In dem Verzechnis landet später auch die Datei für die Kamerakalibrierung falls notwendig.

dolphin .autodarts

3. Teamviewer als direkte Hilfe von Extern

Ja es gibt auch direkt die Möglichkeit externe Hilfe zu bekommen. Teamviewer ist vorinstalliert. Im Anwedungs-Starter findest du unter Internet das Programm TeamViewer. Der Kontakt wird über discord hergestellt.

4. Kalibrierung der Kameras

Auf dem System ist auch alles zum Kalibrieren der Kameras installiert. Dazu muss man aber Autodarts zuerst beenden wie oben beschrieben.

4.1 Aufnehmen der Bilder

Wir wechseln zuerst in das richtige Verzechnis und starten dann das Programm zum Aufnehmen der Bilder. Dann starten wir die Bildaufnahme. Bitte die Auflösung der Kameras korrekt eintragen. Die Bilder landen im Verzechnis cam-calibration/calibrationImages. Die Bilder kann man sehen, wenn man den die Dateiverwaltung Dolphin startet und in das Verzeichnis wechselt.

cd cam-calibration
python3 main.py generate -camIds 0 2 4 -fps 30 -w 1920 -h 1080

4.2 Starten der Kalibrierung

Wieder im gleichen Verzeichnis kann man dann die Kalibrierungs starten. Auch hier wieder Auflösung anpassen. Es ensteht eine Datei distortion.json die man wieder mit Dolphin in das Verzechnis .autodarts kopieren kann. (Wer dabei Hilfe braucht kurze Nachricht - Tipp: Dolphin).

python3 main.py distortion -w 1920 -h 1080

5. Anzeigen und einstellen der Kameras

Wenn ihr die Kameras einstellen wollt dann könnt ihr das tun. Autodarts stopppen und dann folgendes auf der Konsole eingeben. Die Kameras drei Kameras haben bei mir die Nummern 0, 2 und 4 aber das kann bei euch anders sein. Stoppen wieder mit <strg>+c .

guvcview -d /dev/video4

5.1 Einstellungen dauerhaft übernehmen

Um die Einstellungen der Kameras dauerhaft zu übernehmen gibt es eine Regel, die immer wenn eine Kamera hinzugefügt wird ein Skript startet. Diese Skripte liegen im Verzeichnis .autodarts und tragen den Namen setup_video0, setup_video2, usw. . Für jede Kamera gibt es eines. Das Skript muss ausführbar sein.

chmod a+x /home/player/.autodarts/setup_video*

In dem Skript stehen dann folgende Zeilen. Die erste Zeile besagt, dass es sich um ein Skript handelt und die zweite gibt eine Nachricht an den System-Log aus. Die darauf folgenden Zeilen setzen die Einstellungen der Kamera. Diese müssen an die eigene Kamera angepasst werden. 

#!/bin/bash
logger "autodarts running camera configuration for device video2"
v4l2-ctl --set-ctrl brightness=-8 --device /dev/video2

6. Noch mehr ?

Natürlich geht noch viel viel mehr. Einfach in Discord ansprechen.

---------------------------------------------------------------------------------------------------------------------------------

Welcome to Nagilo's Autodarts Help!
Here you will find files and explanations that expand the Autodarts project. The link to the original repositories can be found here.

https://github.com/autodarts

Everything presented here is based on a Debian Stable Bullseye Amd64 installation. This can be installed on any compatible computer, which can be found for a few euros on the bay.

Based on Debian, a fully configured computer can be created. The instructions for this will be created later. Here is now the instructions for the already configured computer.

0. Introduction
Here, the most important things about Autodarts are explained. If you still need further help, you can contact Nagilo in the Discord channel.

I will explain quickly what can be done. To do this, you (almost) always have to start the Console (Terminal) program first. In the lower left corner, you will find the Application Starter. Under Applications-> System you will find the Console program. Alternatively, you can also type console in the search that opens when you press the Application Starter.

If everything worked, a black window will have opened with the text "player@debian:~$" visible. Now it can start. Below you will find commands that you can enter in the console. It is best to copy them, otherwise you can easily make typos.

If you are asked for a password - the password is autodarts!

1. Autodarts
Autodarts always runs automatically, so you don't need a monitor or anything else. This is the ideal state. So it's best if you don't see this. If you do, here's what you can do.

1.1 Stopping Autodarts

To stop Autodarts, use the following command

systemctl stop autodarts.service

1.2 Starting Autodarts in the background

To start Autodarts so that the service runs in the background, use the following command

systemctl restart autodarts.service

1.2 Starting Autodarts in the foreground

If you have stopped Autodarts before, you can also start the system in the foreground. This is helpful if you want to see the output of Autodarts. The command is simply autodarts. If you want to end Autodarts in the foreground, press +c .

autodarts

2. Configuration
The configuration of Autodarts is located in the .autodarts directory. Attention the first dot is important, this is a hidden directory.

2.1 Opening and editing the configuration file

If you want to edit your Board-ID and your key, it is best to use a file manager. This can also be done on the console, but with graphics it's easier. To start the file manager in the correct directory, type the following command on the console. A window will open where you can see all the files that are currently in your configuration directory. If you click on one of the files (only once !!!) then an editor will open and you can customize everything. Later, the file for camera calibration will also land in this directory if necessary.

dolphin .autodarts

3. Teamviewer as direct help from Extern
Yes, there is also the possibility of getting direct external help. Teamviewer is pre-installed. In the Application Starter, you will find the TeamViewer program under Internet. Contact will be made via discord.

4. Camera calibration
Everything necessary to calibrate the cameras is also installed on the system. However, Autodarts must first be stopped as described above.

4.1 Taking pictures

First, we switch to the correct directory and then start the program for taking pictures. Then we start taking pictures. Please enter the correct resolution of the cameras. The pictures land in the directory cam-calibration/calibrationImages. The pictures can be seen when you start the file manager Dolphin and switch to the directory.

cd cam-calibration python3 main.

5. Viewing and adjusting cameras
If you want to adjust the cameras, you can do it. Stop autodarts and then enter the following on the console. The three cameras have the numbers 0, 2 and 4 with me, but it can be different for you. Stop again with +c.

guvcview -d /dev/video4

5.1 Permanently apply settings

To permanently apply the camera settings, there is a rule that starts a script whenever a camera is added. These scripts are located in the .autodarts directory and are named setup_video0, setup_video2, etc. There is one for each camera. The script must be executable.

chmod a+x /home/player/.autodarts/setup_video*

The script contains the following lines. The first line indicates that it is a script and the second line sends a message to the system log. The following lines set the camera settings. These must be adapted to your own camera.

#!/bin/bash logger "autodarts running camera configuration for device video2" v4l2-ctl --set-ctrl brightness=-8 --device /dev/video2

6. More?
Of course, there is still much more. Just ask in Discord.

