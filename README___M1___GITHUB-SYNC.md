# Synchronisieren eines Repositories mit GitHub

## Einleitung

Der Einfacheit halber wird auf die Konsolenbefehle verzichtet, und nur der Vorgang über die Visual Code GUI dargestellt.

Für detailiierte Fragen zu Git und dessen Funktionsweise, Terminilogi und und Befehle studieren Sie die Hilfeseiten im Netz: z.B:

Youtube Git Tutorial:
<https://www.youtube.com/watch?v=MgnRFZJ7M2s>

ProGit Book:
<https://git-scm.com/book/en/v2>

## Voraussetzung

- OS: Windows 10 / 11
- GitHub Konto

## GitHub Konto

Stellen Sie sicher, das sie bereits ein Konto bei GitHub besitzen.

<https://github.com/login>

Verwenden Sie ihren Firmen-Login. Sollten Sie keinen Zugang besitzen, wenden Sie sich an ihre Fachperson, um diesen zu beantragen.

## Stellen Sie sicher, das Git auf ihrem Gerät installiert ist

Sie können Git herunterladen und installieren:

<https://git-scm.com/downloads/win>

oder den Windows-Paket-Manager "winget" verwenden (sofern vorhanden)

```ps
$ winget install --id Git.Git -e --source winget
```

**die Installation werden Admin-Rechte benötigt.**

Damit der Git Befehl in der Konsole bekannt ist, öffnen Sie eine neues konsolenfenster.

Jeder Commit in Git wird mit einer Identität verbunden. Daher konfigurieren Sie global einmalig ihre Daten Werte:

Ersetzen Sie den Namen "Hans Muster" und die E-Mail-Adresse "hans.muster@firma.com" mit Ihren Werten.

```ps
$ git config --global user.name "Hans Muster"
$ git config --global user.email hans.muster@firma.com"
```

## Verwenden Sie Visual Code zur Synchronisation

Klicken Sie im VSCode auf Source-Control

![1.png](/assets/m1/1.png "Title: 1.png")

Falls VSCode noch nicht am GitHun angemeldet war, folgen Sie den Anweisungen:

![6.png](/assets/m1/6.png "Title: 6.png")

![7.png](/assets/m1/7.png "Title: 7.png")

![8.png](/assets/m1/8.png "Title: 8.png")

Wählen Sie einen Namen für das Repository auf Github (standarmässig wird der lokale Verzeichnisname vorgeschlagen)

![2.png](/assets/m1/2.png "Title: 2.png")

Wählen Sie die Dateien aus, welche initial hochgeladen werden sollen:

![3.png](/assets/m1/3.png "Title: 3.png")

Falls notwendig, authentifizieren sie VSCode über den Browser um den Sync auszuführen.

![9.png](/assets/m1/9.png "Title: 9.png")

Das lokale Repository sollte nun auf GitHub ersichtlich sein:

![4.png](/assets/m1/4.png "Title: 4.png")

Zukünftig können Sie neue die Modifikationen an den Dateien über VSCode und die Source-Control tracken: "stagen", "commiten" und "veröffentlichen".

![5.png](/assets/m1/5.png "Title: 5.png")

## Wichtig

### Synchronisieren Sie jeweils nur einen Codebase pro Repository

- ein Repository für das Angular Projekt
- ein Repository für das React Projekt

### Niemals Sicherheitsrelevante Daten synchronisieren

Stellen Sie sicher das Passwörter, IP-Adressen, API-keys, etc nicht zu GitHun hochgeladen werden. Stellen Sie sicher das Dateien oder Verzeichnisse über die Daten ".gitignore" von der Synchronisation ausgeschlossen sind.
