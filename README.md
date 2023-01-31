# LA1400

```
package WilliRebecca;
import robocode.*;


public class Starbucks extends JuniorRobot
{
	boolean hitByBullet = false;
	

	public void run() 
	{
		setColors(orange, blue, white, yellow, black);

		// Robot main loop
		while(true) 
		{
			movement();
			energyOfEnemy();
			saveEnergy();
		}	
			
	}

	public void onScannedRobot() 
	{
		ahead(0);
		turnGunTo(scannedAngle);
		if(scannedDistance < 100);
		{
			fire(3);
		}
		
		fire(1);	
	}


	public void onHitByBullet() 
	{
		turnLeft(90);
		back( 40);	
		turnGunTo(scannedAngle);
		fire(1);
		hitByBullet = true;
	}
	
	public void onHitWall() 
	{
		turnRight(60);
		back(20);
	}	
	
	public void saveEnergy() 
	{
        if (energy <= 20) 
		{
			back(100);
			turnRight(90);
			ahead(fieldHeight / 3);
			turnRight(90);
		}
	}
	
	public void movement()
	{
		while(energy > 20)
		{
			if (hitByBullet == false); 
			{
				ahead(100);
				turnGunTo(scannedAngle);
				fire(1);
			}
			
			if(hitByBullet == true);
			{
				ahead(100);
				turnLeft(60);
			}	
		}
	}
	
	public void energyOfEnemy()
	{
		if(scannedEnergy < 20)
		{
			turnGunTo(scannedAngle);
			fire(3);
		}
		fire(1);
	}
}


```
