# EDDS_Docker
Repozitorija kurioje talpinama informacija apie darbą susijusį su konteinerizavimo sprendimais, pateikiamos specifikacijos, iliustracijos, išvardijami reikalavimai.

## Darbo specifikacijos aprašymas
Užduotis bus suskaidyta į 3 dalis:
1. Konteinerių inicializavimas - paleidimas
2. Konteinerių topologijos realizavimas, patikrinimas
3. Programinės įrangos panaudojimas, scenarijaus išpildymas

Tikslas šio darbo - atsiminti kaip sujungti mazgus lokaliame kompiuteriniame tinkle, izoliuoti tinklo srautą pagal sąsajų bei maršrutų konfigūravimą pasinaudojant konteinerizavimo sprendimus.
Konteinerizavimo rolė šiame darbe yra sudaryti virtualų scenarijų kuriame studentas galėtų ištestuoti tinklo srautą, išsiųsti paketus ir juos analizuoti ir vėliau išbandyti tinklo pralaidumo programas, kodą.

## Scenarijus

Scenarijus - Studentas dirba įmonėje kurioje kuriami mikrokompiuteriai skirti belaidžiam tinklui realizuoti. Vienas konteineris yra prieigos taškas *(angl. Access Point)*, kitas - stotis *(angl. Station)*. Įvyko pokyčiai produkcijoje - realizuojamas naujausias IEEE 802.11ax standartas produkcijoje, tad atitinkamai reikia įvertinti ar atitinkamu kanalu perduodamas pakankamas kiekis paketų tarp prieigos taško bei stoties per apribotą laiko tarpą.

Pavyzdys topologijos:

    ┌──────────────────────────────┐
    │          KOMPIUTERIS         │
    │                              │
    │ ┌───────────┐  ┌───────────┐ │
    │ │KONTEINERIS│  │KONTEINERIS│ │
    │ │           │  │           │ │
    │ │ ┌─┐   ┌─┐ │  │ ┌─┐   ┌─┐ │ │
    │ │ │ │ A │ │ │  │ │ │ B │ │ │ │
    │ └─┴─┴───┴┬┴─┘  └─┴┬┴───┴┬┴─┘ │
    │          │        │     │    │
    │          └────────┘     │    │
    │                         │    │
    │                         │    │
    │                         │    │
    │                         │    │
    │                         │    │
    │                ┌─┬─┬───┬┴┬─┐ │
    │                │ │ │ C │ │ │ │
    │                │ └─┘   └─┘ │ │
    │                │           │ │
    │                │KONTEINERIS│ │
    │                └───────────┘ │
    │                              │
    │                              │
    └──────────────────────────────┘
