# SunoAI_MP3_Downloader

Automatisches **MP3-Download-Skript** für die **Browser-Konsole** (Chrome/Edge/Firefox) auf suno.com.  
Es öffnet pro Track das Kontextmenü (⋯) → **Download** → **MP3 Audio** – ohne Hover, per Fokus + Enter.

---

## TL;DR (so benutzt du’s)

1. **Browser vorbereiten**
   - „Vor dem Download **jeden Speicherort abfragen**“ **AUS**  
     - Chrome/Edge: Einstellungen → Downloads → Schalter aus  
     - (Optional) Seiteneinstellungen: **Automatische Downloads zulassen**, Pop-ups/Weiterleitungen erlauben  
   - Firefox: Einstellungen → Allgemein → Downloads → **Dateien speichern nach** (Ordner wählen) und **„Jedes Mal nachfragen…“** **aus**

2. **Suno öffnen** → Seite mit den Song-Karten.

3. **DevTools** öffnen (F12) → **Console**.

4. Inhalt aus `suno-downloader.js` **komplett einfügen** → **Enter**.

5. Den **Prompts** folgen (Anzahl, Offset, Delay etc.).

6. Zurücklehnen. Abbruch jederzeit mit **ESC** (echte Taste) oder `window.__abortDownloads = true`.

---

## Parameter (Prompts)

- **Auto-Scroll aktivieren?**  
  Lädt vor dem Start zusätzliche Karten ins DOM (Lazy-Loading/virtuelle Listen).  
  - **Ziel-Anzahl Karten:** Wie viele Karten sollen vorab eingesammelt werden (z. B. 50)?

- **Wie viele Songs herunterladen?**  
  Anzahl der **von oben** gezählten Karten, die tatsächlich geladen werden.

- **Ab welchem Index starten? (Offset)**  
  Startposition (1-basiert). Beispiel: Offset **17** = ab Karte #17 weiter (praktisch für Teil-Runs).

- **Pause zwischen Downloads (Sek.)**  
  Wartezeit zwischen zwei Auslösungen (z. B. 5). Ein kleines Jitter wird automatisch addiert.

---

## Features

- Keine Maus-Hovers nötig: **Fokus + Enter** (robust gegenüber Fullscreen/Zoom).
- **Auto-Scroll Pre-Scan** sammelt weitere Karten, bis Zielanzahl erreicht ist.
- **Not-Aus:** ESC (echter Tastendruck) oder `window.__abortDownloads = true`.
- Ausführliche **Konsole-Logs** (Fortschritt, Skips, Hinweise).

---

## Start/Stop – kurz & knackig

- **Start:** Skript in der Konsole einfügen → Enter → Prompts beantworten.  
- **Stop:**  
  - **ESC** drücken (echte Taste), **oder**  
  - in die Konsole: `window.__abortDownloads = true`.

---

## Hinweise & Limits

- Du **musst** die Browser-Rückfrage „Speicherort wählen“ **deaktivieren**, sonst musst du jeden Download bestätigen.
- Das Skript klickt exakt **Download → MP3 Audio**. WAV/Video werden ignoriert.
- Bei UI-Änderungen von Suno können Selektoren brechen – bitte Issue eröffnen/PR schicken.
- Pro Seite sind oft nur ~N Karten gerendert (virtuelle Liste). **Auto-Scroll** hebt das Limit in der Regel auf.
- Beachte die **Nutzungsbedingungen** von Suno und lokales Recht.

---

## Troubleshooting

- **Findet nur wenige Karten** → Auto-Scroll aktivieren und Ziel-Anzahl erhöhen (z. B. 50).
- **Jeder Download fragt nach Speicherort** → Browser-Einstellung „vor dem Download fragen“ **aus**.
- **Stoppt sofort** → Prüfen, ob ESC gedrückt wurde; `window.__abortDownloads` darf nicht `true` sein.
- **„Download“/„MP3 Audio“ nicht gefunden** → Seite neu laden, „⋯“-Menü manuell testen; ggf. UI geändert → Issue erstellen.

---

## Sicherheit & Rechtliches

Dieses Skript automatisiert **dein eigenes** Klick-Verhalten im Browser.  
Kein Zugriff auf Accounts/APIs, kein Scraping geschützter Inhalte. Nutzung auf eigene Verantwortung.  
Bitte **Suno-ToS** beachten.

---

## Lizenz

MIT – feel free to use/modify. Contributions willkommen. 🚀
