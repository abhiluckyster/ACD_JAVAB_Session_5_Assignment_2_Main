# ACD_JAVAB_Session_5_Assignment_2_Main
package com.inheritance;
public class Building {
	public Building(){
		System.out.println("WELCOME TO ABHINAV'S BUILDING !!");
	}
	public int calprice(int len, int brd, String cat)
	{
		int area=len*brd;
		if (cat.equalsIgnoreCase("Hotel"))
		return(area*100);
		else if (cat.equalsIgnoreCase("Apartments"))
			return(area*11237);
			else
				return(0);
	}
}

package com.inheritance;
public class Hotels extends Building{
	public Hotels() {
		System.out.println("This is Abhinav's Hotel");
		System.out.println("It is a preferred destination to share cherished moments with loved ones.");
		System.out.println("It is a 5 star hotel, mountain view with super deluxe rooms");
	}
}

package com.inheritance;
public class Flats extends Building{
	
	public Flats() {
		System.out.println("This is Abhinav's flats");
	}
	public void flatDetails(int choice)
	{
		if (choice==1)
		{
			System.out.println("One bedroom, One hall, One Kitchen and One Balcony");
		}
		else if (choice==2)
		{
			System.out.println("Two bedroom, One hall, One Kitchen and Two Balcony");
		}
		else
		{
			System.out.println("Three bedroom, One hall, One Kitchen and Three balcony");
		}
	}
}

package com.inheritance;
public class Apartments extends Flats{
	public Apartments() {
		System.out.println("This is Abhinav's Apartments");
		System.out.println("We have 1,2 and 3 Bhk flats");
	}
	public Apartments(int flat) {
		if (flat==1)
		{
		super.flatDetails(1);
		}
		else if (flat==2)
		{
		super.flatDetails(2);
		}
		else if (flat==3)
		{
		super.flatDetails(3);
		}
		else
		{
			System.out.println("Wrong Input");
		}
	}		
}



package com.inheritance;
import java.util.Scanner;
public class ClassMain {
	public static void main(String[] args) {
	Scanner type = new Scanner(System.in);
	char choice;
	do{
	System.out.println("Enter what building info you need - Apartment, Hotel or Hospital");
	String input = type.next();
		if (input.equalsIgnoreCase("Hotel"))
			{
				Hotels hotel = new Hotels();
				System.out.println("Do you want to know the size of rooms. If yes press Y");
				String inputH = type.next();
				if(inputH.equalsIgnoreCase("Y"))
				{
					int roomPrice=hotel.calprice(10, 20,"Hotel");
					System.out.println("Size of room is 10 by 20 feets and rent is "+roomPrice);
					System.out.println("Thank You");
				}
				
			}
		else if (input.equalsIgnoreCase("Hospital"))
			{
			Hospital Ht = new Hospital();
			int HP=Ht.calprice(1,2,"Hospitals");
			System.out.println("Price of hospital room is  "+HP);
			}
		else if (input.equalsIgnoreCase("Apartment"))
			{
				System.out.println("Which flat info you need. Enter 1 or 2 or 3");
				int flat =type.nextInt();
				Apartments a2 = new Apartments(flat);
				int aptPrice=a2.calprice(40, 21,"Apartments");
				System.out.println("Size of apt is 840 and price is "+aptPrice);
				System.out.println("Thank You");
			}
			else
				{
				System.out.println("Wrong Input");
				}
				
				System.out.println("Enter Y  to continue");
				choice = type.next(".").charAt(0);
	}
	while(Character.toLowerCase(choice) == 'y');
		type.close();
	
	}
			
}
