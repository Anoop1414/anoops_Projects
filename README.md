# anoops_Projects
package maven_package;



import java.util.Iterator;
import java.util.Set;


import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
//import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.edge.EdgeDriver;
//import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;



public class EndToEndProject1 {

	public static void main(String[] args) throws InterruptedException{
		// TODO Auto-generated method stub



		WebDriver Az; 
		Az = new EdgeDriver();

		Az.manage().window().maximize();

		Az.get("https://Amazon.in//");

		WebElement srch = Az.findElement(By.id("twotabsearchtextbox"));
		srch.click();

		srch.sendKeys("Realme");
		srch.sendKeys(Keys.ENTER);
		Thread.sleep(5000);
		Az.findElement(By.xpath("//a[@class= 'a-link-normal s-navigation-item']/span[text()= 'Android 12.0']")).click();
		Az.findElement(By.xpath("//a[@class= 'a-link-normal s-navigation-item']/span[text()= '256 GB']")).click();
		Az.findElement(By.xpath("//a[@class= 'a-link-normal s-navigation-item']/span[text()= '5G']")).click();
		Az.findElement(By.xpath("//a[@class= 'a-link-normal s-navigation-item']/span[text()= '10 GB & Above']")).click();

		Thread.sleep(4000);
		Az.findElement(By.xpath("//a[@class= 'a-link-normal s-underline-text s-underline-link-text s-link-style a-text-normal']/span[text()= '(Refurbished) OPPO Reno8 Pro 5G (Glazed Black, 256 GB) (12 GB RAM)']")).click();

		Set<String> WinH = Az.getWindowHandles();

		Iterator<String> ItIds= WinH.iterator(); 

		String win1= ItIds.next();
		String win2= ItIds.next();

		Az.switchTo().window(win2);

		Thread.sleep(4000);

		Az.findElement(By.xpath("//input[@id= 'add-to-cart-button']")).click();

		Thread.sleep(4000);
		Az.switchTo().window(win1);

		Thread.sleep(4000);

		Az.findElement(By.xpath("//input[@id= 'twotabsearchtextbox']")).click();

		Az.findElement(By.xpath("//input[@id= 'twotabsearchtextbox']")).clear();

		Az.findElement(By.xpath("//input[@id= 'twotabsearchtextbox']")).sendKeys("Nazro N60 hybid cover");

		Az.findElement(By.xpath("//input[@id= 'twotabsearchtextbox']")).sendKeys(Keys.ENTER);

		Thread.sleep(5000);

		WebElement Cart= Az.findElement(By.xpath("//span[@id= 'nav-cart-count']"));
		Cart.click();

		Thread.sleep(3000);

		Az.findElement(By.xpath("//input[@name='proceedToRetailCheckout']")).click();


		Az.close();

	     }

}
