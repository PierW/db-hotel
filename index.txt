HOTEL

STANZA:
  -id -- INT -- PRIMARY KEY, AUTO_INCREMENT
  -numero -- SMALLINT -- UNIQUE, NOT NULL
  -tipologia -- VARCHAR(20) -- NOT NULL
  -disponibilità -- TINYINT(1) -- DEFAULT(0)
  -prezzo -- FLOAT(6,2) -- NULLABLE
  -animali -- TINYINT(1) -- DEFAULT(0)
  -services -- VARCHAR(255) -- NULLABLE

PERSONA:
  -id -- INT -- PRIMARY KEY, AUTO_INCREMENT
  -nome -- VARCHAR(30) -- NOT NULL
  -cognome -- VARCHAR(30) -- NOT NULL
  -d. id -- VARCHAR(20) -- NOT NULL
  -d. id tipo -- VARCHAR(10) -- NOT NULL
  -data di nascita -- DATE -- NOT NULL
  -telefono -- VARCHAR(25) -- NULLABLE, UNIQUE

PRENOTAZIONE:
  -id -- INT -- PRIMARY KEY, AUTO_INCREMENT
  -d inizio -- DATE -- NOT NULL
  -d fine -- DATE -- NOT NULL
  -d canc gratuita -- DATE -- NULLABLE
  -ota -- VARCHAR(20) -- NOT NULL
  -prezzo -- FLOAT(8, 2) -- NOT NULL
  -sconto -- FLOAT(4, 2) -- DEFAULT(0)


PAGAMENTO:
  -id -- INT -- PRIMARY KEY, AUTO_INCREMENT
  -pagato -- TINYINT(1) -- DEFAULT(0)
  -canale pagamento -- VARCHAR(15) -- NOT NULL
  -data pagamento -- DATE
  -allegati -- TEXT
  -c. sconto -- VARCHAR(15)


  ----------------------
  HOTEL : RELAZIONI

  PRENOTAZIONE <--------N-N---------> STANZA
     STANZA    <--------N-N---------> PERSONA
    PAGAMENTO  <--------N-1---------> PERSONA
    PAGAMENTO  <--------1-1---------> PRENOTAZIONE
