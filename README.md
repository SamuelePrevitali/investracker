# Investracker

**Tracker personale di budget e portafoglio.** Spese, risparmi e posizioni in ETF, azioni e obbligazioni in un unico posto, con i prezzi aggiornati dalla Borsa e il valore convertito in euro.

> 🔒 Il codice sorgente è in un repository privato. Questa pagina descrive il progetto e le scelte tecniche: se vuoi vedere il codice, [scrivimi](#contatti) e te lo mostro.

## Cosa fa

- 💶 **Dashboard del budget**: entrate, spese e risparmi del mese, con un obiettivo di risparmio e la barra di avanzamento.
- 📈 **Portafoglio**: posizioni in ETF, azioni e obbligazioni con prezzo di carico, valore attuale e guadagno o perdita.
- 🔄 **Prezzi live**: Twelve Data come fonte principale e Yahoo Finance come riserva, con una cache di 20 minuti per non sprecare le chiamate gratuite.
- 💱 **Conversione in euro** dei titoli quotati in altre valute, con i cambi della Banca Centrale Europea.
- ⚖️ **Ribilanciamento**: confronta l'allocazione attuale con quella obiettivo.
- 📊 **Cronologia**: grafico a torta e andamento nel tempo (Chart.js), esportazione in CSV.
- ✉️ **Promemoria mensile via email** per aggiornare i dati.
- 🛠️ **Gestionale per l'amministratore**: utenti, chiavi delle API, impostazioni.

## Sicurezza

- Password cifrate con bcrypt, mai salvate in chiaro.
- Query con parametri preparati contro la SQL injection, output sempre filtrato contro l'XSS.
- Protezione CSRF su tutti i form e su ogni azione che modifica dati.
- Account attivo solo dopo la verifica dell'email, con token a scadenza.
- reCAPTCHA verificato lato server alla registrazione.
- Limite di tentativi su login e recupero password contro gli attacchi a forza bruta.
- Cookie di sessione `HttpOnly` e `Secure`, ID di sessione rigenerato al login.
- Recupero password che non rivela quali email sono registrate.

## Stack

| | |
|---|---|
| Backend | PHP, MySQL |
| Frontend | HTML, CSS, JavaScript, Chart.js |
| Dati di mercato | Twelve Data, Yahoo Finance, Frankfurter (cambi BCE) |
| Email e protezione | Brevo, Google reCAPTCHA v2 |
| Hosting | Qualsiasi hosting PHP + MySQL, anche gratuito, con HTTPS |

## Nota

Lo strumento non dà consigli di investimento: serve solo a tenere traccia delle scelte di chi lo usa.

## Contatti

Progetto di **Samuele Previtali** · previsamu@gmail.com · [LinkedIn](https://www.linkedin.com/in/samuele-giovanni-previtali) · [altri progetti](https://github.com/SamuelePrevitali)

---

© 2026 Samuele Previtali. Tutti i diritti riservati.
