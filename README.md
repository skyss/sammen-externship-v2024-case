# Sammen Externship våren 2024

<img src="./assets/skysslogo.svg" width="300" />

Velkommen til Skyss! 

Skyss har nettopp startet arbeidet med å etablere en ny dataplattform.
En del av dette er å utforske potensielle kilder for relevant data.
Dette inkluderer selvfølgelig data vi får direkte fra kjøretøyene som er i oppdrag for Skyss, og fra operatørene som drifter disse (f.eks. Tide og Norled).
I tillegg kan det være andre eksterne datakilder som er relevante.

Et eksempel vi ønsker at dere undersøker nærmere er [trafikkdata fra Statens Vegvesen](https://trafikkdata.atlas.vegvesen.no/#/om-trafikkdata).
Dette datasettet inneholder aggregerte data om trafikkvolum fra målepunkter plassert rundt omkring på veier i landet.
Utover dette har vi i Skyss i liten grad innsikt i hva som finnes i datasettet, og hvilken kvalitet det har – her trenger vi hjelp fra dere :)

Generelt er Skyss alltid interessert i å vite mest mulig om trafikkbildet, både i nåtid (ikke mulig med dette API-et og historisk).
Grunner til dette kan bl.a. være å se på bakgrunnen for forsinkelser i busstrafikken, og å vurdere om ruter burde endres i fremtiden.

Merk at denne oppgaven er _meget_ åpen, og at det ikke er noen krav til en leveranse.
Det vi ønsker oss er at dere gjør deres beste for å bli kjent med API-et og hvilken informasjon en kan hente utifra det, og hvis dere har tid, presenterer denne på en eller annen måte.
Det kan f.eks. være i en presentasjon, på en nettside, i en Jupyter Notebok, et script, eller hva som helst. Det er helt opp til dere!

## Teknisk om API-et

API-et er tilgjengelig her: https://trafikkdata-api.atlas.vegvesen.no/.
Om dere besøker det fra nettleseren kommer dere til en interaktiv GraphQL-klient som inneholder dokumentasjon om de ulike spørringene som er tilgjengelige og en konsoll som kan brukes til eksperimentering.

Se docs her: https://trafikkdata.atlas.vegvesen.no/#/om-api.
Her finnes det også eksempler på praktisk bruk av API-et og eksempler med `curl` og JavaScript. 


### Om GraphQL

Det er et **GraphQL-API**.
Om dere ikke er kjent med GraphQL fra før finnes det mye nyttig informasjon på den [offisielle hjemmesiden](https://graphql.org/learn/).
Kort fortalt innebærer det at en i stedet for å benytte ulike URL-er for å be om ulik informasjon.
Om en har en webserver som inneholder informasjon om kjæledyr ville en med et tradisjonelt REST-API som ikke benytter GraphQL ha sendt en `GET`-request til `/pets/{petId}` for å hente informasjon om et kjæledyr. Med GraphQL er alle requests en `POST` til samme endepunkt, f.eks. `/graphql`, hvor request body inneholder en GraphQL-spørring som spesifiserer hvilken data vi ønsker å få tilbake. Et eksempel på en slik body er
```graphql
{
    pet(petId: 123) {
        name
        category {
            id
            name
        }
    }
}
```
Responsen på en slik spørring kan da se slik ut:
```json
{
    "pet": {
        "name": "Fido",
        "category": {
            "id": 1,
            "name": "dog"
        }
    }
}
```
Igjen, se den [offisielle dokumentasjonen](https://graphql.org/learn/) for mer informasjon.

Det finnes flere GraphQL-klienter en kan velge å benytte med ulike kodespråk.
Se f.eks. [GQL](https://github.com/graphql-python/gql) for Python og [Apollo Client](https://www.apollographql.com/docs/react/) for Javascript. Å bruke en klient er selvfølgelig valgfritt.

## Forventninger

Igjen, dette er en helt åpen oppgave.
Om det er mye av det over som er helt nytt er det for mye å forvente at en skal få opp en nettside eller noe lignende.
Det holder lenge med en gjennomgang av hva som finnes i API-et!

Det vi forventer er at dere gjør så godt dere kan, og at dere presenterer det dere har funnet ut :)

Lykke til!
