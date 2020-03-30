# Skyspark_API_Client
Python API client to query data from Skyspark database and run various data quality checks on time series data. Client is able to connect to your Skyspark implementation, request data using standard Axon notation, and return in a pandas dataframe.
## Getting Started
The user functions can be found in `spyspark.py` and is dependent on both the two *scram* files to perform the scram authentication protocol and the `TS_Util_Clean_Data.py` file to run data quality metrics against the data.

Most functions can be ran using the basic class object and following Axon notation, **however**, some complex functions such as
`run_analysis_from_meta` is specialized for the LBNL Skyspark implementation and may not be generalizable.
### Prerequisites
Code runs with Python 3.6 and above.

The current configuration file needs to be modified to reflect the current address of your Skyspark instance. Update both `address`
and `opsaddress` to the appropriate url. Also, update `user` to your current Skyspark username.


After the client's first attempt to access the database, the following message will appear: 
*Stored or entered username or password invalid* followed by a field to input your username and password for your Skyspark instance. These
credentials will be used to generate a new salted password, salt, and token for your session and will be saved to you config file for later
use.

### Installing
Most imports are standard `pip` installs. Some libraries are not used for normal functionality but are necessary if working with the LBNL Skyspark implementation.
## Running
As previously stated, some of the functions will only work with the LBNL implementation. The rest of the functions can be used to query
the database based on metadata tags or composed Axon queries and return time series data in a pandas dataframe.
## Authors
* **Jacob Rodriguez** - *Skyspark client, documentation, and code cleanup* - [Github](https://github.com/JacobBRodriguez)
* **Marco Pritoni** - *Skyspark client, TS Util functions*
* **Raphael Vitti** - *Skyspark client, scram authentication scripts*
