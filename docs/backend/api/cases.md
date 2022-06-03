# Cases

## Queries

**casesByProfession( profession: <String\> ) => <Case[] \>**

Get cases by profession.


| Example: |
|---|
| if(stat.casesByProfession == null) stat.casesByProfession = [0,0,0,0,0,0] |

## Mutations

**report( data: <CaseCreateInput\> ) => <Case\>**

Adds a case record to the CaseRegistry.sol smart contract and to the db.



| Example: |
|---|
|caseRegistryInstance.report ( <br /> caseToReport.companyName, <br /> caseToReport.caseType, <br /> caseToReport.description, <br /> caseToReport.region, <br /> caseToReport.profession, <br /> caseToReport.gender, <br /> caseToReport.ageRange, <br /> caseToReport.experience <br />); |

