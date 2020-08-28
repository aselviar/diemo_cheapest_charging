# diemo_cheapest_charging
Goal:

Further development of the GIS platform of the Swiss Federal Office of Energy (SFOE): Add price information to the charging stations and find the cheapest option around for electric car drivers.

Idea:

A Charge Point Operator (CPO) is a company operating a pool of charging points. A CPO provides value by connecting smart charging devices to E-Mobility Service Providers (EMPs). An EMP is a company offering an EV charging service to EV drivers. EMPs provide value by enabling access to a variety of charging points around a geographic area. One company can be CPO and EMP at the same time.

As a result, at each charging station of a certain CPO pool, different EMPs have different prices. The idea is to find the cheapest charging station around a user according to their EMP subscription(s).

Big picture:

Big differences in EMP prices exist at certain charging stations. This solution should help users to choose the best pricing options. Transparency and market performance is increased and the user/consumer is better informed.

Data:

- Get information from Ich-tanke-strom.ch
- Get information from EMP/CPO websites (see list below)
- Statistical and availability information available in .json format: https://opendata.swiss/dataset/ladestationen-fuer-elektroautos.

EMPs:
- evpass
- MOVE
- Swisscharge: https://map.swisscharge.ch/
- Plug'n'Roll
- Plugsurfing
- NewMotion
- Bosch Charge my EV
- BMW ChargeNow (BMW Charging, MINI Charging)
- Volkswagen Charge&Fuel Card
- Renault Z.E. Pass
- EnBW mobility+ App

## Where can you find the data?

The static data of ich-tanke-strom.ch is found here: https://opendata.swiss/de/dataset/ladestationen-fuer-elektroautos/resource/e33957be-180a-422b-90a5-fbfe9774927a

This json contains static information (location, operator name, unique charging station id etc.) for all the public charging stations in Switzerland (listed in ich-tanke-strom.ch). 

```json
       {
          "Address": {
            "City": "8008 Zürich",
            "Country": "CHE",
            "HouseNum": null,
            "PostalCode": null,
            "Street": "Lengghalde 2",
            "Floor": null,
            "Region": null,
            "Timezone": null
          },
          "IsOpen24Hours": true,
          "ChargingStationId": "CH*SWIEE9973",
          "GeoCoordinates": {
            "Google": "8.573595,47.351939"
          },
          "lastUpdate": null,
          "HotlinePhoneNum": "0488848044",
          "ClearinghouseID": null,
          "OpeningTimes": null,
          "GeoChargingPointEntrance": {
            "Google": "None,None"
          },
          "ChargingStationName": "CH*SWIEE9973",
          "EnChargingStationName": null,
          "HubOperatorID": null,
          "Plugs": [
            "Type 2 Outlet"
          ],
          "Accessibility": "Unspecified",
          "EvseID": "CH*SWIEE9974",
          "DynamicInfoAvailable": "true",
          "ChargingFacilities": [
            {
              "power": "22"
            }
          ],
          "IsHubjectCompatible": true,
          "ChargingModes": [
            "Mode_3"
          ],
          "MaxCapacity": 22,
          "PaymentOptions": null,
          "AdditionalInfo": null,
          "ChargingPoolID": null,
          "deltaType": "update",
          "ValueAddedServices": [
            "Reservation"
          ],
          "AuthenticationModes": [
            "NFC RFID Classic",
            "Direct Payment",
            "REMOTE"
          ]
        }
      ],
      "OperatorID": "CH*SWISSCHARGE",
      "OperatorName": "Swisscharge"
    }
```

In the example above you see a charging station from the operator swisscharge. This charging station has a unique ChargingStationId. The location of the charging station is also depicted.

The price information and the location of all charging stations that are accesible to swisscharge customers can be found on the website of swisscharge https://map.swisscharge.ch/. If you choose a charging station and click on "charge now" (bottom left corner of the screen), you get the price information. 

The idea of the challenge is to find a way to find the prices for each unique id, depending on the EMP subscription. That means the programm should be able to locate the charging station with the unique id on the map and the price information has to be acquired automatically from the EMPs' website. This could be done for example via web scrapping or web crawling. 

The same applies for all the EMPs. 

## Ultimate goal

The ultimate goal is to have a list of the prices of each service provider for each charging station. This is useful for two reasons:

- Enabling subscribers of certain service providers to choose the cheapeast charging option within a certain km range
- Achieving price transparency and thus helping to prevent market inefficiencies and costly and strange charging policies that rely on the current price intransparency.
