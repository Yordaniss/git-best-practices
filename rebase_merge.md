Beispiel-Szenario:
Ein Entwickler arbeitet an einem Feature-Branch (feature-branch), während das Main-Branch (main) weiterentwickelt wird.
Nach einiger Zeit möchte der Entwickler seine Änderungen mit main synchronisieren.
1️⃣ Git Merge – Beibehaltung der Historie
git merge erstellt einen neuen Merge-Commit, der die Änderungen beider Branches zusammenführt.
Die Historie bleibt unverändert, aber es entsteht ein zusätzlicher Merge-Commit.
Befehle:

# git checkout feature-branch
# git merge main
Diagramm (Merge-Historie mit zusätzlichem Merge-Commit):


          A---B---C (main)
         /         \
    D---E---F---G---H (feature-branch, merged)
🔹 Vorteil: Zeigt eine vollständige Historie aller Änderungen.
🔹 Nachteil: Die Historie kann unübersichtlich werden, wenn es viele Merges gibt.

2️⃣ Git Rebase – Lineare Historie
git rebase nimmt die Commits aus feature-branch, setzt sie nach den neuesten main-Commits und erstellt neue Commits mit demselben Inhalt.
Kein zusätzlicher Merge-Commit, aber die Commit-Hashes ändern sich.
Befehle:

bash

# git checkout feature-branch
# git rebase main
Diagramm (Rebase – Saubere lineare Historie):


          A---B---C (main)
                  \
                   D'---E'---F'---G' (feature-branch, rebased)
🔹 Vorteil: Saubere, lineare Historie ohne Merge-Commits.
🔹 Nachteil: Falls der Branch bereits geteilt wurde, kann Rebase zu Konflikten für andere Entwickler führen.

Wann sollte man Merge oder Rebase verwenden?
Situation	                    Git Merge	    Git Rebase
Historie verständlich halten	✅	           ❌
Saubere lineare Historie	    ❌	           ✅ 
Arbeiten mit geteilten Branches	✅	           ❌ (kann problematisch sein)
Vermeidung von Merge-Komplexität❌	           ✅
