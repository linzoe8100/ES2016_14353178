#Lab1 Installation of DOL
***
##Description##
**The distributed operation layer**(DOL) is a framework that enables the (semi-) automatic mapping of applications onto the multiprocessor SHAPES architecture platform.

The DOL consists of basically three parts:


- **DOL Application Programming Interface**: The DOL defines a set of computation and communication routines that *enable the programming of distributed, parallel applications for the SHAPES platform*.


- **DOL Functional Simulation**: To provide programmers a possibility to *test* their applications, a functional simulation framework has been developed. Besides functional verification of applications, this framework is used to *obtain performance parameters* at the application level.


- **DOL Mapping Optimization**: The goal of the DOL mapping optimization is to compute a set of optimal mappings of an application onto the SHAPES architecture platform. 

##How to install##
- **necessary environment**

	`sudo apt-get update`

	`sudo apt-get install ant`

	`sudo apt-get install openjdk-7-jdk`

	`sudo apt-get install unzip`
- **install dol and systemc**

	`sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz`

	`sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip`
- **unzip dol and systemc**

	`$sudo mkdirdol`

	`$sudounzip dol_ethz.zip -d dol`

	`$sudotar -zxvfsystemc-2.3.1.tgz`
- **compile systemc**

    1. `cd systemc-2.3.1` enter the path of system-2.3.1

	2. `$sudo mkdir objdir`   build folder objdir

	3. `$cd objdir`  enter folder objdir

	4. `$sudo../configure CXX=g++ --disable-async-updates` run "configure"
	![](http://shcm09.baidupcs.com/file/6f33c058e02153ddc1099bba8c8fde40?bkt=p3-14006f33c058e02153ddc1099bba8c8fde401557729900000000d95a&fid=4017972734-250528-979207478416683&time=1475977211&sign=FDTAXGERLBH-DCb740ccc5511e5e8fedcff06b081203-XUchJ5GM%2FP7%2B%2FhT3i5NIroiEU%2FI%3D&to=sh09vb&fm=Yan,B,M,mn&sta_dx=55642&sta_cs=&sta_ft=jpg&sta_ct=0&sta_mt=0&fm2=Yangquan,B,M,mn&newver=1&newfm=1&secfm=1&flow_ver=3&pkey=14006f33c058e02153ddc1099bba8c8fde401557729900000000d95a&sl=79364174&expires=8h&rt=pr&r=616789749&mlogid=6549720754486661031&vuk=4017972734&vbdid=1054194258&fin=360%E6%88%AA%E5%9B%BE20161009003621901.jpg&fn=360%E6%88%AA%E5%9B%BE20161009003621901.jpg&slt=pm&uta=0&rtype=1&iv=0&isw=0&dp-logid=6549720754486661031&dp-callid=0.1.1&csl=100&csign=2MCA29NZK7P6W%2BV6rcxRXCWOqr8%3D)	
	


	5. `sudomake install`  

	6. get the current path,that is, the path of systemc `sudo pwd`

	

- **complie dol**

	

	1. `cd ../dol`

	
	2. open file **build_zip.xml**
	find`< property name="systemc.inc" value="YYY/include"/> `
	`< property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>`
	change YYY into the path of systemc	

	3. `sudo ant -f build_zip.xml all`

- **run first example**
	
	 `cd build/bin/main`

	  `ant -f runexample.xml -Dnumber=1`

	![](http://shcm09.baidupcs.com/file/6af9fb9f2b81451387c62f1328e75dc5?bkt=p3-14006af9fb9f2b81451387c62f1328e75dc54d9d61cd00000000cffd&fid=4017972734-250528-491281031202870&time=1475977038&sign=FDTAXGERLBH-DCb740ccc5511e5e8fedcff06b081203-wLZsGm3fiSfWFOeJAyCAumyfUqs%3D&to=sh09vb&fm=Yan,B,M,mn&sta_dx=53245&sta_cs=&sta_ft=jpg&sta_ct=0&sta_mt=0&fm2=Yangquan,B,M,mn&newver=1&newfm=1&secfm=1&flow_ver=3&pkey=14006af9fb9f2b81451387c62f1328e75dc54d9d61cd00000000cffd&sl=79364174&expires=8h&rt=pr&r=345168287&mlogid=6549674441320582094&vuk=4017972734&vbdid=1054194258&fin=test.jpg&fn=test.jpg&slt=pm&uta=0&rtype=1&iv=0&isw=0&dp-logid=6549674441320582094&dp-callid=0.1.1&csl=100&csign=2MCA29NZK7P6W%2BV6rcxRXCWOqr8%3D)
##Experimental experience##
In this lab,I've learned more about the operation on the LINUX OS.The use of ant in the lab showed only a small part of its funtion.Further study of ant is necessary to have skilled operation on the LINUX platform.

