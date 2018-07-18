# DBCrud-C#

Re-usable C# Class for performing CRUD database operations similiar to the one for [java](https://github.com/msteve/DBCrud)

for example for select name,id from assets where name='room' and  registration_date=CAST(getdate() as date) , you can use

String table="assets";
string[] cols={"name","id"};
 Dictionary<string, string> where=new  Dictionary<string, string>(){
     {"name","room"},
     {DBAcess.SQL_KEYWORD, "registration_date=CAST(getdate() as date)"}
 };
 List<Dictionary<string, string>> resultList = new DBAcess().select(table,cols,where);


 For Insert
 e.g 
 Insert into assets (name,amount,depression) values("Car","50000","10")

Dictionary<string, string> data=new  Dictionary<string, string>(){
     {"name","car"},
     {"amount","50000"},
     {"depression","10"}
 };
string returned_column="_ID";
 string insertId=new DBAcess().insert(table,data,returned_column);
 

