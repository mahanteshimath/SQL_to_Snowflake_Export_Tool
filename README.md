# WowMaker | Free Data Migration & Export Tool for Snowflake



### *This utility is not intended to run on the DB server itself so please install it on a stand-alone machine that has connectivity to all your sources.*

Windows export utility to automatically transfer entire set of tables & data from following database platforms to Snowflake. 

Below are the Supported Sources:

- **Microsoft SQL -  (*Requires Microsot SQL OLEDB 64-bit Driver [here](https://www.microsoft.com/en-us/download/details.aspx?id=56730)***)
- **Oracle   -  (*Requires Oracle OLEDB 64-bit Driver found [here](https://www.oracle.com/database/technologies/odac-downloads.html)***)
- **RedShift -  (*Requires RedShift ODBC Driver found [here](https://docs.aws.amazon.com/redshift/latest/mgmt/configure-odbc-connection.html#install-odbc-driver-windows)***) 
 
- **SAP Hana - (*Requires Hana ODBC Client found [here](https://tools.hana.ondemand.com/#hanatools)***)
- **MySQL** 
- **Postgres  -  (*Requires PostGre ODBC Driver found [here](https://www.postgresql.org/ftp/odbc/versions/msi/)***)
<br><br>
![Image of SQL to Snowflake tool](https://github.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/blob/main/images/SQL_2_Snowflake_Screenshot_H.png.PNG)

<br>
<br>
The tool will create Schema, Tables & optionally transfer data with proper data type mappings and conversions for date & binary formats.





  
# Installation

**App requires Snowflake_ODBC_driver Win64 to be installed on the machine before it can run properly.**

1- Download [**WowInstaller.msi**](https://github.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/raw/main/WowInstaller.msi)

2- Run the **WowInstaller.msi** file (You may have to click **INFO & RUN ANYWAY** if you get DON'T RUN warning due to this app not being signed)
 
 ![Image of SQL to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/images/Capture1_LI.jpg)
 ![Image of SQL to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/images/Capture2.PNG)
 

3- Download & Install [Snowflake Win64 ODBC Driver](https://sfc-repo.snowflakecomputing.com/odbc/win64/latest/index.html)
 
4- Download & Install drivers matching your Source Databases
- [Download Microsot SQL OLEDB 64-bit Driver](https://www.microsoft.com/en-us/download/details.aspx?id=56730)
- [Download Oracle OLEDB 64-bit Driver)](https://www.oracle.com/database/technologies/odac-downloads.html)
- [Download SAP Hana ODBC Driver](https://tools.hana.ondemand.com/#hanatools)
- [Download PostGres ODBC Driver](https://www.postgresql.org/ftp/odbc/versions/msi/) 
- [Download RedShift ODBC 64-bit Driver](https://docs.aws.amazon.com/redshift/latest/mgmt/configure-odbc-connection.html#install-odbc-driver-windows) 
 
 5- Search & Start **Wowmaker Migration to Snowflake** in your Programs Menu (OR Run ""C:\Program Files\Wowmaker\WowMaker SQL_to_Snowflake\WowMaker_SQL_2_Snowflake.exe")
 
  
# Description


This utility will automatically move tables (in full) from a source database (MsSQL or Oracle) to Snowflake. Just select a list of tables from source db and point to an existing Snowflake account & a database with proper user cridentials to start transfering schemas, tables & data.



The tool will do the following for each table:
- Generate a DDL & Create the table in Snowflake.
- Auto map proper datatypes.
- Perform date type conversion
- Login to Snowflake using SSO. Fill in userid in WowMaker & Leave PW blank. Userid has to match the userid used with SSO.
- if **EXPORT DATA** is checked (checked by default)
  - Export the data into a temp folder as flat files broken in to chunks (**10MB - 600MB**).
  - Create an internal stage in the target Snowflake database & Upload the files
  - Copy the uploaded files into the proper table in snowflake.

<br><br>

<strong>This product is a personal project & provided as is without any warranty. 
This application is not associated with Snowflake Inc. & not a supported product. Please use it at your own risk.</strong>

<br>
<br>


# Version History
- **5/11/2022 Added SSO login for Snowflake. Enter only username & leave PW blank in Wowmaker UI**
- **6/23/2021 Added Redshift as a separate Source using RedShift ODBC Drivers**
- **2/9/2021 Added SAP/Hana as Source**

- <strong>3/11/2021 - Removed Clientside 45 secs Timeout</strong>
- **12/20/2020 Added PostGres as Source**
- **12/18/2020 Added Proxy Server option for Snowflake**
- <strong>12/02/2020 - Fixed date formatting issues</strong>

- <strong>11/30/2020 - Updated V9 - Added MySQL Schema & Data Export option (beta)</strong>
 
- <strong>11/23/2020 - Updated V8 - Added ORACLE Schema & Data Export option (beta)</strong>
  - Extraction Performance improvements for larger datasets.
  - Modified RECORD_SEPERATOR to HEX 0x02 to reduce export file size.
- <strong>11/22/2020 - Updated V7 with following changes</strong>
  - Extraction Performance improvements for larger datasets.

- <strong>11/21/2020 - Updated V6 with following changes</strong>
  - Added Windows Authentication support for SQL connection
  - Added max file size option for exporting chucks for large table exports (10, 25, 50, 75 & 100 MB)
  - Added Option to Enable/Disable client side file compression (gzip) prior to uploading to Snowflake
  - Enhanced logic to reduce redundant SQL create schema commands.
  - Fixed an issue with Column names with spaces.
  - Fixed an issue displaying status for tables with 0 records

<BR><BR>



# Export Microsoft SQL
![Image of SQL to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/images/SQL_2_Snowflake_Screenshot_S.png)

<br>
<br>

# Export Oracle

![Image of Oracle to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/images/SQL_2_Snowflake_Screenshot_O.png)

<br>
<br>

# Export MySQL

![Image of Oracle to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/images/SQL_2_Snowflake_Screenshot_MySQL.png)



<br><br>
# Export Postgres

![Image of Oracle to Snowflake tool](https://raw.githubusercontent.com/NickAkincilar/SQL_to_Snowflake_Export_Tool/main/images/SQL_2_Snowflake_Screenshot_P.png)



  
  
