# Synchronisieren eines Repositories mit GitHub

## Einleitung

Der Einfacheit halber wird auf die Konsolenbefehle verzichtet, und nur der Vorgang über VSCode dargestellt.

Für Fragen zu Git und dessen Funktionsweise, Terminologie und Befehle studieren Sie die Hilfeseiten im Netz: z.B:

Youtube Git Tutorial:
<https://www.youtube.com/watch?v=MgnRFZJ7M2s>

ProGit Book:
<https://git-scm.com/book/en/v2>

## Voraussetzung

- OS: Windows 10 / 11
- GitHub Konto

## GitHub Konto

Stellen Sie sicher, das Sie bereits ein Konto bei GitHub besitzen.

<https://github.com/login>

Verwenden Sie ihren Firmen-Login. Sollten Sie keinen Zugang besitzen, wenden Sie sich an ihre Fachperson, damit diese mit Ihnen zusammen die Einrichtung vornimmt.

## Git Installation

Stellen Sie sicher, das Git auf ihrem Gerät installiert ist.

Sie können Git herunterladen und installieren:

<https://git-scm.com/downloads/win>

oder den Windows-Paket-Manager "winget" verwenden (sofern vorhanden)

```ps
$ winget install --id Git.Git -e --source winget
```

**Die Installation benötigt Admin-Rechte.**

Damit der Pfad zum Git Befehl in der Konsole bekannt ist, öffnen Sie ihr Terminalfenster nach der Installation neu.

Jeder Commit in Git wird mit einer Identität verbunden. Daher konfigurieren Sie global einmalig ihre Daten:

Ersetzen Sie den Namen "Hans Muster" und die E-Mail-Adresse "hans.muster@firma.com" mit Ihren Werten und führen die folgenden beide Befehle im Terminal aus:

```ps
$ git config --global user.name "Hans Muster"
$ git config --global user.email hans.muster@firma.com"
```

## Sync via VSCode

Öffnen Sie VSCode mit Ihrem Projektverzeichnis.

Klicken Sie im VSCode auf Source-Control

![1.png](/assets/m1/1.png "Title: 1.png")

Falls VSCode bisher noch nicht am GitHub angemeldet war, folgen Sie den Anweisungen:

![6.png](/assets/m1/6.png "Title: 6.png")

![7.png](/assets/m1/7.png "Title: 7.png")

![8.png](/assets/m1/8.png "Title: 8.png")

Wählen Sie einen Namen für das Repository auf Github (standardmässig wird der lokale Verzeichnisname vorgeschlagen).

Sie können unterscheiden, ob das Repository auf GitHub öffentlich zugänglich sein soll (public), oder als privat gilt mit expliziten Berechtigungen (private).

![2.png](/assets/m1/2.png "Title: 2.png")

Wählen Sie die Dateien aus, welche initial hochgeladen werden sollen:

![3.png](/assets/m1/3.png "Title: 3.png")

Falls notwendig, authentifizieren sie VSCode über den Browser um den Sync zu starten.

![9.png](/assets/m1/9.png "Title: 9.png")

Das lokale Repository sollte nun auf GitHub in Ihrem Konto ersichtlich sein:

![4.png](/assets/m1/4.png "Title: 4.png")

Zukünftig können Sie die Modifikationen an den Dateien ihres Projektes über VSCode und die Source-Control tracken: "stagen", "commiten" und "veröffentlichen".

![5.png](/assets/m1/5.png "Title: 5.png")

## Wichtig

### Synchronisieren Sie jeweils nur eine Codebase pro Repository

z.B.:

- ein Repository für das Angular Projekt
- ein Repository für das React Projekt

### Niemals Sicherheitsrelevante Daten synchronisieren

Passwörter, IP-Adressen, API-keys, usw. dürfen nie auf GitHub landen. Stellen Sie sicher, das sicherheitsrelevante Dateien oder Verzeichnisse über die Datei ".gitignore" von der Synchronisation ausgeschlossen sind.

## Source-Control Worklfow

Vereinfachte grafische Darstellung des Git Ablaufs - Local (i.e. Dev-Device) <-> Remote (i.e. GitHub)

![ablauf.png](/assets/m1/ablauf.png "Title: ablauf.png")