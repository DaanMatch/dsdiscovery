# Database - w2

**Objective:** Using DaanMatch's Data Model, create a Schema and load DaanMatch data to database.

```{admonition} Patrick Contact Info
OH: Tuesday: 6:30 - 8:00pm PST <br>
guopatrick.comping@gmail.com <br> 
Mobile: 5107178380 <br>
GitHub: [shpatrickguo](https://github.com/shpatrickguo) 
```

## This Week's Objective

Get familiar with DaaMatch's data model, data, GitHub, AWS and your team.

````{panels}
:column: col-4
:card: border-2
Meiyi (Emily) Ding
^^^
emilyding@berkeley.edu
GitHub: EmilyDing201
---
Arthi Matrubutham
^^^
apm.butham8@berkeley.edu
GitHub: artmatru4b
---
Apoorv Lawange
^^^
apoorv.lawange@berkeley.edu <br>
GitHub: ALaw30
````

:::{admonition} What is a Data model?
:class: tip, dropdown
A data model is an abstract model that organizes elements of data and standardizes how they relate to one another and to the properties of real-world entities.
:::

:::{admonition} What is a Database?
:class: tip, dropdown
A database is information that is set up for easy access, management and updating.
:::

- [What are database schemas?](https://www.educative.io/blog/what-are-database-schemas-examples)
- [Difference between primary and foreign key](https://www.geeksforgeeks.org/difference-between-primary-key-and-foreign-key/)

## DaanMatch's Data Model

:::{figure-md} Data-Model
:class: myclass

<img src="img/drawsql.png" alt="DaanMatch Data Model" class="bg-primary mb-1" width="600px">

DaanMatch's Data Model visualized using DrawSQL.
:::

## Git

DaanMatch is using GitHub for version control. Code submissions will be done through pull requests.

✅ **TODO:** To enable effective collaboration please download/review the following

- [ ] [Download Git](https://git-scm.com/downloads)
- [ ] [Join DaanMatch's GitHub organization](https://github.com/DaanMatch)
- [ ] [GitHub Desktop](https://desktop.github.com/) (Optional)
- [ ] [Basic Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
- [ ] [Git Branching Naming conventions](https://codingsight.com/git-branching-naming-convention-best-practices/)
- [ ] [How to write good commit messages](https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/)

**TODO:** Clone [Data Model](https://github.com/DaanMatch/ngodata/tree/main/Data%20Model)

- [ ] Create a GitBranch and add your name to CONTRIBUTING.md on [Data Model](https://github.com/DaanMatch/ngodata/tree/main/Data%20Model).

## How to get our data

DaanMatch's data files are stored on AWS S3.

:::{admonition} What is S3?
:class: tip, dropdown

Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. You can use Amazon S3 to store and retrieve any amount of data at any time, from anywhere.
:::

✅ **TODO:** Load data from AWS S3 to Jupyter notebook.

- [ ] [Follow Connection instructions on Codebook](https://github.com/DaanMatch/Codebook)

```{warning}
Login information found in #team-shpg on Slack. Please keep login information private.
```

- [ ] Run the following in Jupyter Notebook and submit in shpg-1 folder in [Data Model](https://github.com/DaanMatch/ngodata/tree/main/Data%20Model)

```
import pandas as pd
import io
import boto3

client = boto3.client('s3')
obj = client.get_object(Bucket='daanmatchdatafiles', Key='webscrape-fall2021/Final_IndiaNGO.csv')
df = pd.read_csv(io.BytesIO(obj['Body'].read()), low_memory=False)
df.head()
```

### File Assignment

- **Arthi:** "giveIndia - giveIndia.csv"
- **Emily:** "InvestIndia.csv"
- **Apoorv:** "helpyourngo.json"

✅ **TODO:** <2 min presentation about your data

## Resources ℹ️

- [DS Discovery Scheduling](https://docs.google.com/spreadsheets/d/1uwpQJ0VeinKC-fPI7-ZN-RinID5Y0VamjWiwza7-otY/edit#gid=1395204760)
- [Codebook Documentation](https://github.com/DaanMatch/Codebook)
- [Data Model](https://github.com/DaanMatch/ngodata/tree/main/Data%20Model)
- [Webscrapers](https://github.com/DaanMatch/webscrape)
