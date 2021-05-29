package database; 
import java.sql.*;
public class JdbcAccess {
 
    public static void main(String[] args) {
         
        String databaseURL = "jdbc:ucanaccess://e://User//VANISHREESB//eclipse-workspace//databse//Employee.accdb";
         
        try  {
             
            Class.forName(net.ucanaccess.jdbc.UcanaccessDriver");
            Connection con = DriverManager.getConnection(databaseURL);
            String sql = "INSERT INTO Employees (E_id, E_Name, E_Addr) VALUES (?, ?, ?)";
             
            PreparedStatement preparedStatement = con.preparedStatement(sql);
            preparedStatement.setString(1, "100");
            preparedStatement.setString(2, "Pragati");
            preparedStatement.setString(3, "Hubbali");
             
            int row = preparedStatement.executeUpdate();
             
            if (row > 0) {
                System.out.println("Inserted successfully.");
            }
             
            sql = "select * from Employees";
             
            Statement st = con.createStatement();
            ResultSet rs = st.executeQuery(sql);
             
            while (rs.next()) {
                int no = rs.getInt("Employee_No");
                String eid = rs.getString("E_id");
                String ename = rs.getString("E_Name");
                String eaddr = rs.getString("E_Addr");
                 
                System.out.println(no + ", " + eid + ", " + ename + ", " + eaddr);
            }
             
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
