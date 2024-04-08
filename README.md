# FRC-2024-Scouting-Data

<details>

<summary>Mishawaka Data</summary>

## Mishawaka Data

Raw Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Mishawaka/scouting-export-2024-3-1-15-28-54.csv
```

Formated Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Mishawaka/Mishawaka-Data.csv
```

Match Schedule

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Mishawaka/scouting-match-schedule-2024-3-1-15-28-57.csv
```

</details>


<details>

<summary>Columbus Data</summary>

## Columbus Data

Raw Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Columbus/scouting-export-2024-3-1-15-29-26.csv
```

Formated Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Columbus/Columbus-Data.csv
```

Match Schedule

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Columbus/scouting-match-schedule-2024-3-1-15-29-29.csv
```

</details>

<details>

<summary>Plainfield Data</summary>

## Plainfield Data

Raw Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Plainfield/scouting-export-2024-3-1-15-29-48.csv
```

Formated Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Plainfield/Plainfield-Data.csv
```

Match Schedule

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Plainfield/scouting-match-schedule-2024-3-1-15-29-50.csv
```

</details>

<details>

<summary>Washington Data</summary>

## Washington Data

Raw Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Washington/scouting-export-2024-3-1-15-30-12.csv
```

Formated Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Washington/Washington-Data.csv
```

Match Schedule

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/Washington/scouting-match-schedule-2024-3-1-15-30-14.csv
```

</details>

<details>

<summary>State Data</summary>

## State Data

Raw Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/State/scouting-export-2024-3-1-15-28-12.csv
```

Formated Data Link

```
https://raw.githubusercontent.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/main/Indiana-Scouting-Data/State/2024-State-Totals.csv
```

Match Schedule

```
https://github.com/FRC-Scouting-Data/FRC-2024-Scouting-Data/blob/main/Indiana-Scouting-Data/State/scouting-match-schedule-2024-3-1-15-28-8.csv
```

</details>

<details>

<summary>Excel Match Data Query</summary>

## Excel Match Data Query

Excel Match Data Query for RAW data

```txt
let
    Source = Csv.Document(Web.Contents("https://api.scout.kennan.tech/dump/2024ineva/CSV/"),[Delimiter=",", Columns=46, Encoding=1252, QuoteStyle=QuoteStyle.None]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"matchnumber", Int64.Type}, {"reportedRedScore", Int64.Type}, {"reportedBlueScore", Int64.Type}, {"teamNumber", Int64.Type}, {"noshow", Int64.Type}, {"autonote1", Int64.Type}, {"autonote2", Int64.Type}, {"autonote3", Int64.Type}, {"autonote4", Int64.Type}, {"autonote5", Int64.Type}, {"autonote6", Int64.Type}, {"autonote7", Int64.Type}, {"autonote8", Int64.Type}, {"autoamp", Int64.Type}, {"autospeaker", Int64.Type}, {"leave", Int64.Type}, {"teleopamp", Int64.Type}, {"teleopspeaker", Int64.Type}, {"shotfromsubwoofer", Int64.Type}, {"shotfrompodium", Int64.Type}, {"shotfromwing", Int64.Type}, {"shotfromoutside", Int64.Type}, {"teleoptrap", Int64.Type}, {"climbtime", Int64.Type}, {"onstageorder", Int64.Type}, {"harmonizeqty", Int64.Type}, {"buddy", Int64.Type}, {"spotlit", Int64.Type}, {"floorpickup", Int64.Type}, {"sourcepickup", Int64.Type}, {"understage", Int64.Type}, {"playeddefense", Int64.Type}, {"receiveddefense", Int64.Type}, {"died", Int64.Type}, {"tipped", Int64.Type}, {"broke", Int64.Type}, {"startTime", type datetime}}),
    #"Added Conditional Column" = Table.AddColumn(#"Changed Type", "StartA", each if [startingpos] = "a" then 1 else 0),
    #"Reordered Columns" = Table.ReorderColumns(#"Added Conditional Column",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "autoamp", "autospeaker", "leave", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "harmonizeqty", "buddy", "spotlit", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke"}),
    #"Added Conditional Column1" = Table.AddColumn(#"Reordered Columns", "StartB", each if [startingpos] = "b" then 1 else 0),
    #"Reordered Columns1" = Table.ReorderColumns(#"Added Conditional Column1",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "autoamp", "autospeaker", "leave", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "harmonizeqty", "buddy", "spotlit", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke"}),
    #"Added Conditional Column2" = Table.AddColumn(#"Reordered Columns1", "StartC", each if [startingpos] = "c" then 1 else 0),
    #"Added Conditional Column3" = Table.AddColumn(#"Added Conditional Column2", "StartD", each if [startingpos] = "d" then 1 else 0),
    #"Reordered Columns2" = Table.ReorderColumns(#"Added Conditional Column3",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "StartC", "StartD", "autoamp", "autospeaker", "leave", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "harmonizeqty", "buddy", "spotlit", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke"}),
    #"Changed Type1" = Table.TransformColumnTypes(#"Reordered Columns2",{{"StartA", Int64.Type}, {"StartB", Int64.Type}, {"StartC", Int64.Type}, {"StartD", Int64.Type}}),
    #"Added Conditional Column4" = Table.AddColumn(#"Changed Type1", "OnstageFirst", each if [onstageorder] = 1 then 1 else 0),
    #"Added Conditional Column5" = Table.AddColumn(#"Added Conditional Column4", "OnstageSecond", each if [onstageorder] = 2 then 1 else 0),
    #"Added Conditional Column6" = Table.AddColumn(#"Added Conditional Column5", "OnstageThird", each if [onstageorder] = 3 then 1 else 0),
    #"Reordered Columns3" = Table.ReorderColumns(#"Added Conditional Column6",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "StartC", "StartD", "autoamp", "autospeaker", "leave", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "OnstageFirst", "OnstageSecond", "OnstageThird", "harmonizeqty", "buddy", "spotlit", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke"}),
    #"Changed Type2" = Table.TransformColumnTypes(#"Reordered Columns3",{{"OnstageFirst", Int64.Type}, {"OnstageSecond", Int64.Type}, {"OnstageThird", Int64.Type}}),
    #"Added Conditional Column7" = Table.AddColumn(#"Changed Type2", "HarmonizeWith1", each if [harmonizeqty] = 1 then 1 else 0),
    #"Added Conditional Column8" = Table.AddColumn(#"Added Conditional Column7", "HarmonizeWith2", each if [harmonizeqty] = 2 then 1 else 0),
    #"Changed Type3" = Table.TransformColumnTypes(#"Added Conditional Column8",{{"HarmonizeWith1", Int64.Type}, {"HarmonizeWith2", Int64.Type}}),
    #"Reordered Columns4" = Table.ReorderColumns(#"Changed Type3",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "StartC", "StartD", "autoamp", "autospeaker", "leave", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "OnstageFirst", "OnstageSecond", "OnstageThird", "harmonizeqty", "HarmonizeWith1", "HarmonizeWith2", "buddy", "spotlit", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke"}),
    #"Added Conditional Column9" = Table.AddColumn(#"Reordered Columns4", "Spotlit1", each if [spotlit] = 1 then 1 else 0),
    #"Added Conditional Column10" = Table.AddColumn(#"Added Conditional Column9", "Spotlit2", each if [spotlit] = 2 then 1 else 0),
    #"Added Conditional Column11" = Table.AddColumn(#"Added Conditional Column10", "Spotlit3", each if [spotlit] = 3 then 1 else 0),
    #"Changed Type4" = Table.TransformColumnTypes(#"Added Conditional Column11",{{"Spotlit1", Int64.Type}, {"Spotlit2", Int64.Type}, {"Spotlit3", Int64.Type}}),
    #"Reordered Columns5" = Table.ReorderColumns(#"Changed Type4",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "StartC", "StartD", "autoamp", "autospeaker", "leave", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "OnstageFirst", "OnstageSecond", "OnstageThird", "harmonizeqty", "HarmonizeWith1", "HarmonizeWith2", "buddy", "spotlit", "Spotlit1", "Spotlit2", "Spotlit3", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke"}),
    #"Reordered Columns6" = Table.ReorderColumns(#"Reordered Columns5",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "StartC", "StartD", "autoamp", "autospeaker", "leave", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "OnstageFirst", "OnstageSecond", "OnstageThird", "harmonizeqty", "HarmonizeWith1", "HarmonizeWith2", "buddy", "spotlit", "Spotlit1", "Spotlit2", "Spotlit3", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke"}),
    #"Added Custom" = Table.AddColumn(#"Reordered Columns6", "AutoScore", each if [noshow]=1 then 0 else ([leave]*2)+([autoamp]*2)+([autospeaker]*5)),
    #"Added Conditional Column15" = Table.AddColumn(#"Added Custom", "Park", each if [onstageorder] = 4 then 1 else 0),
    #"Reordered Columns7" = Table.ReorderColumns(#"Added Conditional Column15",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "StartC", "StartD", "autoamp", "autospeaker", "leave", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "Park", "OnstageFirst", "OnstageSecond", "OnstageThird", "harmonizeqty", "HarmonizeWith1", "HarmonizeWith2", "buddy", "spotlit", "Spotlit1", "Spotlit2", "Spotlit3", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke", "AutoScore"}),
    #"Changed Type6" = Table.TransformColumnTypes(#"Reordered Columns7",{{"Park", Int64.Type}}),
    #"Added Custom1" = Table.AddColumn(#"Changed Type6", "TeleopScoreUnamplified", each if [noshow] = 1 then 0 else ([teleopamp]*1)+([teleopspeaker]*2)+([Park]*1)+(if ([onstageorder] < 4 and [onstageorder] > 0) then 3 else 0)+(if[harmonizeqty] = null then 0 else [harmonizeqty]*2)+([teleoptrap]*5)),
    #"Added Custom2" = Table.AddColumn(#"Added Custom1", "TeleopScoreAmplified", each if [noshow] = 1 then 0 else ([teleopamp]*4)+([teleopspeaker]*5)+([Park]*1)+(if ([onstageorder] < 4 and [onstageorder] > 0) then 3 else 0)+(if[harmonizeqty] = null then 0 else [harmonizeqty]*2)+([teleoptrap]*5)),
    #"Added Custom3" = Table.AddColumn(#"Added Custom2", "TeleopScoreAveraged", each ([TeleopScoreUnamplified]+[TeleopScoreAmplified])/2),
    #"Changed Type7" = Table.TransformColumnTypes(#"Added Custom3",{{"AutoScore", Int64.Type}, {"TeleopScoreUnamplified", Int64.Type}, {"TeleopScoreAmplified", Int64.Type}, {"TeleopScoreAveraged", type number}}),
    #"Reordered Columns8" = Table.ReorderColumns(#"Changed Type7",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "StartC", "StartD", "autoamp", "autospeaker", "leave", "AutoScore", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "Park", "OnstageFirst", "OnstageSecond", "OnstageThird", "harmonizeqty", "HarmonizeWith1", "HarmonizeWith2", "buddy", "TeleopScoreUnamplified", "TeleopScoreAmplified", "TeleopScoreAveraged", "spotlit", "Spotlit1", "Spotlit2", "Spotlit3", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke"}),
    #"Added Custom4" = Table.AddColumn(#"Reordered Columns8", "Unamplified Score", each [AutoScore]+[TeleopScoreUnamplified]),
    #"Added Custom5" = Table.AddColumn(#"Added Custom4", "Amplified Score", each [AutoScore]+[TeleopScoreAmplified]),
    #"Added Custom6" = Table.AddColumn(#"Added Custom5", "AverageScore", each [AutoScore]+[TeleopScoreAveraged]),
    #"Changed Type8" = Table.TransformColumnTypes(#"Added Custom6",{{"Unamplified Score", Int64.Type}, {"Amplified Score", Int64.Type}, {"AverageScore", type number}}),
    #"Added Custom7" = Table.AddColumn(#"Changed Type8", "Climbed", each if [onstageorder]=null then null else if [onstageorder]>0 and [onstageorder]<4 then 1 else 0),
    #"Reordered Columns9" = Table.ReorderColumns(#"Added Custom7",{"matchKey", "matchnumber", "alliance", "startTime", "eventKey", "reportedWinningAlliance", "reportedRedScore", "reportedBlueScore", "scoutname", "teamNumber", "noshow", "autonote1", "autonote2", "autonote3", "autonote4", "autonote5", "autonote6", "autonote7", "autonote8", "startingpos", "StartA", "StartB", "StartC", "StartD", "autoamp", "autospeaker", "leave", "AutoScore", "teleopamp", "teleopspeaker", "shotfromsubwoofer", "shotfrompodium", "shotfromwing", "shotfromoutside", "teleoptrap", "climbtime", "onstageorder", "Park", "OnstageFirst", "OnstageSecond", "OnstageThird", "Climbed", "harmonizeqty", "HarmonizeWith1", "HarmonizeWith2", "buddy", "TeleopScoreUnamplified", "TeleopScoreAmplified", "TeleopScoreAveraged", "spotlit", "Spotlit1", "Spotlit2", "Spotlit3", "floorpickup", "sourcepickup", "understage", "playeddefense", "receiveddefense", "died", "tipped", "broke", "Unamplified Score", "Amplified Score", "AverageScore"}),
    #"Changed Type9" = Table.TransformColumnTypes(#"Reordered Columns9",{{"Climbed", Int64.Type}, {"amplifications", Int64.Type}})
in
    #"Changed Type9"
```

</details>

<details>

<summary>Excel Schedule Query</summary>

## Excel Schedule Query

Excel Schedule Query

```txt
let
    Source = Csv.Document(Web.Contents("https://api.scout.kennan.tech/dump/schedule/2024inmis/csv/"),[Delimiter=",", Columns=8, Encoding=65001, QuoteStyle=QuoteStyle.None]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"matchKey", type text}, {"startTime", type text}, {"red1", Int64.Type}, {"red2", Int64.Type}, {"red3", Int64.Type}, {"blue1", Int64.Type}, {"blue2", Int64.Type}, {"blue3", Int64.Type}})
in
    #"Changed Type"
```

</details>