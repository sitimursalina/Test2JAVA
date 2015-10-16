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
		
		  //tries to connect to DNS to get IP Address and hostname
          IP = InetAddress.getLocalHost();
          System.out.println("show IP Address:  " + IP.getHostAddress());
          
          NetworkInterface network = NetworkInterface.getByInetAddress(IP);
          
          //MAC Address
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

