# MarketEcho Windows Setup

Launcher pubblico per il setup Windows di MarketEcho, ospitato gratuitamente su GitHub Pages.
Il codice applicativo rimane nel repository privato MarketEcho-AI/MarketEcho-AI.

Aprire PowerShell normalmente su Windows x64, **senza Esegui come amministratore**, e incollare:

```powershell
irm https://marketecho-ai.github.io/marketecho-setup/install.ps1 | iex
```

Servono una connessione Internet, accesso GitHub al repository privato e un conto FxPro MT5 Demo.
Il launcher prepara Git for Windows se manca (verifica SHA256 e firma Authenticode),
scarica main e avvia il setup ufficiale. Il setup mostra il commit, chiede una nuova
cartella e il numero del conto Demo, quindi usa la distribuzione verificata di quel commit.
La password del conto si inserisce soltanto in MT5.
Una console elevata viene bloccata prima di download, pulizia o creazione di cartelle
con `SETUP_STANDARD_USER_REQUIRED`: riaprire PowerShell normalmente e ripetere la stessa riga.
Solo gli helper di orologio e percorsi lunghi richiedono la UAC quando necessario.

Non sostituisce vecchie installazioni e non importa database esistenti.
Avvio protetto: Trading OFF, Kill ON, Algo OFF, Demo PAUSED.
Non autorizza trading e non crea consensi o ordini.

Questo repository contiene soltanto il launcher e queste istruzioni, senza credenziali.
Il file install.ps1 e generato nel progetto privato da
`python scripts/windows_setup_command.py --public-launcher` e mantiene il bootstrap
in un processo PowerShell separato. Modifiche al bootstrap richiedono una nuova
pubblicazione di questo file; la versione applicativa viene letta da main a ogni avvio.
