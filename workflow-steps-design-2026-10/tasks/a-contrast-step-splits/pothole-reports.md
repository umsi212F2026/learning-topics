A city takes reports of potholes from its residents through a phone app, and handles them with a
weekly workflow. About 120 reports come in a week, many of them about the same few potholes.

1. Collect the week's pothole reports from the app into one list. (a program)
2. Merge the reports that describe the same pothole into one entry, sort the merged potholes by
   district, and write a short, plain description of each pothole saying where it is and how bad
   the reports say it is. (an AI agent)
3. Choose which potholes get fixed this week, then group the chosen potholes into one route for
   each workday, and text each resident who reported one the day it will be fixed. (the road
   supervisor, then a program)
4. Fill each pothole on the routes and mark it fixed in the app. (the road crew)

Some of these steps do more than one step's work.

### q1

Nadia, Owen and Paloma each propose splitting step 2 into two steps.

1. Nadia: split after the agent merges the reports, and pass the merged potholes straight on
   without storing them.
2. Owen: split after the agent sorts the potholes by district, and keep that sorted list, one line
   per pothole with its reports.
3. Paloma: split after the agent merges the reports, and keep the list of merged potholes, each
   with the reports it came from.

Which proposal is the best division of step 2?

1. Nadia's
2. Owen's
3. Paloma's

### q2

Quinn, Rosa and Samir each propose splitting step 3 into two steps.

1. Quinn: split after the program groups the potholes into routes, and keep the routes, each
   pothole with its day.
2. Rosa: split after the supervisor chooses this week's potholes, and keep the sorted list of
   potholes from step 2.
3. Samir: split after the supervisor chooses this week's potholes, and keep the list of potholes
   the supervisor chose.

Which proposal is the best division of step 3?

1. Quinn's
2. Rosa's
3. Samir's
