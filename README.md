# VerifyURL
package web_driver;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class Verifay_url {

	public static void main(String[] args) throws Throwable {
		
		// TODO Auto-generated method stub
		System.setProperty( "webdriver.chrome.driver","E:\\Chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.manage().deleteAllCookies();
		driver.get("http://primusbank.qedgetech.com/");
        
		Thread.sleep(5000);
		String expected = driver.getCurrentUrl();
		String actual ="https://";
		if(expected.startsWith(actual))
		{
			System.out.println("url is secured::"+expected+"     "+actual);
		}
		else
		{
			System.out.println("url is not secured::"+expected+"     "+actual);
		}
		driver.close();
		
	}

}
