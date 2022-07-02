package sovtechprac;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

public class testing {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
// Invoke the web driver
		System.setProperty("webdriver.chrome.driver","C:\\Users\\Patricia\\Downloads\\chromedriver_win32\\chromedriver.exe");
		WebDriver driver= new ChromeDriver();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(05));
		driver.get("https://www.sovtech.co.za/contact-us/");
		driver.findElement(By.name("your_name")).sendKeys("Patricia");
		driver.findElement(By.name("email ")).sendKeys("matjipapatricia@gmail.com");
		driver.findElement(By.xpath("/html/body/div/form/fieldset[2]/div[1]/label")).sendKeys("0772622345");
	//Drop down field for company size	
		WebElement ddown = driver.findElement(By.name("numemployees"));
		Select select = new Select(ddown);
		select.selectByValue("5-25");
		Thread.sleep(2000);
	
		select.selectByIndex(2);
		Thread.sleep(2000);
		//Drop down field for what service are you looking for
		
		WebElement ddown1 = driver.findElement(By.xpath("//*[@id=\"what_kind_of_problem_is_your_business_currently_facing_-c2e387f9-4bd8-496f-ab2a-81fbbc31712a\"]"));
		Select select1 = new Select(ddown1);
		select1.selectByValue("Manage & improve existing platforms");
		Thread.sleep(2000);
		
		select1.selectByIndex(3);
		Thread.sleep(2000);
		
	driver.findElement(By.name("message")).sendKeys(" I need to learn more abput your services");
	driver.findElement(By.name("LEGAL_CONSENT")).click();
	driver.findElement(By.className("hs-button")).click();
	driver.close();

	}

}
