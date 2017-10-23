# Git Merge Übung

Mit dieser Aufgabe sollen Sie den Umgang mit Remotes, Branches und dem Zusammenführen von Branches (`merge`) üben.

Zu diesem Zweck finden Sie in diesem Repository 9 Branches, die schrittweise eine Liste der Planeten im Sonnensystem beschreiben. Ihre Aufgabe besteht darin, diese Branches in der durch die Namen angegebenen Reihenfolge (`1-..`, `2-..`, etc.) in den `master`-Branch zu `mergen` und die dabei entstehenden Konflikte zu lösen.
Abschließend sollen die Branches `8-a...` und `8-b...` zusammengeführt werden. Diese Branches enthalten sich widersprechende Implementierungen, so dass Sie sich nach dem Merge für eine der Varianten entscheiden müssen und die Dateien entsprechend anpassen müssen. Dies kann Ihnen in größeren Projekten leicht passieren.

## Tests

Das Repository enthält Tests, mit denen sie nach jedem Merge sicherstellen können, ob sie sich in einem gültigen Zustand befinden.

Die Tests können Sie mit Gradle oder in ihrer IDE starten. Um die Tests mit Gradle auszuführen, können Sie folgenden Aufruf verwenden:

* macOs/Linux: `./gradlew test`
* Windows: `gradle.bat test`

## Hinweise:

Mit dem Befehl `git branch -a` bekommen Sie eine Liste aller im Repository verfügbaren Branches angezeigt:

```
* master                                    989e2a7 ...
  remotes/origin/1-title                    3b51963 ...
  remotes/origin/2-first-planet             8079191 ...
  remotes/origin/3-second-and-third-planet  54fa567 ...
  remotes/origin/4-mars-test                ab49240 ...
  remotes/origin/5-mars                     6d63f11 ...
  remotes/origin/6-outer-planets            313c795 ...
  remotes/origin/7-pluto                    8bc3467 ...
  remotes/origin/8-a-change-title-for-pluto 58ac725 ...
  remotes/origin/8-b-pluto-is-not-a-planet  cdd2f5f ...
  remotes/origin/HEAD                       -> origin/master
  remotes/origin/master                     989e2a7 ...
```

Die Branches existieren zunächst nur in dem Remote (hier `origin`). 
Sie können den Branch zunächst lokal auschecken und dann die lokale Version mergen:

```
git checkout -b 1-title --track origin/1-title
git checkout master
git merge 1-title
```

Alternativ können Sie direkt den remote-Branch mergen. Hierfür können Sie, ausgehend von dem `master`-Branch, den git Befehl `git merge origin/<branch-name>` verwenden.
