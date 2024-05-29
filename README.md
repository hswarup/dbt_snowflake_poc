# dbt_snowflake_poc

## Step 1 : Create  a virtual environment
python3 -m venv dbt_Snowflake_venv
source dbt_Snowflake_venv/bin/activate

## Step 2 : Install dbt-snowflake adapter
pip3 install dbt-snowflake

## Step 3 : Run 'dbt init' to setup the dbt project 
(dbt_Snowflake_venv) Soujis-MacBook-Air:dbt_snowflake_proj souji$ dbt init
20:32:02  Running with dbt=1.8.1
Enter a name for your project (letters, digits, underscore): dbt_snowflake_poc
Your new dbt project "dbt_snowflake_poc" was created!

Happy modeling!

20:32:12  Setting up your profile.
Which database would you like to use?
[1] snowflake

(Don't see the one you want? https://docs.getdbt.com/docs/available-adapters)

Enter a number: 1
account (https://<this_value>.snowflakecomputing.com): lcbjqux-uo25651 
user (dev username): HSWARUP
[1] password
[2] keypair
[3] sso
Desired authentication type option (enter a number): 1
password (dev password): 
role (dev role): 
role (dev role): ACCOUNTADMIN
warehouse (warehouse name): COMPUTE_WH
database (default database that dbt will build objects in): ANALYTICS
schema (default schema that dbt will build objects in): DBT_HSWARUP
threads (1 or more) [1]: 2
20:34:49  Profile dbt_snowflake_poc written to /Users/souji/.dbt/profiles.yml using target's profile_template.yml and your supplied values. 

### For production workloads , You can also use Keypair for authentication(instead of password) using the steps mentioned here - https://community.snowflake.com/s/article/How-to-configure-Snowflake-key-pair-authentication-fields-in-dbt-connection

## Step 4 : Run 'dbt debug' to validate the connection.
cd dbt_snowflake_poc/
dbt debug

## Step 5 : Create the models and run 'dbt run'
