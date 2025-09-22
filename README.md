ESERCIZIO 1
SELECT clienti.nome, clienti.cognome FROM clienti
WHERE clienti.nome = 'Mario'

ESERCIZIO 2
SELECT clienti.nome, clienti.cognome FROM clienti
WHERE clienti.anno_di_nascita = 1982

ESERCIZIO 3
SELECT * FROM fatture
WHERE fatture.iva = 20

ESERECIZIO 4
SELECT * FROM prodotti
WHERE prodotti.in_produzione = true or prodotti.in_commercio = true 
and EXTRACT(YEAR FROM prodotti.data_attivazione) = 2017

ESERCIZIO 5
SELECT * FROM fatture
JOIN clienti
ON fatture.id_cliente = clienti.numero_cliente
WHERE fatture.importo <= 1000

ESERCIZIO 6
SELECT fatture.numero_fattura, fatture.importo, fatture.iva,
fatture.data_fattura, fornitori.numero_fornitore
FROM  fatture JOIN fornitori
ON fatture.numero_fornitore = fornitori.numero_fornitore

ESERCIZIO 7
SELECT EXTRACT(YEAR FROM fatture.data_fattura) , COUNT (*)
FROM fatture
WHERE fatture.iva = 20
GROUP BY EXTRACT(YEAR FROM fatture.data_fattura)

ESERCIZIO 8
SELECT  EXTRACT(YEAR FROM fatture.data_fattura), COUNT (*), SUM(fatture.importo)
FROM fatture
GROUP BY EXTRACT(YEAR FROM fatture.data_fattura)
