# puliderma.github.io

---

Esito del 2026-08-15 17:34 UTC: pubblicazione NON eseguita. Il download dell'archivio del sito da https://infinanza.net/puliderma-sito-20260815-172901-871873-01.gz e' stato bloccato dalla policy di rete dell'ambiente di lavoro (il proxy ha rifiutato la connessione verso infinanza.net con codice 403, anche dopo piu' tentativi). Nessun file estratto, nessun contenuto del sito committato: l'impronta sha256 non era verificabile. Da riprovare da un ambiente con accesso di rete a infinanza.net, oppure abilitando quel dominio nella network policy dell'ambiente.

---

Esito del 2026-08-17 08:58 UTC: pubblicazione ESEGUITA. Commit `e7c77b8` ("sito Puliderma v1: 788 prodotti, pubblicazione iniziale"). File pubblicati e presenti nel repo: `index.html`, `catalogo.html`, `aziende.html`, `tesserino.html`, `stile.css`, piu' il `.nojekyll` gia' aggiunto in precedenza (commit `3428349`).

Verifica HTTP impossibile da qui: il proxy nega l'accesso a puliderma.github.io. La richiesta `curl` verso https://puliderma.github.io/ ha restituito codice 000 (curl 56, "CONNECT tunnel failed, response 403"), quindi nessuna risposta HTTP e' stata ottenuta e NON e' stato possibile controllare se la home contiene la parola «Puliderma». Quello che risulta verificato e' soltanto questo: i file del sito sono committati e presenti nel repository. Lo stato online del sito resta da confermare da un ambiente con accesso di rete a puliderma.github.io.

L'esito del 2026-08-15 qui sopra («pubblicazione NON eseguita») e' superato dai fatti: viene lasciato leggibile come storia, ma non descrive piu' lo stato attuale del repository.

---

Esito del 2026-08-23 19:00 UTC: deploy CONFERMATO dalla pipeline di GitHub Pages, verificato per via API. Il workflow «pages build and deployment» e' andato a buon fine su `main` al commit `52ee643`: run n. 5 (id 32012947909), conclusione «success» il 17/08/2026 alle 08:59 UTC. Tutte e cinque le esecuzioni della pipeline Pages risultano riuscite, quindi GitHub ha costruito e distribuito il sito. Il branch `main` remoto contiene tutti i file del sito: `index.html`, `catalogo.html` (con esattamente 788 schede prodotto, riconteggiate), `aziende.html`, `tesserino.html`, `stile.css`, `.nojekyll`.

Il controllo HTTP diretto su https://puliderma.github.io/ resta impossibile anche da questo ambiente: la richiesta `curl` viene rifiutata dal proxy (CONNECT 403) e anche il fetch lato server e' negato dalla policy di rete (egress bloccato per puliderma.github.io). L'unico controllo non eseguito rimane quindi l'apertura della home da un browser normale, fuori da questo ambiente di lavoro.

La dicitura del 17/08 «lo stato online del sito resta da confermare» e' superata: la pubblicazione risulta eseguita e distribuita da GitHub Pages secondo i sistemi di GitHub stessi.