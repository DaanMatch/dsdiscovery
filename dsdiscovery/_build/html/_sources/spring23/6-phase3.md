# Phase 3: Transforming Data

Now we transform the data to fit the DaanMatch's data model. This involves a close examination of the data model and identifying how the existing data files can be adjusted to fit into this model. The process of transforming the data to fit the data model will likely involve a significant amount of data cleaning.

## Data Schema

A data schema is a blueprint or a plan that outlines the logical structure of a database, data warehouse, or any other data repository. It defines how data is organized, stored, and accessed, and it specifies the relationships and constraints between different data elements.

```
CREATE TABLE IF NOT EXISTS public.Project
(
 ProjectId uuid,
 NgoId uuid,
 ProjectName character varying(255),
 ProjectLocation character varying(255),
 StartDate date,
 EndDate date,
 NatureOfIntervention character varying(255),
 ProjectSector character varying(255),
 ScheduleVii text,
 SdgIndicator text,
 Budget numeric,
 ExternalFundingReceived numeric,
 BeneficiaryGroup text,
 NoOfBeneficiaries integer,
 ProjectType character varying(255),
 MediaLink text,
 DocumentsLink text,
 Status character varying(255),
 Description text,
 Objective text,
 Achievements text,
 WhatsNext text,
 Manager character varying(255),
 BudgetAllocation numeric,
 BudgetUtlization numeric,
 Impact character varying(255),
 ReportLink text
);

CREATE TABLE IF NOT EXISTS public.Beneficiary
(
 BeneficiaryId uuid NOT NULL,
 NgoId uuid,
 ProjectId uuid,
 BeneficiaryName text,
 Age integer,
 Gender text,
 BeneficiaryLocation text,
 Phone text,
 Email text,
 FamilySize integer,
 Occupation text,
 Income numeric,
 EducationLevel text,
 MaritalStatus text,
 HealthStatus text,
 MediaLink text,
 Religion text,
 Disability text,
 EconomicStatus text,
 AadhaarNo text,
 RationCard text,
 Notes text
);

CREATE TABLE IF NOT EXISTS public.NgoContact
(
 NgoId UUID,
 NgoName text,
 OrgEmail text,
 OfficePhone text,
 PrimaryPoc text,
 PrimaryPocPhone text,
 SecondaryPoc text,
 SecondaryPocPhone text,
 MailingAddress text,
 PhysicalAddress text,
 FieldOffices text,
 OrgType text,
 OrgWebsite character varying(2048),
 Facebook character varying(2048),
 Twitter character varying(2048),
 Instagram character varying(2048),
 Youtube character varying(2048),
 Whatsapp text,
 OtherSocials text,
 ExecutiveDirector text,
 TechnicalSupport text,
 ChairmanName text,
 ChairmanMobile text,
 ChairmanEmail text,
 ViceChairmanName text,
 ViceChairmanMobile text,
 ViceChairmanEmail text,
 SecretaryName text,
 SecretaryMobile text,
 SecretaryEmail text,
 AssistantSecretaryName text,
 AssistantSecretaryMobile text,
 AssistantSecretaryEmail text
);

CREATE TABLE IF NOT EXISTS public.NgoBackground
(
    NgoId uuid,
    Logo text,
    YearEstablished date,
    MissionStatement text,
    Vision text,
    Objectives text,
    LegalStatus text,
    AreasOfOperation character varying(255),
    SectorsOfOperation character varying(255),
    ActiveStatus text,
    sourceUrl text
);

CREATE TABLE IF NOT EXISTS public.NgoRegistration
(
    NgoId uuid,
    NgoType character varying(255),
    RegNo character varying(255),
    RegDate date,
    Registrar character varying(255),
    "12ANo" character varying(255),
    "12ARegdate" date,
    "12AUpload" text,
    "80GNo" character varying(255),
    "80GRegdate" date,
    "80GUpload" text,
    "35ACNo" character varying(255),
    "35ACRegdate" date,
    "35ACUpload" text,
    "FCRANo" character varying(255),
    "FCRARegdate" date,
    NatureListed text,
    "FCRAStatus" text,
    "FCRAExpiration" date,
    "FCRAUpload" text,
    "PAN" character varying(255),
    "TAN" character varying(255),
    "GST" character varying(255),
    Notes text
);

CREATE TABLE IF NOT EXISTS public.NgoFinance
(
    NgoId uuid,
 FiscalYear integer,
 TotalIncome numeric,
 TotalGrant numeric,
 TotalExpense numeric,
 TotalAssets numeric,
 TotalLiabilities numeric,
 TotalFundingGap numeric,
 SourceOfFunds character varying,
 MajorFunders text,
 BudgetAllocation numeric,
 BudgetUtilization numeric,
 AuditReport text,
 AvgMonthlyExpenditure numeric,
 AvgMonthlyOverhead numeric,
 LongTermLoan text,
 FulltimeEmployees integer,
 ParttimeEmployees integer,
 EmploymentExpenses numeric,
 FulltimeVolunteers integer,
 ParttimeVolunteers integer,
 VolunteerExpenses numeric,
 Consultants integer,
 ConsultantExpenses numeric,
 OccupancyExpenses numeric,
 FundraisingExpenses numeric
);

CREATE TABLE IF NOT EXISTS public.Image
(
    ImageId uuid,
 ImageName text,
 FileLink text,
 Format text,
 ImageSize integer,
 Resolution text,
 ColorDepth integer,
 CameraManufacturer text,
 CameraModel text,
 CreationDate date,
 ModificationDate date,
 Description text,
 Latitude numeric,
 Longitude numeric,
 Altitude numeric,
 CompassDirection text
);

CREATE TABLE IF NOT EXISTS public.Geography
(
    Geocode character varying(255),
    Country character varying(255),
    State character varying(255),
    "PIN" character varying(255),
    District character varying(255),
    SubDistrict character varying(255),
    Municipality character varying(255),
    City character varying(255),
    Town character varying(255),
    Block character varying(255),
    Village character varying(255),
    Ward character varying(255)
);

CREATE TABLE IF NOT EXISTS public.Video
(
    VideoId uuid,
    VideoName text,
    FileLink text,
    FrameRate numeric,
    VideoSize integer,
    Resolution text,
    VideoCodec text,
    AudioCodec text,
    Bitrate integer,
    CreationDate date,
    ModificationDate date,
    Description text,
    Latitude numeric,
    Longitude numeric,
    Altitude numeric,
    Tags text
);

CREATE TABLE IF NOT EXISTS public.Audio
(
    AudioId uuid,
    AudioName text,
    FileLink text,
    Format text,
    AudioSize integer,
    Bitrate integer,
    Duration text,
    Channels integer,
    SampleRate integer,
    CreationDate date,
    ModificationDate date,
    Description text,
    Latitude numeric,
    Longitude numeric,
    RecordingDevice text,
    RecordingSoftware text,
    Codec text,
    Notes text
)
```

## Data processing in scrapy

[Item Loader Tutorial](https://towardsdatascience.com/a-minimalist-end-to-end-scrapy-tutorial-part-ii-b917509b73f7)
[Item Loader Documentation](https://docs.scrapy.org/en/latest/topics/loaders.html)

## Connecting to posgreSQL through Python

```
#!pip install psycopg2-binary
#!pip install python-dotenv

import pandas as pd
import numpy as np
import sys
import psycopg2
from dotenv import load_dotenv
import os

load_dotenv()  # load the variables from .env file

password = os.getenv('DB_PASSWORD')

# Connection parameters, yours will be different
param_dic = {
    "host"      : "localhost",
    "database"  : "postgres",
    "user"      : "postgres",
    "password"  : password
}
def connect(params_dic):
    """ Connect to the PostgreSQL database server """
    conn = None
    try:
        # connect to the PostgreSQL server
        print('Connecting to the PostgreSQL database...')
        conn = psycopg2.connect(**params_dic)
    except (Exception, psycopg2.DatabaseError) as error:
        print(error)
        sys.exit(1) 
    print("Connection successful")
    return conn

def postgresql_to_dataframe(conn, select_query, column_names):
    """
    Tranform a SELECT query into a pandas dataframe
    """
    cursor = conn.cursor()
    try:
        cursor.execute(select_query)
    except (Exception, psycopg2.DatabaseError) as error:
        print("Error: %s" % error)
        cursor.close()
        return 1
    
    # Naturally we get a list of tupples
    tupples = cursor.fetchall()
    cursor.close()
    
    # We just need to turn it into a pandas dataframe
    df = pd.DataFrame(tupples, columns=column_names)
    return df

    # Connect to the database
    onn = connect(param_dic)
    cur = conn.cursor()
```

To list all your tables inside your database:

```
cur.execute("SELECT table_name FROM information_schema.tables WHERE table_schema = 'public' ORDER BY table_name;")
rows = cur.fetchall()

for row in rows:
    print(row[0])
```

You can read more about this on [How to Execute SQL Queries in Python and R Tutorial](https://www.datacamp.com/tutorial/tutorial-how-to-execute-sql-queries-in-r-and-python).

## TODO

1. Review Data Schema - Are there any fields that were not captured?
2. Perform EDA on your webscraped data, repeat steps in phase 1
3. Transform webscraped data to data schema
4. Submit [Meeting Feedback form](https://docs.google.com/forms/d/e/1FAIpQLSeqIDZzhh5mC1VLh9GpZIyC1YO30XlnoLPgzT8YatSQrTlx4w/viewform?usp=sf_link)
