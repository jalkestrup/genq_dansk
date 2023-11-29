

Repo består af 3 Notebooks:
- 01 til at generere question, der kunne det være interessant hvis du ville kigge på selve prompten og evt iterere på formen af den
- 02  en lille explainer notebook der bare kigger lidt nærmere på det QA objekt som llamaindex spytter ud når man genererer questions (jeg havde selv brug for lige at forstå det)
- 03 som i første omgang bare er et simpelt setup til at loade de question og chunks som er genereret i 01 ind igen, og så sætte en vektor retrieval op med en valgfri embedding model, og køre en llamaindex built-in retrieval evaluering (hit-rate, de har ikke NDGC endnu) fra de 100 generede spørgsmål og det vektor index, som lige er oprettet. 03 viser også tydeligt problematiken i at der ofte vil være mange andre chunks af data som matcher i top K på vektor search, som faktisk virker til at være et godt match, men som bliver klassificeret som "foerkert" fordi den lige nu helt naitvt kun matcher det spørgsmål og chunk som blev brugt til at generere Q.