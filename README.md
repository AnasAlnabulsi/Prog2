# 🧠 Git – Vollständige Anleitung (Schritte 1–10)

Dieses Dokument erklärt alle wichtigen **Git-Befehle** in 10 klaren Schritten – vom Setup bis zum Lösen von Konflikten.  
Ideal für Entwickler, Studenten und Teams, die professionell mit Git & GitHub arbeiten möchten.

---

## ⚙️ 1. Installation & Grundeinrichtung

### 🔧 Git installieren
```
sudo apt update
sudo apt install git -y
```

### 🔍 Version prüfen
```
git --version
```

### 👤 Benutzer konfigurieren
```
git config --global user.name "Vorname Nachname"
git config --global user.email "deine.email@example.com"
```

### 🔎 Konfiguration prüfen
```
git config --list
```

---

## 🏗️ 2. Neues Projekt starten

### 🆕 Neues Repository lokal anlegen
```
git init
```

### 📄 Dateien hinzufügen
```
git add dateiname.txt
# oder alle Dateien
git add .
```

### 💬 Änderungen speichern (Commit)
```
git commit -m "Erster Commit"
```

---

## ☁️ 3. Verbindung zu GitHub herstellen

### 🔗 Remote Repository hinzufügen
```
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

### 🔍 Remote-URLs anzeigen
```
git remote -v
```

### 🔄 Remote-URL ändern
```
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```

---

## 🚀 4. Änderungen hochladen & herunterladen

### 📤 Push (lokal → GitHub)
```
git push -u origin main
```

> ⚠️ Wenn Git ein Passwort verlangt, **verwende dein GitHub-Personal-Access-Token (PAT)** statt deines echten Passworts.

### 📥 Pull (GitHub → lokal)
```
git pull origin main
```

### 🔁 Fetch (nur Updates holen, ohne zu mergen)
```
git fetch origin
```

---

## 🌿 5. Arbeiten mit Branches

### ➕ Neuen Branch erstellen
```
git branch feature/login
```

### 🔄 Zu Branch wechseln
```
git checkout feature/login
```

### 🧭 Branch erstellen + wechseln (Kurzform)
```
git checkout -b feature/login
```

### 🗑️ Branch löschen
```
git branch -d feature/login
```

### 🌍 Alle Branches anzeigen
```
git branch -a
```

### 🔀 Branch mergen
```
git checkout main
git merge feature/login
```

---

## 🧩 6. Status, Historie & Änderungen prüfen

### 📊 Aktuellen Status sehen
```
git status
```

### 🕓 Commit-Historie anzeigen
```
git log
```

### Kurzformatierte Log-Ansicht
```
git log --oneline --graph --decorate
```

### 🔍 Unterschiede anzeigen
```
git diff
```

---

## ♻️ 7. Änderungen rückgängig machen

### ❌ Dateiänderung verwerfen (seit letztem Commit)
```
git checkout -- dateiname.txt
```

### 🔙 Letzten Commit rückgängig machen (ohne Änderungen zu verlieren)
```
git reset --soft HEAD~1
```

### 🔄 Commit komplett rückgängig machen (auch Änderungen löschen)
```
git reset --hard HEAD~1
```

### 🔄 Datei entfernen
```
git rm dateiname.txt
```

---

## 🔐 8. Authentifizierung mit SSH (empfohlen)

### 🗝️ SSH-Key erzeugen
```
ssh-keygen -t ed25519 -C "deine.email@example.com"
```

### 🔑 SSH-Agent starten
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### 📋 Öffentlichen Schlüssel anzeigen und kopieren
```
cat ~/.ssh/id_ed25519.pub
```

Dann auf **GitHub → Settings → SSH and GPG keys → New SSH key**  
→ Schlüssel einfügen.

### 🧪 Verbindung testen
```
ssh -T git@github.com
```

### 🔁 Remote auf SSH umstellen
```
git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

---

## 🧱 9. Rebase, Stash & Tags

### ✨ Rebase (Commits neu ordnen)
```
git checkout feature/login
git rebase main
```

### 🧳 Zwischenstand speichern (Stash)
```
git stash
```

### 🧾 Gespeicherten Stand wiederherstellen
```
git stash pop
```

### 🏷️ Versionstag setzen
```
git tag -a v1.0 -m "Version 1.0"
```

### 🏷️ Tags anzeigen
```
git tag
```

---

## ⚔️ 10. Konflikte lösen

Wenn Merge-Konflikte auftreten:

1. Öffne betroffene Dateien  
2. Suche nach Konfliktmarkierungen:
   ```
   <<<<<<< HEAD
   Code aus deinem Branch
   =======
   Code aus anderem Branch
   >>>>>>> main
   ```
3. Konflikt manuell bereinigen  
4. Änderungen hinzufügen und committen:
   ```
   git add .
   git commit -m "Konflikt behoben"
   ```

---

**© 2025 – Git Lern- und Arbeitsdokument von Anas Alnabulsi**  
*Struktur, Ordnung und Klarheit sind die Basis erfolgreicher Softwareentwicklung.*
