# Codecats

## Befehle der Git CommandLine:

- `git init` Initialisierung eines lokalen git-Repositories
- `git remote add <name of repo> <repo link>` Hinzufügen eines Remote Repositories [Gitref.org](http://gitref.org/remotes/)
- `git remote -v` Remotes incl. Links anzeigen
- `git remote show <name of branch>` Gibt weitere Informationen aus, die mit dem `-v` Befehl noch nicht angezeigt werden
- `git remote rm <remotename>` Remove a Remote
- `git remote set-url <remotename> <git-url>` RemoteURL der einzelnen Repos ändern [GitHub](https://help.github.com/articles/changing-a-remote-s-url/)
- `git clone <link>` Clonen eines bereits existierenden Repositories [clone incl. fetch, merge und pull](https://help.github.com/articles/fetching-a-remote/)
- `git commit` Commiten ( `-m` erlaubt dabei das sofortige hinzufügen eines Comments in `""` ) (--> ruhig oft commiten, als Absicherung und um den eigenen Weg nachzuvollziehen)
- `git status` Abfrage ob Veränderungen vorliegen
- `git add` Hinzufügen von noch nicht getrackten Elementen (nutze den `git add .` Befehl und alle Resourcen des Ordners werden hinzugefügt)
- `git push <remotename> <branchname>` Möglichkeiten des Uploads des lokalen Repositories `git push origin master` `git push  <REMOTENAME> <BRANCHNAME>`
- `git log` Anzeigen der bisherigen Commits `git shortlog` gibt dabei kompaktere Ausgabe [Änderungsrecherche im Repository](http://www.ralfebert.de/git/log-recherche/)
- `git branch` Ausgabe existierender Branches `git branch -a` zeigt auch nicht lokale Branches an und damit evtl. existierende Remote-Branches [Atlassian](https://www.atlassian.com/git/tutorials/using-branches/git-branch)
- `git branch <name>` Erstellt eine neue lokale Branch mit dem Namen  `<name>`
- `git branch <neuer-lokaler-Name> <remotename>/<branchname>` Download einer neuen Remotebranch, die im lokalen Verzeichnis dann unter dem `<neuen-lokalen-Namen>` zu finden sein wird. Es wird empfohlen für den neuen-lokalen-Namen die gleiche Bezeichnung zu verwenden, die beim RepoHoster angegeben ist.
- `git checkout <name>` Wechseln zur `<name>` Branch. Lässt sich mit einem `git status` oder einem `git branch` anschließend überprüfen.
- `git fetch <remotename>` Downloaden der Veränderungen in einem Remote-Repository
- `git diff <name1> <name2>` Unterschiede zwischen zwei verschiedenen Branches anzeigen (bspw. `git fetch origin/master master` --> zeigt die Unterschiede zwischen der gerade gefetchten Remotebranch und der passenden lokalen Masterbranch)
- `git merge` Zusammenfügen zweier Branches (Im Falle eines vorhergegangenen Fetch-Vorgangs dann die Kombination aus lokalem und gedownloadetem RemoteRepo) [MergeConflicts](https://git-scm.com/book/de/v1/Git-Branching-Einfaches-Branching-und-Merging)
- `git pull` Kombination aus `git fetch` und `git merge`, der beide Befehle unter einer Abfrage zusammenfasst (mit Vorsicht zu genießen!)


### How to undo commits (go back to previous version) | or reset my branch

- `git reset <option> <commit-hash>` Zurücksetzen der Files auf den Stand des angegebenen commits [StackOverflow I](http://stackoverflow.com/questions/2530060/can-you-explain-what-git-reset-does-in-plain-english) [StackOverflow II](http://stackoverflow.com/questions/927358/how-do-you-undo-the-last-commit) [GitHub](https://github.com/blog/2019-how-to-undo-almost-anything-with-git)
- `git reset --hard` Löscht alle Änderungen, die bisher noch nicht committed wurden [StackOverflow](http://stackoverflow.com/questions/9529078/how-do-i-use-git-reset-hard-head-to-revert-to-a-previous-commit) [GitSCM](http://git-scm.com/docs/git-reset)
- `git revert <commit-hash>` Erstellt einen Commit, der das genaue Gegenteil des `commit-hash` an nimmt. [GitHub](https://github.com/blog/2019-how-to-undo-almost-anything-with-git)



### How to delete Branches

|Ort|Befehl|
|:---|:---|
|lokal| `git branch -d <branchname>` |
|remote| `git push <remotename> --delete <branchname>` |
[GitHub](http://stackoverflow.com/questions/2003505/delete-a-git-branch-both-locally-and-remotely)

- `git remote prune origin` Sollte man eine Branch direkt bei GitHub löschen oder der Mitarbeiter löscht die Branch, dann erscheint diese dennoch bei der Abfrage durch `git branch -a` als Remote Branch. Der obige Befehl korrigiert dies.


### How to delete a local git repository but keep the last (and final) Version

- `rm -rf .git` Löscht die .git-File und damit alle gespeicherten Veränderungen, Branches, Einstellungen etc. -r gibt an einen Ordner zu Löschen (den .git ja darstellt und -f meint einen Force-delete ohne anhaltende Bestätigungs-Promts) [StackOverflow](http://stackoverflow.com/questions/1514054/how-do-i-delete-a-local-repository-in-git)
- `rm -rf .git*` Löscht alle Files, die mit .git[xy] beginnen und damit auch evtl. vorhandene .gitignore oder .gitmodules

___

## Links

- [Super simple start with Git](http://rogerdudler.github.io/git-guide/) Klasse Überblick mit vielen Commands ein tolles CheatSheat, Verweiße auf ausführliche Tutorials und eine Auflistung von top Software Clients
- [Gerade erwähntes CheatSheet](http://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf)
- [GitGuys](http://www.gitguys.com/)
- [Git-Tower - Learn Version Control with Git](http://www.git-tower.com/learn/git/ebook/command-line/introduction)
- [Why fetch not pull - Mark's blog](http://longair.net/blog/2009/04/16/git-fetch-and-merge/)
- [Atlassian Git Tutorial- creator of BitBucket](https://www.atlassian.com/git/)
- [Atlassian Git Tutorial - Comparing Workflows](https://www.atlassian.com/git/tutorials/comparing-workflows)
- [RawGit - ermöglicht das Anzeigen vom WebSites direkt von GitHub aus](http://rawgit.com/)

## Alternative RepoHost

- [GitHub](https://github.com/)
- [GitLab](https://about.gitlab.com/)
- [Beanstalk](http://beanstalkapp.com/)
- [BitBucket by Atlassian](https://bitbucket.org/)

## Tools, Clients and GUIs

- [Official GitHub Client (Win)](https://windows.github.com/)
- [Official GitHub Client (Mac)](https://mac.github.com/)
- [Git Client by Atlassian (Mac & Win)](https://www.sourcetreeapp.com/)
- [Git-Tower (Mac)](http://www.git-tower.com/)
- [weitere Clients in der offiziellen Git Dokumentation](https://git-scm.com/downloads/guis)

___
## Das offizielle und kostenlose Git Handbuch zum Download
[als pdf, mobi, epub oder html Version](https://git-scm.com/book/en/v2)
