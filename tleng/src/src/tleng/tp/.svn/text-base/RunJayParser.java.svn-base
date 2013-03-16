package tleng.tp;

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import tleng.tp.grammar.JayParser;
import tleng.tp.grammar.ParseException;

public class RunJayParser {

	public static final String[] filesOK = { "ejemploOK1.jay", "ejemploOK2.jay","ejemploOK3.jay",};
	public static final String[] filesFail = { "ejemploFAIL1.jay", "ejemploFAIL2.jay","ejemploFAIL3.jay",  "ejemploFAIL4.jay"};
	public static final String PATH = "src/tleng/tp/examples/";

	/**
	 * @param args
	 * @throws IOException 
	 * 
	 */
	public static void main(String[] args) throws IOException {

		try {

			for (String example : filesOK) {
				parseExample(PATH + example);
			}

			for (String example : filesFail) {
				try {
					parseExample(PATH + example);
					throw new RuntimeException("File didnt fail");
				} catch (ParseException e) {
					System.out.println(example + " is not correctly formatted");
				}
			}

		} catch (ParseException e) {
			System.out.println("Error");
			System.out.println(e.getMessage());

		}
	}

	private static void parseExample(String file) throws ParseException,
			IOException {
		System.out.println("Reading file: " + file);

		FileInputStream is = new FileInputStream(file);

		JayParser parser = new JayParser(is);
		String html_code = parser.Program();
		byte[] byteArray = html_code.getBytes("UTF-8");
				
		FileOutputStream os = new FileOutputStream(file + ".html");
		os.write(byteArray);
		os.close();
		
	}

}
