## CLICKJACKING ASSIGNMENT 

Clickjacking is a type of security threat in which an adversary makes the user click on a link involuntarily without his/her knowledge about  what the link is supposed to do.

### Version 1: 

A clickjacking page is created such that the user unintentionally downloads a malicious file.
This is achieved using a transparent layer(iframe) laid upon a bottom layer which the user perceives he is clicking.

<img width="926" alt="screen shot 2018-03-25 at 17 51 59" src="https://user-images.githubusercontent.com/37773779/37875830-762da704-3055-11e8-8d1d-d7ec52d007f4.png">

Fig 1: The code to lie one iframe on top of the other

<img width="922" alt="screen shot 2018-03-25 at 17 52 23" src="https://user-images.githubusercontent.com/37773779/37875828-75cb9776-3055-11e8-9374-cebe3d0c19b9.png">

Fig 2: The code to download malicious file unto system

### Version 2: 

In this, a page is created where the user thinks that he is liking the page of a website but is unintentionally liking another facebook page.
This is achieved by positioning the iframe of 2 pages in such a manner that both their like buttons coincide and as the top layer is transparent the user perceives that he/she is liking the page to the bottom iframe.

<img width="927" alt="screen shot 2018-03-25 at 17 51 47" src="https://user-images.githubusercontent.com/37773779/37875831-76606f2c-3055-11e8-9bdb-028f1ccbda28.png">

Fig 3: The code which redirects to the website not visible to the user.

### Version 3: 

Likejacking This is a slight improvement attack over version 2. As the top iframe is completely laid over the bottom iframe, it gets suspicious. So in this version a very small iframe is created which unlike previous versions is visible to users.

<img width="1198" alt="screen shot 2018-03-25 at 17 53 29" src="https://user-images.githubusercontent.com/37773779/37875826-755e32da-3055-11e8-942b-7de22a6b024b.png">

Fig 4: The website which is present in the small iframe.




Studied about various countermeasures like Framebuster and X-frame.

X-frame :
In x-frame, php code above the html is entered like
<?php>
	header(“X-Frame-Options: DENY”);
?>


Other X-Frame Options: SAMEORIGIN and ALLOW-FROM-%url%

Framebuster :
In framebuster a similar script is entered in the html page:
<script>
	if(self == top) {
		document.documentElement.style.display = ‘block’ ;
	} else{
		top.location = self.location;
	}
</script>
