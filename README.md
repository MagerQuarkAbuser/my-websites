classDiagram
    class Tierarztpraxis {
        - name: String
        - adresse: String
    }

    class Tierarzt {
        - name: String
        - fachgebiet: String
        + behandeln(): void
    }

    class Haustier {
        # name: String
        # alter: int
        # gewicht: double
        + fressen(): void
    }

    class Hund {
        - rasse: String
        + bellen(): void
    }

    class Katze {
    }

    class Tierhalter {
        - name: String
        - telefonnummer: String
        + rechnungBezahlen(): void
    }

    %% Assoziationen (normale Linien, keine Rauten für Aggregation/Komposition)
    Tierarztpraxis "1" -- "1..*" Tierarzt : hat angestellte
    Tierarztpraxis "1" -- "0..*" Haustier : betreut
    Tierhalter "1" -- "1..*" Haustier : besitzt

    %% Vererbungen (hohler Pfeil)
    Haustier <|-- Hund
    Haustier <|-- Katze
