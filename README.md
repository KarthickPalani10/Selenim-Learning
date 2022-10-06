# Selenim-Learning.

1,    What is selenim?
      ● Selenium is a very popularly used Web UI(User interface) automation testing suite.
      ● It is an open-source tool.
      ● Jason Huggins originally developed it in 2004 as an internal tool in Thought Works.
      ● It supports automation across different browsers, platforms and programming languages
      ● Selenium software is not just tools but a suite of software. Each piece caters to different
      selenium QA needs. Following are the lists of tools:-
         a. Selenium IDE(Integrated Development environment)
         b. Selenium RC(Remote Control)
         c. Selenium WebDriver(we are must learning imp)
         d. Selenium Grid
    
2,   What is Selenium Webdriver?  
     ● It’s a collection of core java APIs
     ● It is widely used and better than RC and IDE
     ● It supported multiple browser and OS
     ● It supported multiple language like java, c#,python,PHP,perl,Ruby
     ● Unlike RC it does not rely on javascript for selenium automation testing
 ----------------------------------------------------------------------------------------------------------------------------------------------
1,Getting Start with Test Automation.

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class Chrome {
	public static void main(String[] args) {
		System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.get("https://relevel.com/home");
		System.out.println("The Manstor");
		driver.quit();\\Close the 
 ----------------------------------------------------------------------------------------------------------------------------------------------           
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class FirefoxBrowser {
	
	public static void main (String[]args) throws InterruptedException{
		System.setProperty("webdriver.gecko.driver", "C:\\application\\geckodriver-v0.31.0-win64\\geckodriver.exe");
		WebDriver driver = new FirefoxDriver();
		Thread.sleep(5000);
		driver.get("https://relevel.com/home");
		System.out.println(driver.getTitle());
		driver.close();
 ----------------------------------------------------------------------------------------------------------------------------------------------           
			

     
     
     
 
       
    
