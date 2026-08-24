# puliderma.github.io

---

Esito del 2026-08-15 17:34 UTC: pubblicazione NON eseguita. Il download dell'archivio del sito da https://infinanza.net/puliderma-sito-20260815-172901-871873-01.gz e' stato bloccato dalla policy di rete dell'ambiente di lavoro (il proxy ha rifiutato la connessione verso infinanza.net con codice 403, anche dopo piu' tentativi). Nessun file estratto, nessun contenuto del sito committato: l'impronta sha256 non era verificabile. Da riprovare da un ambiente con accesso di rete a infinanza.net, oppure abilitando quel dominio nella network policy dell'ambiente.

---

Esito del 2026-08-17 08:58 UTC: pubblicazione ESEGUITA. Commit `e7c77b8` ("sito Puliderma v1: 788 prodotti, pubblicazione iniziale"). File pubblicati e presenti nel repo: `index.html`, `catalogo.html`, `aziende.html`, `tesserino.html`, `stile.css`, piu' il `.nojekyll` gia' aggiunto in precedenza (commit `3428349`).

Verifica HTTP impossibile da qui: il proxy nega l'accesso a puliderma.github.io. La richiesta `curl` verso https://puliderma.github.io/ ha restituito codice 000 (curl 56, "CONNECT tunnel failed, response 403"), quindi nessuna risposta HTTP e' stata ottenuta e NON e' stato possibile controllare se la home contiene la parola «Puliderma». Quello che risulta verificato e' soltanto questo: i file del sito sono committati e presenti nel repository. Lo stato online del sito resta da confermare da un ambiente con accesso di rete a puliderma.github.io.

L'esito del 2026-08-15 qui sopra («pubblicazione NON eseguita») e' superato dai fatti: viene lasciato leggibile come storia, ma non descrive piu' lo stato attuale del repository.

---

Esito del 24/08/2026 (verifica della macchina): GitHub Pages risulta GIA' ACCESO, nessuna attivazione eseguita.

La richiesta arrivata a questa sessione partiva dalla premessa che il repo non avesse deployment ne' ambiente github-pages e che quindi Pages non fosse mai stato attivato. La premessa e' contraddetta dai dati verificati oggi:

1. GET https://api.github.com/repos/puliderma/puliderma.github.io/pages via curl: codice 403 dal proxy dell'ambiente («Access to this GitHub API path is not permitted through this proxy»). NON e' un 404 di GitHub: il path e' bloccato dal proxy, quindi da qui lo stato di Pages non era leggibile con curl.
2. Strumenti GitHub della sessione (elenco esecuzioni Actions): il repo ha 5 esecuzioni del workflow «pages build and deployment», tutte concluse con successo. L'ultima e' la n. 5 del 17/08/2026 08:59 UTC sul commit `52ee643` (l'attuale HEAD di main). Questo workflow esiste solo se Pages e' attivo: quindi Pages e' acceso e l'ultimo build dell'attuale contenuto del sito e' andato a buon fine (equivalente di «built»).
3. POST di attivazione di Pages NON eseguito: non necessario (gia' attivo) e comunque il path API e' bloccato dal proxy di questo ambiente.
4. Prova finale sul sito: `curl https://puliderma.github.io/` ha restituito codice 000 (curl 56, «CONNECT tunnel failed, response 403»): la network policy di questo ambiente non arriva a github.io, come gia' il 17/08. La verifica online della home (presenza della parola «Puliderma») resta quindi non eseguibile da qui e va fatta da un browser normale.

In sintesi: nessuna azione di attivazione era necessaria ne' possibile; lo stato accertato e' «Pages attivo, ultimo deployment riuscito il 17/08/2026 sul commit corrente». Se il sito desse davvero 404 da un browser, il problema andrebbe cercato altrove (propagazione, dominio, cache), non nell'attivazione di Pages.

---

Esito del 2026-08-24 20:02 UTC (immagini D28): pubblicazione NON eseguita, download bloccato dalla rete. Comando provato (due tentativi): curl -sS -o pacchetto.zip "https://d2ol7oe51mr4n9.cloudfront.net/user_3FeDqVrrckQdXDyAd8vykaJ4L1N/bd859c59-27bd-4553-93ae-bdafef3f8edf.zip" — errore esatto: curl 56, «CONNECT tunnel failed, response 403» (il proxy dell'ambiente nega la connessione verso d2ol7oe51mr4n9.cloudfront.net: «policy denial»). Nessun file scaricato, impronta sha256 non verificabile, cartella immagini/ non creata. Da riprovare da un ambiente con accesso di rete a quel dominio CloudFront, oppure abilitandolo nella network policy.