# A-Mac-Address
#Company A-how to get MAC Address


package mac.compA;

import java.net.InetAddress;
import java.net.NetworkInterface;
import java.net.SocketException;
import java.net.UnknownHostException;

    public class macadd{
       
        public static void main(String[] args){
        
        InetAddress IP;
        try {
          
          //tries to connect to DNS to get IP Address and hostname
          IP = InetAddress.getLocalHost();
          System.out.println("Company A-IP Address:  " + IP.getHostAddress());
          
          NetworkInterface networkA = NetworkInterface.getByInetAddress(IP);
          
          //MAC Address
          byte[] macA = networkA.getHardwareAddress();
          
          System.out.println("Company A - MAC address : ");
          
          StringBuilder sbA = new StringBuilder();
		for (int a = 0; a < macA.length; a++) {
			sbA.append(String.format("%02X%s", macA[a], (a < macA.length - 1) ? "-" : ""));		
          }
          
          System.out.println(sbA.toString());
        
} catch (UnknownHostException e) {
		
		e.printStackTrace();
		
	} catch (SocketException e){
			
		e.printStackTrace();
			
	}
  }
 } 
