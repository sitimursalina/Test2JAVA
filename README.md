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
        
          IP = InetAddress.getLocalHost();
          System.out.println("Company A-IP Address:  " + IP.getHostAddress());
          
          NetworkInterface networkA = NetworkInterface.getByInetAddress(IP);
          
          byte[] macA = networkA.getHardwareAddress();
        
        
        
} catch (UnknownHostException e) {
		
		e.printStackTrace();
		
	} catch (SocketException e){
			
		e.printStackTrace();
			
	}

