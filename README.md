# 🧠 Git – Vollständige Anleitung (Schritte 1–10)

Dieses Dokument erklärt alle wichtigen **Git-Befehle** in 10 klaren Schritten – vom Setup bis zum Lösen von Konflikten.  
Ideal für Entwickler, Studenten und Teams, die professionell mit Git & GitHub arbeiten möchten.

---

## ⚙️ 1. Installation & Grundeinrichtung

### 🔧 Git installieren
sudo apt update
sudo apt install git -y

shell
Code kopieren

### 🔍 Version prüfen
git --version

shell
Code kopieren

### 👤 Benutzer konfigurieren
git config --global user.name "Vorname Nachname"
git config --global user.email "deine.email@example.com"

shell
Code kopieren

### 🔎 Konfiguration prüfen
git config --list

yaml
Code kopieren

---

## 🏗️ 2. Neues Projekt starten

### 🆕 Neues Repository lokal anlegen
git init

shell
Code kopieren

### 📄 Dateien hinzufügen
git add dateiname.txt

oder alle Dateien
git add .

shell
Code kopieren

### 💬 Änderungen speichern (Commit)
git commit -m "Erster Commit"

yaml
Code kopieren

---

## ☁️ 3. Verbindung zu GitHub herstellen

### 🔗 Remote Repository hinzufügen
git remote add origin https://github.com/USERNAME/REPOSITORY.git

shell
Code kopieren

### 🔍 Remote-URLs anzeigen
git remote -v

shell
Code kopieren

### 🔄 Remote-URL ändern
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git

yaml
Code kopieren

---

## 🚀 4. Änderungen hochladen & herunterladen

### 📤 Push (lokal → GitHub)
git push -u origin main

markdown
Code kopieren

> ⚠️ Wenn Git ein Passwort verlangt, **verwende dein GitHub-Personal-Access-Token (PAT)** statt deines echten Passworts.

### 📥 Pull (GitHub → lokal)
git pull origin main

shell
Code kopieren

### 🔁 Fetch (nur Updates holen, ohne zu mergen)
git fetch origin

yaml
Code kopieren

---

## 🌿 5. Arbeiten mit Branches

### ➕ Neuen Branch erstellen
git branch feature/login

shell
Code kopieren

### 🔄 Zu Branch wechseln
git checkout feature/login

shell
Code kopieren

### 🧭 Branch erstellen + wechseln (Kurzform)
git checkout -b feature/login

shell
Code kopieren

### 🗑️ Branch löschen
git branch -d feature/login

shell
Code kopieren

### 🌍 Alle Branches anzeigen
git branch -a

shell
Code kopieren

### 🔀 Branch mergen
git checkout main
git merge feature/login

yaml
Code kopieren

---

## 🧩 6. Status, Historie & Änderungen prüfen

### 📊 Aktuellen Status sehen
git status

shell
Code kopieren

### 🕓 Commit-Historie anzeigen
git log

shell
Code kopieren

### Kurzformatierte Log-Ansicht
git log --oneline --graph --decorate

shell
Code kopieren

### 🔍 Unterschiede anzeigen
git diff

yaml
Code kopieren

---

## ♻️ 7. Änderungen rückgängig machen

### ❌ Dateiänderung verwerfen (seit letztem Commit)
git checkout -- dateiname.txt

shell
Code kopieren

### 🔙 Letzten Commit rückgängig machen (ohne Änderungen zu verlieren)
git reset --soft HEAD~1

shell
Code kopieren

### 🔄 Commit komplett rückgängig machen (auch Änderungen löschen)
git reset --hard HEAD~1

shell
Code kopieren

### 🔄 Datei entfernen
git rm dateiname.txt

yaml
Code kopieren

---

## 🔐 8. Authentifizierung mit SSH (empfohlen)

### 🗝️ SSH-Key erzeugen
ssh-keygen -t ed25519 -C "deine.email@example.com"

shell
Code kopieren

### 🔑 SSH-Agent starten
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

shell
Code kopieren

### 📋 Öffentlichen Schlüssel anzeigen und kopieren
cat ~/.ssh/id_ed25519.pub

markdown
Code kopieren

Dann auf **GitHub → Settings → SSH and GPG keys → New SSH key**  
→ Schlüssel einfügen.

### 🧪 Verbindung testen
ssh -T git@github.com

graphql
Code kopieren

### 🔁 Remote auf SSH umstellen
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git

yaml
Code kopieren

---

## 🧱 9. Rebase, Stash & Tags

### ✨ Rebase (Commits neu ordnen)
git checkout feature/login
git rebase main

shell
Code kopieren

### 🧳 Zwischenstand speichern (Stash)
git stash

shell
Code kopieren

### 🧾 Gespeicherten Stand wiederherstellen
git stash pop

shell
Code kopieren

### 🏷️ Versionstag setzen
git tag -a v1.0 -m "Version 1.0"

shell
Code kopieren

### 🏷️ Tags anzeigen
git tag

yaml
Code kopieren

---

## ⚔️ 10. Konflikte lösen

Wenn Merge-Konflikte auftreten:

1. Öffne betroffene Dateien  
2. Suche nach Konfliktmarkierungen:
<<<<<<< HEAD
Code aus deinem Branch
Code aus anderem Branch

main

markdown
Code kopieren
3. Konflikt manuell bereinigen  
4. Änderungen hinzufügen und committen:
git add .
git commit -m "Konflikt behoben"

yaml
Code kopieren

---

**© 2025 – Git Lern- und Arbeitsdokument von Anas Alnabulsi**  
*Struktur, Ordnung und Klarheit sind die Basis erfolgreicher Softwareentwicklung.*
