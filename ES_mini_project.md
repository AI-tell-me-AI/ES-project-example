# EXPERT SYSTEMS PROJECT	     Name, surname __________________________________

Design a a small ES that helps choose a home heating system and implement it in the JavaDON environment.

ES user requirements are as follows:

Users that are sensitive to cold must have a centralized heating system. Otherwise, centralized systems are most beneficial to houses that are 50 square meters or more in area. In all other cases, non-centralized systems are a better option.

Solid fuel centralized heating systems (description: wood or coal central furnace with radiators in all rooms) are the only low-priced centralized heating systems. When the price does not need to be as low as possible, gas central heating systems (description: gas fuel central furnace with radiators in all rooms), city network central heating systems (description: radiators in all rooms connected to the city heating plant) or a centralized electric system may be used (description: electric central furnace with radiators in all rooms), depending on the availability of a gas network connection for the house, the city network heating connection or the availability of electricity. If neither gas nor city network connections are available but only electricity, then a centralized electric system may be used.

Non-centralized electric heating (description: electric furnace, "Norwegian" radiators) is preferable to non-centralized solid fuel heating (description: fireplace, solid fuel stove) in case the house has electricity. Otherwise, non-centralized solid fuel heating is the only option.


**NOTE: There is no single, optimal, solution for this project. The proposed ES can be designed and implemented in several ways so that each implementation would be correct.**






# SOLUTION (one possible solution, there can be alternative correct solutions)

## DESIGN

**Title**: ES for choosing a home heating system

**Expert**: Heating plant engineer
User: Property owner

**Identified solutions (output variables)**: The solutions provided by ES consist of two parts. The first part is the type of heating system (it can be centralized or non-centralized). The second part consists of a specific system and type of fuel (and for each solution a description needs to be displayed as well):

    1. Non-centralized electric heating (description: electric furnace, "Norwegian" radiators)
    2. Non-centralized solid fuel heating (description: fireplace, solid fuel stove)
    3. Electric central heating (description: electric central furnace with radiators in all rooms)
    4. Gas central heating (description: gas fuel central furnace with radiators in all rooms)
    5. Central heating with solid fuels (description: wood or coal central furnace with radiators in all rooms)
    6. Central heating via the city network (description: radiators in all rooms connected to the city heating plant)

**Identified input variables and their associated questions**:
    1. Area of the house in square meters
    2. Sensitivity to cold
    3. Heating price
    4. Electricity available in the house
    5. LPG gas network available
    6. City heating network available

ES asks the following questions (and expects the following answers):

    1. What is the area of the house in square meters? (50 or more, less than 50)
    2. Are you sensitive to cold? (Yes, No)
    3. Is it important that the price of heating be as low as possible? (Yes, No)
    4. Does the house have electricity? (Yes, No)
    5. Is it possible to connect to LPG gas network? (Yes, No)
    6. Is it possible to connect to the city's heating network? (Yes, No)

**The rules identified are**:
    1. If the user is sensitive to cold, the type of heating system is centralized.
    2. If the user is not sensitive to the cold and the area of the house is less than 50 square meters, the type of heating system is non-centralized.
    3. If the area of the house is 50 square meters or more, the type of heating system is centralized.
    4. If the type of heating system is centralized and it is not important that the price be as low as possible and there is the possibility of connecting to gas, then the concrete solution is gas central heating.
    5. If the type of heating system is centralized and it is not important that the price be as low as possible and there is a possibility of connection to the city heating network, then the concrete solution is central heating via the city network.
    6. If the type of heating system is centralized and it does not matter that the price is as low as possible and the house has electricity and there is no possibility of connecting to gas and there is no possibility of connecting to the city's heating network, then the concrete solution is electric central heating.
    7. If the type of heating system is centralized and it is important that the price be as low as possible, then the concrete solution is central heating with solid fuels.
    8. If the type of heating system is non-centralized and the house has electricity, then the concrete solution is non-centralized heating with electricity.
    9. If the type of heating system is non-centralized and the house does not have electricity, then the concrete solution is non-centralized solid fuel heating.

## IMPLEMENTATION

The implementation of this ES in JavaDON is provided in an attached file (ES_HEATING.jdml). JavaDON binaries can be downloaded [here](http://ai.fon.bg.ac.rs/wp-content/uploads/2015/04/ES-JavaDON-2014.zip)

1. unzip the JavaDON file after downloading and double-click on JavaDON.jar to start
2. Choose File -> Open from the main menu and navigate to ES_HEATING.jdml file to open the provided ES implementation.

