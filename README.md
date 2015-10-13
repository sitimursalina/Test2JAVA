# A-Mac-Address
#Company A-how to get MAC Address


package mac.compA;

import java.net.InetAddress;


    public class macadd{
       
        public static void main(String[] args){
        
        InetAddress IP;
        try {
        
          IP = InetAddress.getLocalHost();
          System.out.println("Company A-IP Address:  " + IP.getHostAddress());
        
        
        
} catch (UnknownHostException e) {
		
		e.printStackTrace();
		
	} catch (SocketException e){
			
		e.printStackTrace();
			
	}

