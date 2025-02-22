Best Practices using Git/GitHub
1. Die goldene Regel: Git Pull & Push
🚀 Regel: „git pull bevor du arbeitest, git push bevor du gehst“

🔹 Warum?

Vermeidet Konflikte mit Änderungen anderer Teammitglieder
Hält dein lokales Repository aktuell
Schützt deine Arbeit vor Verlust (z. B. durch einen defekten Laptop)
💡 Visuelle Idee:
Ein einfaches Diagramm mit einer Person, die morgens git pull ausführt, tagsüber arbeitet und abends git push nutzt, bevor der Rechner ausgeschaltet wird.

2. Merge-Konflikte reduzieren
Wie kann ich Merge-Konflikte vermeiden?
✅ Regelmäßig git pull ausführen, um Änderungen frühzeitig zu sehen
✅ Feature-Branches verwenden, damit sich Änderungen nicht in main oder develop stauen
✅ Kleine, thematische Commits statt riesiger Codeblöcke

💡 Visuelle Idee:
Ein Diagramm mit zwei Entwicklern, die parallel arbeiten, wobei einer frühzeitig merged und der andere eine lange isolierte Entwicklungslinie hat (die zu einem Merge-Konflikt führt).

3. Git Stash vs. Git Commit
Was ist git stash?
Speichert Änderungen vorübergehend, ohne sie zu committen
Ermöglicht es, den Branch zu wechseln, ohne unvollständige Änderungen zu verlieren
Wann git stash nutzen?
🔹 Wenn du unerwartet den Branch wechseln musst
🔹 Wenn du Änderungen sichern willst, ohne sie sofort zu committen
🔹 Wenn dein Code nicht in einem commitbaren Zustand ist

git stash         # Speichert alle nicht committeten Änderungen  
git stash list    # Zeigt alle gespeicherten Stashes  
git stash pop     # Holt die zuletzt gespeicherten Änderungen zurück  

💡 Visuelle Idee:
Ein Bild eines Entwicklers, der ein Dokument in eine „Schublade“ (Stash) legt und es später wieder herausnimmt.

4. Git Merge vs. Git Rebase

Hauptunterschiede
Feature	          Git Merge	                Git Rebase
Historie	      Bewahrt Merge-Historie	Lineare Commit-Historie
Konflikte	      Beim Merge-Zeitpunkt	    Schrittweise beim Rebase
Wann nutzen?	  Wenn Historie wichtig ist	Wenn Historie sauber bleiben soll


Beispiel für git merge
# git checkout feature-branch  
# git merge main  
Beispiel für git rebase
bash
# git checkout feature-branch  
# git rebase main  
💡 Visuelle Idee:

Ein Diagramm mit zwei parallelen Entwicklungslinien (Merge) vs. eine neu angeordnete, saubere Linie (Rebase).
5. GitHub Pull Request Template
Warum eine Pull-Request-Vorlage nutzen?
✅ Einheitlicher Workflow für Code-Reviews
✅ Klare Beschreibung der Änderungen
✅ Verhindert unnötige Nachfragen

Beispiel für eine .github/PULL_REQUEST_TEMPLATE.md
md
Kopieren
Bearbeiten
## Beschreibung
<!-- Kurz erklären, was geändert wurde -->

## Änderungen
- [ ] Feature hinzugefügt  
- [ ] Bugfix  
- [ ] Code verbessert  

## Testanweisungen
<!-- Wie kann der Reviewer die Änderungen testen? -->

## Screenshots (falls nötig)
💡 Visuelle Idee:
Ein Screenshot eines strukturierten PRs vs. ein PR ohne Beschreibung (Chaos).