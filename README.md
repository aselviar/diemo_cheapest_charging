# diemo_cheapest_charging
Goal:

Further development of the GIS platform of the Swiss Federal Office of Energy (SFOE): Add price information to the charging stations and find the cheapest option around for electric car drivers.
Idea:

A Charge Point Operator (CPO) is a company operating a pool of charging points. A CPO provides value by connecting smart charging devices to E-Mobility Service Providers (EMPs). An EMP is a company offering an EV charging service to EV drivers. EMPs provide value by enabling access to a variety of charging points around a geographic area. One company can be CPO and EMP at the same time.

As a result, at each charging station of a certain CPO pool, different EMPs have different prices. The idea is to find the cheapest charging station around a user according to their EMP subscription(s).
Big picture:

Big differences in EMP prices exist at certain charging stations. This solution should help users to choose the best pricing options. Transparency and market performance is increased and the user/consumer is better informed.
Data:

    Get information from Ich-tanke-strom.ch
    Get information from EMP/CPO websites
    Statistical and availability information available in .json format: https://opendata.swiss/dataset/ladestationen-fuer-elektroautos.
