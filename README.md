#Company A (Mac Address,NIC,Threads)

import java.net.InetAddress;
import java.net.NetworkInterface;
import java.net.SocketException;
import java.net.UnknownHostException;

public class Threads 
{
	
   public static void main(String args[]) throws Throwable  
   {
	   InetAddress IP;
		try {
		
		  
          IP = InetAddress.getLocalHost();
          System.out.println("show IP Address:  " + IP.getHostAddress());
          
          NetworkInterface network = NetworkInterface.getByInetAddress(IP);
        
          byte[] mac = network.getHardwareAddress();
          
          System.out.println("show MAC address : ");
          
          StringBuilder sb = new StringBuilder();
		for (int a = 0; a < mac.length; a++) {
			sb.append(String.format("%02X%s", mac[a], (a < mac.length - 1) ? "-" : ""));		
          }
          
          System.out.println(sb.toString());
				
		} catch (UnknownHostException e) {
			
			e.printStackTrace();
			
		} catch (SocketException e){
				
			e.printStackTrace();
				
		}
		
		new Threads.myfunc();
   }
   void myfunc() throws Throwable
   {
   for (int count = 1, row = 1; row < 20; row++, count++)
	      {
	      for (int t = 0; t < count; t++)
	                System.out.print ("threadDemo" +Thread.currentThread().getName()+" # "+t);
         Thread.sleep(200);
	           //to enter newline
	           System.out.print ('\n');
	         }
   }
}


