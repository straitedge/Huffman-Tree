import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

////////////////////////////////////////////////////////////////
class HuffmanApp
{
	public static void main(String[] args) throws IOException
	{
		Huffman Huffman = null;
		int value;
		String str;

		while(true)
		{
			System.out.print("Enter first letter of ");
			System.out.print("enter, show, code, or decode: ");
			int choice = getChar();
			switch(choice)
			{
			case 'e':
				System.out.println(
						"Enter text lines, terminate with $");
				str = getText();
				Huffman = new Huffman(str);
				break;
			case 's':
				Huffman.displayTree();
				break;
			case 'c':
				Huffman.encode();
				break;
			case 'd':
				Huffman.decode();
				break;
			default:
				System.out.print("Invalid entry\n");
			}  // end switch
		}  // end while
	}  // end main()
	// -------------------------------------------------------------
	public static String getString() throws IOException
	{
		InputStreamReader isr = new InputStreamReader(System.in);
		BufferedReader br = new BufferedReader(isr);
		String s = br.readLine();
		return s;
	}
	// -------------------------------------------------------------
	public static String getText() throws IOException
	{
		String outStr="", str = "";
		while(true)
		{
			str = getString();
			if( str.equals("$") )
				return outStr;
			outStr = outStr + str + "\n";
		}
	}  // end getText()
	// -------------------------------------------------------------
	public static char getChar() throws IOException
	{
		String s = getString();
		return s.charAt(0);
	}
	//-------------------------------------------------------------
	public static int getInt() throws IOException
	{
		String s = getString();
		return Integer.parseInt(s);
	}
	// -------------------------------------------------------------
} 
