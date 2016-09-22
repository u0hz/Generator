# Generator
use the T4 template to auto generate POCO models


 This code is based on the `PetaPoco` project and `SubSonic` T4 templates but has been considerably re-organized and reduced  
 
 -----------------------------------------------------------------------------------------

 This template can read minimal schema information from the following databases:

	* SQL Server
	* SQL Server CE
	* MySQL
	* PostGreSQL
	* Oracle
	* SQLite
	* OleDb for Access

 For connection and provider settings the template will look for the web.config or app.config file of the 
 containing Visual Studio project.  It will not however read DbProvider settings from this file.

 In order to work, the appropriate driver must be registered in the system machine.config file.  If you're
 using Visual Studio 2010 the file you want is here:

	C:\Windows\Microsoft.NET\Framework\v4.0.30319\Config\machine.config

 After making changes to machine.config you will also need to restart Visual Studio.

 Here's a typical set of entries that might help if you're stuck:

	<system.data>
		<DbProviderFactories>
			<add name="Odbc Data Provider" invariant="System.Data.Odbc" description=".Net Framework Data Provider for Odbc" type="System.Data.Odbc.OdbcFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
			<add name="OleDb Data Provider" invariant="System.Data.OleDb" description=".Net Framework Data Provider for OleDb" type="System.Data.OleDb.OleDbFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
			<add name="OracleClient Data Provider" invariant="System.Data.OracleClient" description=".Net Framework Data Provider for Oracle" type="System.Data.OracleClient.OracleClientFactory, System.Data.OracleClient, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
			<add name="SqlClient Data Provider" invariant="System.Data.SqlClient" description=".Net Framework Data Provider for SqlServer" type="System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
			<add name="MySQL Data Provider" invariant="MySql.Data.MySqlClient" description=".Net Framework Data Provider for MySQL" type="MySql.Data.MySqlClient.MySqlClientFactory, MySql.Data, Version=6.3.4.0, Culture=neutral, PublicKeyToken=c5687fc88969c44d"/>
			<add name="Microsoft SQL Server Compact Data Provider" invariant="System.Data.SqlServerCe.3.5" description=".NET Framework Data Provider for Microsoft SQL Server Compact" type="System.Data.SqlServerCe.SqlCeProviderFactory, System.Data.SqlServerCe, Version=3.5.1.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91"/><add name="Microsoft SQL Server Compact Data Provider 4.0" invariant="System.Data.SqlServerCe.4.0" description=".NET Framework Data Provider for Microsoft SQL Server Compact" type="System.Data.SqlServerCe.SqlCeProviderFactory, System.Data.SqlServerCe, Version=4.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91"/>
			<add name="Npgsql Data Provider" invariant="Npgsql" support="FF" description=".Net Framework Data Provider for Postgresql Server" type="Npgsql.NpgsqlFactory, Npgsql, Version=2.0.11.91, Culture=neutral, PublicKeyToken=5d8b90d52f46fda7" />
			<add name="SQLite Data Provider" invariant="System.Data.SQLite" description=".NET Framework Data Provider for SQLite" type="System.Data.SQLite.SQLiteFactory, System.Data.SQLite, Version=1.0.99.0, Culture=neutral, PublicKeyToken=db937bc2d44ff139"/>
		</DbProviderFactories>
	</system.data>

 Also, the providers and their dependencies need to be installed to GAC.  

 Eg; this is how I installed the drivers for PostgreSQL

	 gacutil /i Npgsql.dll
	 gacutil /i Mono.Security.dll

 -----------------------------------------------------------------------------------------
 
 SubSonic - http://subsonicproject.com
 
 The contents of this file are subject to the New BSD
 License (the "License"); you may not use this file
 except in compliance with the License. You may obtain a copy of
 the License at http://www.opensource.org/licenses/bsd-license.php
 
 Software distributed under the License is distributed on an 
 "AS IS" basis, WITHOUT WARRANTY OF ANY KIND, either express or
 implied. See the License for the specific language governing
 rights and limitations under the License.



refs:

> http://subsonicproject.com    
> https://github.com/CollaboratingPlatypus/PetaPoco    
> https://github.com/ServiceStack/ServiceStack.OrmLite    
