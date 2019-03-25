# connectoracle
import java.sql.*;  
class OracleCon{  
public static void main(String args[])
{  
try
{  
Class.forName("oracle.jdbc.driver.OracleDriver");  //step1 load the driver class  

//step2 create  the connection object  
Connection con=DriverManager.getConnection(  
"jdbc:oracle:thin:@localhost:1521:xe","system","oracle");  
 
Statement stmt=con.createStatement();  //step3 create the statement object  
  
ResultSet rs=stmt.executeQuery("select * from emp");  //step4 execute query
while(rs.next())  
System.out.println(rs.getInt(1)+"  "+rs.getString(2)+"  "+rs.getString(3));  
  
con.close();  //step5 close the connection object  
  
}
catch(Exception e){ System.out.println(e);}  
  
}  
}  
