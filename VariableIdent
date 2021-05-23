import java.util.*;
import java.io.*;
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class varIdent {
	public static void main(String[]args) throws FileNotFoundException, IOException {
		BufferedReader reader = new BufferedReader(new FileReader("testVars.txt"));
		StringBuilder stringBuilder = new StringBuilder();
		String line = null;
		String ls = System.getProperty("line.separator");
		while((line = reader.readLine()) != null) {
			stringBuilder.append(line);
			stringBuilder.append(ls);
		}
		stringBuilder.deleteCharAt(stringBuilder.length() - 1);
		reader.close();
		String content = stringBuilder.toString();
		
		String testStr = "\"String\" 100.0234 100.0234f 1.0e10f 100 String";
		strLitChecker(testStr);
		flPtLitChecker(testStr);
		intLitChecker(testStr);
		varChecker(testStr);
	}
	
	//Method to pass string to analyzer
	public static void strLitChecker(String testString) {
		Pattern pattern = Pattern.compile("\"(.*?)\"");
		Matcher matcher = pattern.matcher(testString);
		Pattern pattern2 = Pattern.compile("[0-9].[0-9]");
		Matcher matcher2 = pattern2.matcher(testString);
		while(matcher.find()) {
			matcher.start();
			matcher.end();
			System.out.println(matcher.group() + " is a string literal");
		}
	}
	
  //Method to match input to floating-point literal
	public static void flPtLitChecker(String testString) {
		//Pattern pattern = Pattern.compile("[+-]?[0-9]+\\.[0-9]+");
		Pattern pattern = Pattern.compile("[-+]?[0-9]+\\.[0-9]+[eE]?[-+]?[0-9]+[f]?");
		Matcher matcher = pattern.matcher(testString);
		while(matcher.find()) {
			matcher.start();
			matcher.end();
			System.out.println(matcher.group() + " is a floating-point literal");
		}
	}
	
  //Method to match input to integer literal
	public static void intLitChecker(String testString) {
		Pattern pattern = Pattern.compile("(?<=\\s|^)\\d+(?=\\s|$)");
		Matcher matcher = pattern.matcher(testString);
		while(matcher.find()) {
			matcher.start();
			matcher.end();
			System.out.println(matcher.group() + " is an integer literal");
		}
	}
	
  //Method to match input to variable name
	public static void varChecker(String testString) {
		Pattern pattern = Pattern.compile("(?<=\"|^)[a-zA-Z_$][a-zA-Z_$0-9]*(?=\"|$)");
		Matcher matcher = pattern.matcher(testString);
		while(matcher.find()) {
			matcher.start();
			matcher.end();
			System.out.println(matcher.group() + " is a variable name");
		}
	}
}
