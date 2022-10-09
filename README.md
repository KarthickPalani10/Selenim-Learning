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
		driver.quit();\\Close the window
 ----------------------------------------------------------------------------------------------------------------------------------------------           
2, Using the Firefox

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
3,UI Locators and Xpaths...(https://opensource-demo.orangehrmlive.com/web/index.php/auth/login)

What is xpath ?
 
 * Xpath is one of the most flexible and strongest location strategy and can be used for locating an in a web page.
 
● Xpath= Syntax ://tagname[@attribute=’value’]
  Password      ://input[@type='password']
                 

// - It helps you select the current node.
Tagname-  It is name of particular node like input, div, button etc.
@ - Used to Select attribute.
Attribute - Attribute name of the node like class,id,name,text, colour etc.
Value - It represents the value of the attribute.

Types of xpath. Two types of xpath.

● Absolute xpath
   *It is the xpath that start to locate elements from root. It starts with ‘/’
   *Absolute xpath will start from the root node it will have sigle /.
Exmple:   
Xpath - /html/body/div[1]/div[3]/form/div[1]/div[1]/div[1]/div/div[2]/input

● Relative xpath
   *It starts from the middle/anywhere of HTML DOM .It starts with ‘//’. It can search elements anywhere on the webpage.
   *Relative xpath will start from the curret node it will have double //.
Exmple:
Xpath - //input[@data-testid='royal_email']

XPath using Contains....(https://opensource-demo.orangehrmlive.com/web/index.php/auth/login)

-->>Different types of methods for writing the xpath

1,XPath using Contains.
 
->Contains() is a very useful method in XPath.
->It can be used for all the dynamic elements.
Syntax : Must Know
          /tagname[contains(@attribute,constantvalue)]
Username: //input[contains(@name,'username')]

2,XPath using Logical Operators: OR & AND...(https://opensource-demo.orangehrmlive.com/web/index.php/auth/login)
   
 *We can write logical operators OR & AND on the attributes in xpath. In the case of OR, any one of the conditions should
  be true or both, whereas, in the case of AND, both the conditions should be true.
  
  Using OR
  
    XPath=//tagname[@attribute1=value1 OR @attribute2=value1]
User id : //input[@name="username" or contains(@placeholder,'abc')]

  Using AND
  
    XPath=//tagname[@attribute1=value1 AND @attribute2=value1]/
User id ://input[@name="username" and contains(@placeholder,'name')]

Example of using OR & AND
  *Find input text box of Business Email on the below mentioned page..
  
3,XPath using Text()...(https://opensource-demo.orangehrmlive.com/web/index.php/auth/login)

  It is similar to Contains() method.
  It is very useful where elements values changes dynamically.
  In Starts-With, the initial value of the attribute’s text is used for locating the element.
Syntax :
            //tagname[starts-with(@attribute,value)]
User id :   //input[starts-with(@name,'username')]
---------------------------------------------------------------------------------------------------------------------------------------------- 



  
  
  







  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  





 
 
 
 
 
 
 
 
 
 
 
 
 






	



     
     
     
 
       
    
