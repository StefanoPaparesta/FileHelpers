FileHelpers
===========

  http://www.filehelpers.com  - SourceForge Home: http://sf.net/projects/filehelpers

  The FileHelpers are a **free and easy to use** .NET library to read/write data from fixed length or delimited records in files, strings or streams
 
  If you want to start using the library go directly to the Quick Start Guide in the CHM.

Downloads
---------

You can **download** the last stable version from our build server at:

####[Last Stable Build](http://teamcity.codebetter.com/viewLog.html?buildId=lastSuccessful&buildTypeId=FileHelpersStable&tab=artifacts&guest=1)

    Download the zip with the format: FileHelpers_x.x.x_Build.zip


Delimited Example 
-----------------

Source Data
```
    1732,Juan Perez,435.00,11-05-2002 
    554,Pedro Gomez,12342.30,06-02-2004 
    112,Ramiro Politti,0.00,01-02-2000 
    924,Pablo Ramirez,3321.30,24-11-2002 
```
Record Type

```csharp
	[DelimitedRecord(",")]
	public class Customer
	{
		public int CustId;
		
		public string Name;

		public decimal Balance;

		[FieldConverter(ConverterKind.Date, "dd-MM-yyyy")]
		public DateTime AddedDate;
	}
```
Usage

```csharp
  var engine = new FileHelperEngine<Customer>();

  // To Read Use:
  Customer[] res = engine.ReadFile("FileIn.txt");

  // To Write Use:
  engine.WriteFile("FileOut.txt", res);
```

Who needs the File Helpers Library ? 
------------------------------------

  In almost every project there is a need to read/write data from/to a file of a specified format.

  For example for log parsing, data warehouse and OLAP applications, 
  communication between systems, file format transformations 
  (for example from a fixed length to a CSV file).

  This library aims to provide an easy and reliable way to accomplish this task.


License
-------

 The FileHelpers are licensed under the **new BSD or LPGL, pick the best for you**
 
 FileHelpers Library source and binaries are **completely free for commercial and non commercial use**


Contact and Ideas
-----------------

 If you find that there is a feature that I should include, or you have a new idea 
 (for the API, Source Code or Examples), please let me know, by sending an e-mail 
 to marcos (at) filehelpers.com

Sponsors
-----------------

 Our build server is kindly provided by [CodeBetter](http://codebetter.com/) at [FileHelpers Builds](http://teamcity.codebetter.com/project.html?tab=projectOverview&projectId=FileHelpers)

 We have also the awesome .Net tools from [JetBrains](http://www.jetbrains.com/).

 ![YouTrack and TeamCity](http://www.jetbrains.com/img/banners/Codebetter300x250.png)
