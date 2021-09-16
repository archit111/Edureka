public class collect implements Runnable 
{
	public void run()
	{
		collect.printThread();
	}
	
	public synchronized void printThread ()
	{
		for (int i=0;i<5;i++)
		{
		System.out.println(Thread.currentThread().getName()+" - Number "+ i);
		}
	}
}

class Test
{
	public static void main(String args[])
	{
	collect c=new collect();
	Thread t1=new Thread(c,"state1");
	Thread t2=new Thread(c,"state2");
	Thread t3=new Thread(c,"state3");
	Thread t4=new Thread(c,"state4");
	Thread t5=new Thread(c,"state5");
	Thread t6=new Thread(c,"state6");
	t1.start();
	t2.start();
	t3.start();
	t4.start();
	t5.start();
	t6.start();
