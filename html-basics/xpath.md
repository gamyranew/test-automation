9. Relative XPath Expressions examples set 4:

- locating Button2

- Locating all the tags having id attribute value as but2
	- locating all input tags //input
	- locating all anchor tags //a
	- locating all button tags //button
	- locating all tags //*
		//*[@id=‘but2’]


- Locating button tags having any attribute value as but2
		//button
		//button[@*=‘but2’]
- Locating button tags having id attribute value as anything
		//button
		//button[@id]

10. Set 5
- Locate the first input tag and second input tag having the name attribute value as 	gender 
		//input
		//input[@name=‘gender’]
		//input[@name=‘gender’][1]
		//input[@name=‘gender’][2]
- Locate all the tags on the web page having the name attribute value as ‘gender’
		//*
		//*[@name=‘gender’]
- Locate all input tags on the web page having name attribute as anything
		//input
		//input[@name]
- Locate all the tags on the web page having id attribute value as radio1 and the    	name attribute value as gender
 		//*
		//*[@id=‘radio1’][@name=‘gender’]
- Locate all the tags on the web page having either id attribute value as radio1 or 	name attribute value as gender
		//*
		//*[@id=‘radio1’or@name=‘gender’]
http://www.selenium143.blogpost.com

11. Set 6
- Locate all the hyperkinks on the web page
		//a
- Find all the hyperlinks on the page having the href attribute value as 
		http://www.selenium143.blogpost.com
    	//a
		//a[@href=‘http://www.selenium143.blogpost.com']
- Find the first hyperlink on the web page having href attribute value as 
		http://www.selenium143.blogpost.com
		//a	
		//a@href=‘http://www.selenium143.blogpost.com'][1]

- Find the second hyperlink on the web page having href attribute value as 
	http://www.selenium143.blogpost.com
		//a	
		//a@href=‘http://www.selenium143.blogpost.com'][2]

- Difference between with ()- [locate on page level],  and without () -[locate on tag 	level), in the above example.

12. Set 7

- Locate the first child of ‘html’ tag
		//html
		//html/*[1]
- Locate the second child of ‘html’ tag
		//html	
		//html/*[2]
- Using //in b/n thr Relative XPath Expression
		//html//p[@id=‘para1’] - shortcut (to get to paragraph)

13. XPath Expressions - Wild Cards

- The two Wild Cards that can be used in the XPath Expression:
			1. *
			2. node()
	* - is used to represent any tag or any attribute name.
			//*
			//*[@*]
	node() - is only used to represent any tags.
		/html/body/p[1]
		/node()/node()/p[1]

	* - is the most used WC in XP E.
	node()- leased used and can be replaced usinng * 
			/node()node()p[1]
			/*/*/p[1]
	node() should not be suded at the end of the Expession
			/html/body/node() in invalid
- Using node() in Relative XPath Expressons
			//body/p[1]
			//node()/p[1]

14. XPath Expressions - HTML Tables

- Locating all tables on the page
		//table
- Locating a specific table 
		//table[@id=‘table’]
- Locating all the rows in the table
		//table[@id=‘table1]//tr
- Locate all the table headings in the table 
		//table[@id=‘table1]//th
- Locate all the table data 
		//table[@id=‘table1’]//td
- Locate all the cells in the table (i.e. table headings+ table data)
		//table[@id=‘table1’]th
		//table[@id=‘table1’]td
		//table[@id=‘table1]th//table[@id=‘table1’]//td
- Locate the second data row and the third column
		//table[@id=‘table1’]tr
		//table[@id=‘table1]//tr[2]
		//table[@id=‘table1]//tr[2]//tr[3]

15. Different XPath functions:
		- position()
		- last()
		- text()
		- contains()
		- starts-with()

16. text() XPath Function ( using tex() to locate UI element)- the entire text of the 	UI must be provided)

- Locate PracticeAutomationHere text using text() XPath function
			//p[text()=‘PracticeAutomationHere’]
- Use . instead of text()
		//p[.=‘PracticeAutomationHere’]

        Other examles:
		//a[text()=‘SeleniumTutorial’]
		//a[text()=‘Selenium143’]
		//a[text()=‘PageOne’]
		//a[text()=‘Button2’]
		//li[text()=‘One’]
- text()function cannot be used when there is no text b/n tags

17. contains()XPath Function - can be used with partial text or values to locate a UI 	element.
		//p[text()=‘PracticeAutomation’]
		//p[contains(text(),’PracticeAutomation’)]
		//p[contains(.,’PracticeAutomation’)]

- providing partial values assigned to the attributes of HTML tags

		//input[contains(@value,’ra’)]
- The actual purpose of the contains()function is real time Selenium Automation  	cases.	
		id=’123QAFoxing123’to id=’456QAFox456’.
		//tagName[cintains(@id,’QAFox’)]

18. starts-with() XPath Function - can be used with the beginning portion of the text 	or the attribute values assigned to the attributes of the HTML tags:

		//p[starts-with(text(),’Practice’)]			//p[starts-with(.,’Practice’)]	
		//input[starts-with@value,’or’)]

	- the actual purpose of the starts-with() function in real time Selenium 		Automation cases:
		id=‘QAFox123456’to id=‘QAFox789012’
		//tagNames[starts-with@is,’QAFox’)]

19. last()XPath Function - can be used to locate the last UI on the web page
		//p[1]
		//p[last()]	
		//p[last()-1]
		//body/*[1]		
		//body/*[last()]
		(//input)[1]
		(//input)[last()]
		(//input)[last()-1]	
		(//input)[last()-2]
		//p[1][@class=‘main’]
		//p[last()][@class=‘sub’]

20. position()XPath Function
		//p[position()=1]
		//p[position()=2]
		(//input)[position=1]	
		(//input)[position=8]

21. Different XPath AXES:

	- XPath AXES is a concept that makes XPath Expressions powerful and unbeatable in 	locating the UI elements out of all the locator types(such as id/name/class/	linktext/css selectors/DOM) bc can locate 99.99% of the UI.
	- XPath AXES are used to locate the required UI element by means of id/name/class 	name attribute values of the othe UI elements. 
			XPath AXES: 
				+ following-sibling 
				- namespace
				+ parent
				+ preceding	
				+ preceding- sibling
				- self
				+ ancestor	
				- ancestor-or-self
				- attribute
				+ child 
				+ descendant
				- descendant-or-self
				+ following 	

22. following XPath AXES can select/traverse everuthing in the HTML doc AFTER the 	CLOSING TAG or the current node.
	- if you’re using ‘following’ XPath Axes with ‘head’ tag, then it can help to 	select/traverse all teh tags that come after the ending of ‘head’ tag 
				(i.e. after </head>tag).

				//head/following::title - not possible
				//head/following::body
			- find all the div tags after //body/div[1]/div
				//body/div[1]/div/following::div
			- find the first div tag after //body/div[1]/div
				//body/div[1]/div/following::div[1]
			- find all the input tags after //body/div[1]
				//body/div[1]/following::input
			- find the first input tag after //body/div[1]
				//body/div[1]/follwing::input[1]

23. preceding XPath AXES - is used to select/traverse all the tag in the HTML doc 	BEFORE the CURRENT TAG, except current parent & ancestor tags.
	- Locate the second paragraph on the page
				//p[@id=‘para2’]
	- Locate the first p tag 	
				//p[@id=‘para2’]/preceding::p
	- Locate the ‘head’ tag 
				//p[@id=‘para2’]/preceding::head
	- Locate the ‘title’ tag
				//p[@id=para2’]/preceding::body
	- Cannot locate the ancestor tags though they come before the current tag
				//p[@id=‘para2]/preceding::html

24. following-sibling XPath AXES is used to select/traverse all the sibling tags in 	the HTML doc that come BEFORE the CURRENT TAG.
	- Locate the ‘head’ tag
				//head
	- Locate the ‘body’ sibling tag that comes after the ‘head’ tag:
				//head/following-sibling::body
	- Locate the first ‘p’ tag on the page:
				//p[@id=‘para1’]
	- Locate the ‘p’ sibling tag that comes after the first ‘p’ tag:
				//p[@id=‘para1]/following-sibling::p
	- Locate the 1st div tag that comes after the body tag:
				//body/div[1]
	- Locate all the sibling div tags which come after the first div tag:
				//body/div[1]/following-sibling::div
	- Locate the first sibling div tag which comes after the first div tag:
				//body/div[1]/following-sibling::div[1]

25. preceding-sibling XPath AXES are used to select/traverse all the sibling tags in 	the HTML doc that come BEFORE the current tag.
	- Locate the ‘body’ tag
				//body
	- Locate the ‘head’ sibling tag that comes before the ‘body’ tag:
				//body/preceding-sibling::head
	- Locate the second ‘p’ tag on the page:
				//p[@id=‘para2’]
	- Locate the ‘p’ sibling tag that comes before the second ‘p’ tag:
				//p[@id=‘para2]/preceding-sibling::p
	- Locate the fouth div tag that come after the body tag:
				//body/div[4]
	- Locate all the sibling div tags that come before the fourth div tag:
				//body/div[4]/preceding-sibling::div
	- Locate the first sibling div tag which comes before the fourth div tag:
				//body/div[1]/preceding-sibling::div[1]

26. parent XPath AXES are used to locatthe/select the parent tag of the current tag 	in 	the HTML doc:
	
	- Locate the ‘head’ tag:
				//head
	- Locate the ‘html’ parent tag of the ‘head’ tag:
				//head/parent::html
	- Locate the parent tag of the ‘body’ tag:
				//body/parent::html
	- Locate the parent of the ‘title’ tag:
				//title/parent::head
	- Loacate the parent of the ‘p’ tag:
				//p/parent::body
	- Locate the parent of the first ‘p’ tag:
				//p[1]parent::body
	- Locate the parent of the second ‘p’ tag:
				//p[2]/parent::body

27. child XPath AXES selects/locates the child tag of the current tag in HTML doc.
		
	- Locate the ‘html’ tag:
				//html
	- Locat the ‘head’ child tag of the ‘html’ tag:
				//html/child::head
	- Locate the ‘body’ child tag of the ‘html’ tag:
				//html/child::body
	- Loacate the ‘title’ child tag with ‘head’ tag:
				//head/child::title
	- Locate the ‘p’ child tag with ‘body’ tag:
				//body/child::p
	- Locate the first ‘p’ child tag with ‘body’ tag:
				//body/child::p[1]	
	- Locate the second ‘p’ child tag with ‘body’ tag:
				//body/child::p[2]

28. ancestor XPath AXES select/locate the parent and grandparent tags of the current 	tag in the HTML doc:
	- Locate the ‘title’ tag:
				//title
	- Locate the ‘html’ grandparent tag of the ‘title’ tag:
				//title/ancestor::html
	- Locate the ‘head’ parent tag of the ‘title’ tag:
				//title/ancestor::head
	- Locate the ’html’ parent tag with ‘head’ tag:
				//head/ancesor::html
	- Locate the ‘html’ parent tag with ‘body’ tag:
				//body/ancestor::html
	- Locate the ‘body’ parent tag with ‘p’ tags:
				//p/ancestor::body
	- Locate the ‘html’ grandparent tag with ‘p’ tags:
				//p/ancestor::html
	- Locate the ‘html’ grandparent tag with the first ‘p’ tag:
				//p[1]/ancestor::html

29. descendant XPath AXES select/locate the child and grandchild tags of the current 	tag in the HTML doc.
	
	- Locate the ‘html’ tag
				//html
	- Locate the ‘title’ grandchild tag of the ‘html’ tag:
				//html/descendant::title
	- Locate the ‘head’ child tag of the ‘html’ tag:
				//html/descendant::head
	- Locate the ‘body’ child tag with ’html’ tag:
				//html/descendant::body
	- Locate the ‘p’ grandchild tag with ‘html’ tag:
				//html/descendant::p
	- Locate the ‘p’ child tags with ‘body’ tags:
				//body/descendant::p
	- Locate the first ‘p’ granchild with ‘html’ tag:
				//html/descendant::p[1]	

30. Advantages of Relative XPath Expressions over the Absolute XPath Expression:
	- Relative XPath Expressions are reliable and not changing on performing small 	changes on the UI.
	___