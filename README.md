# 🚀 AI-Powered SWOT-Analyse-Bot (n8n + Ollama)

Dieses Projekt implementiert einen automatisierten Workflow zur sofortigen Bewertung von Geschäftsideen. Mitarbeiter können eine Idee über Telegram einreichen, welche anschließend durch ein lokales Large Language Model (LLM) analysiert und als SWOT-Profil zurückgegeben wird.

## 🏗️ Systemarchitektur

Der Prozess wurde nach BPMN 2.0-Standards modelliert:

![BPMN Prozessmodell](swot-bot-prozess.png)

## 🛠️ Verwendete Technologien

* **n8n:** Workflow-Automatisierung (gehostet via Docker).
* **Telegram API:** Benutzeroberfläche für die Dateneingabe.
* **Ollama (Gemma):** Lokale KI-Inferenzmaschine zur Auswertung (via host.docker.internal).

## ⚙️ Funktionsweise

1. Der Nutzer sendet einen Text mit seiner Idee an den dedizierten Telegram-Bot.
2. Ein Webhook in n8n fängt die Nachricht ab.
3. Das System leitet den Text an das lokal gehostete Gemma-Modell weiter, mit einem spezifischen Prompt für Geschäftsanalysten.
4. Die KI generiert eine Machbarkeits- und Nutzenbewertung samt kurzer SWOT-Analyse.
5. Das Ergebnis wird automatisch an den Nutzer auf Telegram zurückgesendet.
