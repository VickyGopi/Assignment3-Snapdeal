package week4.day1;

import java.util.concurrent.TimeUnit;
import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import io.github.bonigarcia.wdm.WebDriverManager;

public class Assignment3 {

	public static void main(String[] args) {
		WebDriverManager.chromedriver().setup();
		ChromeDriver driver = new ChromeDriver();
				driver.get("https://www.snapdeal.com/");
				driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
				driver.manage().window().maximize();
				Actions Build = new Actions(driver);
				WebElement ele1 = driver.findElement(By.xpath("//li[@class='navlink lnHeight']//span[@class='catText']"));
				WebElement ele2 = driver.findElement(By.xpath("//span[@class='linkTest'and text()='Loafers']"));
				Build.moveToElement(ele1).moveToElement(ele2).click().perform();
				WebElement ele3 = driver.findElement(By.xpath("//img[@class='product-image '][1]"));
				WebElement ele4 = driver.findElement(By.xpath("//div[@class='clearfix row-disc']"));
				Build.moveToElement((WebElement) ele3).moveToElement(ele4).click().perform();
				driver.close();

	}

}
