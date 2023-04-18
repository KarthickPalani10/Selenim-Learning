# Selenium-Learning.

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
 3,Finding the web elements & Intracting with them.
 
 public class FindingTheElement {

    public static void main(String[] args) throws InterruptedException {

        System.setProperty("webdriver.gecko.driver", "C:\\application\\geckodriver-v0.31.0-win64\\geckodriver.exe");
        WebDriver driver = new FirefoxDriver();
        driver.get("https://www.google.com/search");
        //Enter a serch team
        //Click the wikpedia link
        driver.findElement(By.name("q")).sendKeys("wikpedia" + Keys.ENTER);
        Thread.sleep(4000);
        driver.quit();
    }
 ----------------------------------------------------------------------------------------------------------------------------------------------
  4, How to work with likes in selenim (hyperLikes)
 
 public class LinkExample {
//Play with hyperlikes
    public static void main (String[]args){
        System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.leafground.com/link.xhtml");
        //we have linkText and partialLinkText
       // driver.findElement(linkText("Go to Dashboard")).click();
        driver.findElement(partialLinkText("Go to")).click();
    }
}
 ----------------------------------------------------------------------------------------------------------------------------------------------
 5, Working with text Box (Work with edit Fields)
 
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class EditExample {
    //Working with edit field
    public static void main(String[] args) throws InterruptedException{
            //open the browser and where is the path copy and past.
            System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
            //We can create the object
            WebDriver driver = new ChromeDriver();
            //We can use the get method where is the link u can interact with them
            driver.get("https://www.leafground.com/input.xhtml");
            Thread.sleep(2000);
            //Write the box Type your name
            WebElement name = driver.findElement(By.id("j_idt88:name"));
            name.sendKeys("karthick");
            Thread.sleep(2000);
            //add your text Append Country to this City. Must know the concept append meaning only write which we added.not overwrite
            WebElement append = driver.findElement(By.id("j_idt88:j_idt91"));
            append.sendKeys(" India");
            Thread.sleep(2000);
            //Type email and Tab. Confirm control moved to next element. we can do this Enter the email id + tab swich the next field.
            WebElement eMailId = driver.findElement(By.id("j_idt88:j_idt99"));
            eMailId.sendKeys("ntt@gmail.com" + Keys.TAB);
            Thread.sleep(2000);
            //Type about yourself. Just type some thing about the field
            WebElement yourself= driver.findElement(By.id("j_idt88:j_idt101"));
            yourself.sendKeys("I am karthick. I'm from chennai");
            Thread.sleep(2000);
            //Retrieve the typed text. whatever is Write the filed Just print the value
            WebElement getAttribute = driver.findElement(By.name("j_idt88:j_idt97"));
            String value = getAttribute.getAttribute("value");
            System.out.println(value);
            Thread.sleep(2000);
            //Clear the typed text. Just Clear the field.
            WebElement clearBox = driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt95\"]"));
            clearBox.clear();
            Thread.sleep(2000);
            //Verify if text box is disabled. isEnabled method is boolean type. True or false only print
            WebElement disbleBox = driver.findElement(By.xpath("//*[@id=\"j_idt88\"]/div[3]/div"));
            boolean enabled = disbleBox.isEnabled();
            System.out.println(enabled);
            Thread.sleep(2000);
            //Just Press Enter and confirm error message. Just enter the key is used check the filed.
            WebElement enter = driver.findElement(By.id("j_idt106:thisform:age"));
            enter.sendKeys(Keys.ENTER);
            Thread.sleep(2000);
            //Click and Confirm Label Position Changes.Just click the key is used check the filed.
            WebElement click = driver.findElement(By.id("j_idt106:float-input"));
            click.click();
            driver.quit();
        }}
----------------------------------------------------------------------------------------------------------------------------------------------
6,Working with Button (Bound with button)

import org.openqa.selenium.By;
import org.openqa.selenium.Point;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
public class ButtonExample {
        //Working with Button field
        public static void main(String[] args){
            //open the browser and where is the path copy and past.
            System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
            //We can create the object
            WebDriver driver = new ChromeDriver();
            //We can use the get method where is the link u can interact with them
            driver.get("https://www.leafground.com/button.xhtml");
            //1, Get the xy position Use the Point method This Must known(Find the position of the Submit button)
            WebElement getPosition  = driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt94\"]/span[2]"));
            Point xypoint = getPosition.getLocation();
            int xValue = xypoint.getX();
            int yValue =xypoint.getY();
            System.out.println("This is x value "+xValue+" This is y value "+yValue);
            //2, Find the color(Find the Save button color)
            WebElement colorButton = driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt96\"]/span[2]"));
            String color = colorButton.getCssValue("backGrount-color");
            System.out.println("Botton color is :"+color);
            //3,Find the size.(Find the height and width of this button)GetSize method and getheight and getwidth method
            WebElement sizeButton =driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt98\"]/span[2]"));
            int height= sizeButton.getSize().getHeight();
            int width = sizeButton.getSize().getWidth();
            System.out.println("Height is  :"+height+" Width is "+width);
            //4,Go to the home.(Click and Confirm title.)Click is method
            WebElement homeButton = driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt90\"]/span"));
            homeButton.click();
        }}
----------------------------------------------------------------------------------------------------------------------------------------------
7,Worning with Drop downs/Sectable components

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import java.util.List;

public class DropDownExample  {
    public static void main(String[] args)throws InterruptedException{
        //open the browser and where is the path copy and past.
        System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
        //We can create the object
        WebDriver driver = new ChromeDriver();
        //We can use the get method where is the link u can interact with them
        driver.get("https://www.leafground.com/select.xhtml");
        //Which is your favorite UI Automation tool? interact with dropdowns. Must imp we can use method Select oje create pannanum
        WebElement dropDown1 = driver.findElement(By.xpath("//*[@id=\"j_idt87\"]/div/div[1]/div[1]/div/div/select"));
        Select select = new Select(dropDown1);
        select.selectByIndex(1);
        Thread.sleep(3000);
        select.selectByVisibleText("Playwright");
        Thread.sleep(3000);
        //  use list interface <> Using Generics
        List <WebElement> listOfOption = select.getOptions();
        int Size = listOfOption.size();
        System.out.println("Number of element : "+Size);
        // We can use sendkey as well
        dropDown1.sendKeys("Cypress");
        //Choose the Course. We can perform multiselect.we can use the select obj create pannanum method create pannaum
        WebElement multiSelect = driver.findElement(By.xpath("//*[@id=\"j_idt87:auto-complete\"]/ul"));
        Select multiSelectionBox = new Select(multiSelect);
        multiSelectionBox.selectByIndex(2);
        multiSelectionBox.selectByIndex(5);
        multiSelectionBox.selectByIndex(7);
    }}
----------------------------------------------------------------------------------------------------------------------------------------------
8,Working with Alerts/type of alerts/
	
import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class AlertsExample {
    public static void main (String [] args){
        //open the browser and where is the path copy and past.
        System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
        //We can create the object
        WebDriver driver = new ChromeDriver();
        //We can use the get method where is the link u can interact with them
        driver.get("https://www.leafground.com/alert.xhtml;jsessionid");
        //Click the button to display. Alert (Simple Dialog)
        WebElement alertBox = driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt91\"]/span[2]"));
        alertBox.click();
        Alert alert = driver.switchTo().alert();
        alert.accept();
        //Click the button to display confirm box.Alert (Confirm Dialog)
        WebElement confirmBox = driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt93\"]/span[2]"));
        confirmBox.click();
        Alert confirmAlert = driver.switchTo().alert();
        confirmAlert.dismiss();
        //Alert (Prompt Dialog
        WebElement promptBox = driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt104\"]/span[2]"));
        promptBox.click();
        Alert promptAleat = driver.switchTo().alert();
        promptAleat.sendKeys("karthick");
        promptAleat.accept();
    }}	
----------------------------------------------------------------------------------------------------------------------------------------------
9, working with Radio Button
	
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class RadioButtonExample {
    public static void main(String[] args) {
        //open the browser and where is the path copy and past.
        System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
        //We can create the object
        WebDriver driver = new ChromeDriver();
        //We can use the get method where is the link u can interact with them
        driver.get("https://www.leafground.com/radio.xhtml");
        //Select the age group (only if not selected) we can use
        WebElement below20 = driver.findElement(By.xpath("//*[@id=\"j_idt87:age\"]/div/div[1]/label"));
        below20.click();
        WebElement favorite = driver.findElement(By.xpath("//*[@id=\"j_idt87:console1\"]/tbody/tr/td[1]/label"));
        favorite.click();
        //UnSelectable
        WebElement UnSelectable = driver.findElement(
                By.xpath("//*[@id=\"j_idt87:city2\"]/div/div[1]/div/div[2]"));
        //Find the default select radio button
        WebElement selected = driver.findElement(
                By.xpath("//*[@id=\"j_idt87:console2\"]/tbody/tr/td[2]/div/div[2]/span"));
        boolean clickOrnot1 = UnSelectable.isSelected();
        boolean clickOrnot2 = selected.isSelected();
        System.out.println("This not UnSelectable :"+clickOrnot1);
        System.out.println("This default  selected :"+clickOrnot2);
    }}
----------------------------------------------------------------------------------------------------------------------------------------------
10, Working with Check Boxes (interact with Checkbox)

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class CheckBoxExample {

    public static void main(String[] args) throws InterruptedException{
        //open the browser and where is the path copy and past.
        System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
        //We can create the object
        WebDriver driver = new ChromeDriver();
        //We can use the get method where is the link u can interact with them
        driver.get("https://www.leafground.com/checkbox.xhtml");
        //Verify if check box is disabled
        WebElement disabled = driver.findElement(
                By.xpath("//*[@id=\"j_idt87:j_idt102\"]"));
        boolean selected = disabled.isEnabled();
        System.out.println("This is disabled :"+selected);
        //Basic Checkbox
        WebElement Checkbox = driver.findElement(
                By.xpath("//*[@id=\"j_idt87:j_idt89\"]/div[2]"));
        Checkbox.click();
        Thread.sleep(3000);
        //Tri State Checkbox
        WebElement click = driver.findElement(
                By.xpath("//*[@id=\"j_idt87:ajaxTriState\"]/div[2]"));
        click.click();
    }}
	
----------------------------------------------------------------------------------------------------------------------------------------------
11,Advance concepts-Widows Handling(https://www.leafground.com/frame.xhtml)

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.devtools.v85.dom.model.PseudoType;

import java.util.Set;

public class WindowExample {
    public static void main(String[] args) {
        //open the browser and where is the path copy and past.
        System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
        //We can create the object
        WebDriver driver = new ChromeDriver();
        //We can use the get method where is the link u can interact with them
        driver.get("https://www.leafground.com/window.xhtml");
        driver.manage().window().maximize();
        String oldWindow= driver.getWindowHandle();
        //Click and Confirm new Window Opens
        WebElement firstButton = driver.findElement(By.xpath("//*[@id=\"j_idt88:new\"]/span"));
        firstButton.click();
        Set<String> handles =driver.getWindowHandles();
        for(String newwindow : handles){
            driver.switchTo().window(newwindow);
        }
        WebElement click =  driver.findElement(By.xpath("//*[@id=\"j_idt107\"]/div[2]"));
        click.click();
        driver.close();
        driver.switchTo().window(oldWindow);//we can use the window(oldwindow) your hands can switch to parent win
        //Open multiple window
        WebElement openMultipleWindow = driver.findElement(
                By.xpath("//*[@id=\"j_idt88:j_idt91\"]/span"));
        openMultipleWindow.click();
        //Find the number of opened tabs
        int numberOfWindowsOpen = driver.getWindowHandles().size();
        System.out.println("No of windows is "+numberOfWindowsOpen);
        //Close all windows except Primary
        WebElement dontCloseMe = driver.findElement(
                By.xpath("//*[@id=\"j_idt88:j_idt93\"]/span[2]"));
        dontCloseMe.click();
        //set save the new windows 
        Set<String> newWindowHandles = driver.getWindowHandles();
        for (String  allwindows : newWindowHandles) {
            if (!allwindows.equals(oldWindow)) {
                driver.switchTo().window(allwindows);
                driver.close();
            }
        }
    }
}
----------------------------------------------------------------------------------------------------------------------------------------------
12,Adnance concepts Handling the frames
	
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import java.util.List;
public class FramesExample {
    public static void main(String[] args) {
        //open the browser and where is the path copy and past.
        System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
        //We can create the object
        WebDriver driver = new ChromeDriver();
        //We can use the get method where is the link u can interact with them
        driver.get("https://www.leafground.com/frame.xhtml");
        driver.manage().window().maximize();
        driver.switchTo().frame(0);
        //Click Me (Inside frame)
        WebElement button1 = driver.findElement(By.xpath("//*[@id=\"Click\"]"));
        button1.click();
        String text = driver.findElement(By.id("Click")).getText();
        System.out.println(text);
        //How many frames in this page? Must use the List and driver.switchTo().defaultContent();
        driver.switchTo().defaultContent();
        List<WebElement>totalFrames= driver.findElements(By.tagName("iframe"));
        int size = totalFrames.size();
        System.out.println(size);
    }}
----------------------------------------------------------------------------------------------------------------------------------------------
13,advanced Concepts Drag and drop(https://www.leafground.com/drag.xhtml)
	
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

public class DragAndDropExample {
    public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver","C:\\application\\chromedriver_win32\\chromedriver.exe");
        WebDriver driver = new ChromeDriver();
        driver.navigate().to("https://www.leafground.com/drag.xhtml");
        driver.manage().window().maximize();
        WebElement from = driver.findElement(By.xpath("//*[@id=\"form:drag_content\"]/p"));
        WebElement to =driver.findElement(By.xpath("//*[@id=\"form:drop_content\"]/p"));
        //you can perform with drag and drop we must create action ojc
        Actions actions = new Actions(driver);
        //actions.clickAndHold(from).moveToElement(to).release(to).build().perform();
        actions.dragAndDrop(from,to).build().perform();
	}}
----------------------------------------------------------------------------------------------------------------------------------------------
14,How to take tool tips text()
	
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;

public class ToolTipExample {
    public static void main(String[] args) {
    //open the browser and where is the path copy and past.
        System.setProperty("webdriver.chrome.driver", "C:\\application\\chromedriver_win32\\chromedriver.exe");
    //We can create the object
    WebDriver driver = new ChromeDriver();
    //We can use the get method where is the link u can interact with them
    driver.get("https://www.leafground.com/input.xhtml");
    WebElement name =  driver.findElement(By.xpath("//*[@id=\"j_idt88:j_idt95\"]"));
    String toolTip =  name.getAttribute("title");
        System.out.println(toolTip);
	
----------------------------------------------------------------------------------------------------------------------------------------------
1,UI Locators and Xpaths...(https://opensource-demo.orangehrmlive.com/web/index.php/auth/login)

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
Identification strategies:(https://opensource-demo.orangehrmlive.com/web/index.php/auth/login)Practice page

Locating the elements with know Attributes.

1,Locating elements with know Attributes.
  Syntax:
         //*[@attributeName='value']
user id://*[@name='username']
 
2,Locating the elements with Know Element and Attributes. 
  Syntax:
        //elementsName[@attributes='value']
user id://input[@name='username']

3,locating elements with known Visible text  (exact match).(OrangeHRM, Inc.)
 * Used for locating elements containing exact text within an element.(etha oru text atha vera web page pogum athu la etha mathiri x path find pannalam)
  Syntax:
     //element[text()='exact text'] and //*[text()='exact text']
     //a[text()='OrangeHRM, Inc']   and //*[text()='OrangeHRM, Inc']
     
4,locating elements whwn the part of the visible text is known (partial match).(OrangeHRM, Inc.)
  Syntax:
    //elementsName[contains(text(),'part of the text')] and //*[contains(text(),'part of the text')]
    //a[contains(text(),'OrangeHRM')]                   and //*[contains(text(),'OrangeHRM')]
    
5,locating element with Multiple atrributs.(exmple intract with login button)(etha at)
  Syntax:
     //*[@attribute][@attribute 1]...we can use multiple attributes
     //*[@type='submit'][@class='oxd-button oxd-button--medium oxd-button--main orangehrm-login-button'] 
     
6,locating elements when starts-with(text(),'starting text')...(OrangeHRM, Inc.)
  Syntax:
     //element[starts-with(text(),'Starting text')]
     ////a[starts-with(text(),https)]
     
7,Locating Elements with dynamic attribute values..
Ex: karthick 123(atha value marita irukum 
EX: karthick 143
EX: karthick 125

 Syntax:
     //element[starts-with(text(),'Starting text')]
     //elementsName[contains(text(),'part of the text')]
----------------------------------------------------------------------------------------------------------------------------------------------
Locating element relative to know element.(https://opensource-demo.orangehrmlive.com/web/index.php/auth/login)
Imp Notes : 

1.location a parent element
2.location a child element
3.location ancestors of a known element
4.location follwing element
5.location preceding element
6.location follwing sibling
7.location preceding sibling

1,Locating a parent element.
   * The parent axes contains the parent of the context node.
   
   Syntax ://<knowXpath>/parent::elementname
   EX     ://*[@placeholder='Username']/parent::*
   
     
2,locating a child element
   *The child axes contains the children of the context node.
   
   Syntax ://<knowXpath>/child::elementname
   EX     ://*[@placeholder='Username']/child::*
   
3.location ancestors of a known element
Syntax ://<knowXpath>/ancestor::elementname
EX     ://*[@placeholder='Username']/ancestor::form

4.location follwing element
(Just small note we shold use the following element first find out the known element after the follwing every element is called a follwing. you can use the lengh() method and metioned the index also)
Syntax ://<knowXpath>/child::elementname
EX     ://*[@placeholder='Username']/follwing::form

5.location preceding element
(Just small note we shold use the following element first find out the known element before the follwing every element is called a follwing. you can use the lengh() method and metioned the index also)
Syntax ://<knowXpath>/child::elementname
EX     ://*[@placeholder='Username']/preceding::form
6.location follwing sibling
7.location preceding sibling
------------------------------------------------------------------------------------------------------------
Type of locator in selenium
ID,Name,className,TagName,xpath,css selector,linklist,partciallink list,
















     
















     
   




  
  
  







  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  





 
 
 
 
 
 
 
 
 
 
 
 
 






	



     
     
     
 
       
    
