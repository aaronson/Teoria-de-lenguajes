package tleng.tp.samples;

import java.io.ByteArrayInputStream;
import java.io.InputStream;

import tleng.tp.samples.adder.grammar.AdderParser;
import tleng.tp.samples.adder.grammar.ParseException;


public class RunAdder {

	/**
	 * @param args
	 * 
	 */
	public static void main(String[] args) {
		
		try {
			
			test1();
			test2();
			test3();

		} catch (ParseException e) {
			System.out.println("Error");
			System.out.println(e.getMessage());

		}
	}

	private static void test1() throws ParseException {
		System.out.println("test1");
		
		byte[] bytes = new byte[] { '1' , '+' , ' ' , '2'};
		
		InputStream is = new ByteArrayInputStream(bytes);

		AdderParser parser = new AdderParser(is);
		System.out.println(parser.Start());
		System.out.println();
		
	}
	
	private static void test2() throws ParseException {
		System.out.println("test2");
		
		String texto = "1+2\r\n+3+4\n+25+6";
		InputStream is = new ByteArrayInputStream(texto.getBytes());
		
		AdderParser parser = new AdderParser(is);
		System.out.println(parser.Start());
		System.out.println();
		
	}

	private static void test3() throws ParseException {
		System.out.println("test3");
		
		String texto = "1++6";
		InputStream is = new ByteArrayInputStream(texto.getBytes());
		
		AdderParser parser = new AdderParser(is);
		System.out.println(parser.Start());
		System.out.println();
		
	}

}
