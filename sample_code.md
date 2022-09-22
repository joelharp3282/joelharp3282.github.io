# This is an example of the I wrote for a spatial programming class.

#### TEST
```javascript
if (isAwesome){
  return true
}
```



---
```javascript
## Nested Conditional Statements for Language or Precinct.

### For precinct input the select function is utilized for visiualization.

# Trying to set up the conditionals for the different languages that were most likely to be asked.
# More languages could be added as needed.

actionNeed = input("Please select language or Precinct Number please: ") # user inputs what they are looking help for.

if actionNeed.lower() == "language": # if language the nested conditional provides different answers for different languages.
    langNeed = input("Please Provide language needed: ")
    if langNeed.lower() == "spanish":
        print("Spanish is already available on all Florida ballots.")
    elif langNeed.lower() == "english":
        print("English is already available on all Florida ballots.")
    elif langNeed.lower() == "creole":
        print("This language can be requested on a ballot by calling the Supervisor of Elections Office.")
    else:
        print("Please contact the Supervior of Elections Office to coordinate other languages via phone.") # for all languages not considered above
        
elif actionNeed == "Precinct Number": # if precinct is selected it would provide the answer below and shows just the one location on the map.
    numNeed = input("Please provide your Precinct Number: ")
    print("All Florida ballots are printed in English and Spanish, other languages are available via phone.")
    userquery = '"{0}"= \'{1}\''.format("Precinct N", numNeed) # this formats the users input with the proper column to highlight which locations was input
    print(userquery)
    import arcpy
    arcpy.env.workspace = "C:/Users/marco/Desktop/Term_Project_Python/StateData/precinct_126_coord" # workspace for the precinct locations
    arcpy.analysis.Select("precinct_coord-point.shp", "C:/Users/marco/Desktop/Term_Project_Python/StateData/precinct_location", userquery)
    ```
