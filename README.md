### General notes  
With every benefit listed, constraints must be considered.  
Every decision made should be made based on how the stakeholder would benefit from it, this should be mentioned when evaluating.  
Add descriptive diagrams like UML, Use case diagram, flowchart… where necessary.  


# Task 1 (Todo-List)
## Activity A (I) <br>
### Planning and system requirements <br>
•	Specify the minimum system requirements to run the application. <br>
  o	Processor <br>
  o	RAM <br>
  o	Hard disk space <br>
  o	Graphics card <br>
  o	Display <br>
•	Specify the minimum mobile requirements to run the application. <br>
  o	Processor <br>
  o	RAM  
  o	Android or IOS version   
  o	Battery capacity  
### Research  
•	Find at least 3 examples of applications that match the type you want to develop.  
•	State the features they all have in common and how they are used.  
• Find out about the legalities involved in making an application like this, Data, permissions and all  
•	Give a detailed description of how these applications work (each).  
•	State the negative sides you have found in the application.  
•	While talking about a specific application show screenshots of the interface to enable the reader to better understand what you are talking about.  
•	Evaluate the UI of the application, state what you like and what you would fix.  
•	If the applications have a website, take screenshots of the interface and evaluate them  
•	Talk about the website and how it works.  
•	Talk about how usable the website was.  
o	Learnability: How easy can the user understand it  
o	Efficiently: How easy can the user perform tasks  
o	Errors: How many errors can the user encounter and how is it handled  
o	Satisfaction: How pleasant looking is design  
•	Talk about all this in detail for all the websites.  
•	Talk about empathy map and how you will use it in the design. [Feel, thinks, says, does]  

## Activity A (II)  
### The Proposal  
•	In the proposal start with a [Motivational type sentence that gives the solution importance  
• The business context should be like a breakdown of what I have been asked to do  
•	List what I have been asked to do/ or what the owner wants.  
•	List the reason they want to build this solution, start with a paragraph that explains, then list   
•	List the benefits this might have. Start with a brief explanation and then list.  
• Talk about the stakeholder. Talk about how this positive or negative effects the outcome of the project will have on the stakeholders
•	Talk more on how this solution will help.  
•	State what the client would like the system to have. Use the words [Must, should, could] and list them according to importance.  
• Empathy map for all the stakeholders [Customer, Employee,Owner]  
•	List the different parts/layers of the system like [Mobile, web, database]. Explain then list.  
•	Create a use case diagram that visualises how the system would work.  
•	Explain how this works a bit.  
•	Using a quality model like FURPS (Functionality, usability, Reliability, Performance and supportability) explain how your proposal will meet all this.  
•	In the functionality, make sure to list the functional and non-functional requirements.  
•	State where the website will link to if any.  
•	List the accessibility features you might consider.  
•	Create a Hierarchy diagram for  
o	How a user would log in / Create an account   
o	Create a hierarchy diagram for any main action that can be performed using the application / Create a user journey diagram for the process.  
•	Talk about the UI/UX and how you want to approach it, talk about the needs and wants of the stakeholder.  
•	If needed create a sort of table that shows the features or activities that can be performed by each user [Admin, customer]  
•	Explain and evaluate the user requirements, justify the requirement. Explain who is likely to use the website and legalities involved.  #
• User acceptance criteria for each major section of your solutiion  
• Identify the potential risk and how you will mitigate them, like a table [Risk, Solution]    
•	Evaluate things like legal, accessibility and benefit/ disadvantages  [GDPR, Accessibility, Copyright, Data protection act]  
• Do this for the requirements [Table type (Features, priority, justification)].  
•	Conclude and evaluate what you will be creating [Like a paragraph explaining your solution]
### Guidance  
•	Make sure that the solution addresses all the needs of the client, make this obvious that you have considered this and explain how you have achieved this.  
•	Justify your proposal adequately in context to how this is what the stakeholder would want and your rationale behind such decisions.  
•	When you have stated all the positives remember to list the potential risks that are involved and how you intend to stop this from having any adverse effects on the solution  
•	While discussing make sure that you consider all the legal guidelines and regulation pertaining to how you want to develop the solution  
•	Make sure to break down and explain all the functional non-functional requirements and how they would benefit the software.  
•	Consider the KPI and user acceptance criteria, The KPI should be something like “The software should run on multiple types of devices” This would evaluate how and if this was net at the end. The user acceptance criteria should be in a user wants and can the user do type of scenario.  
## Activity B (I)  
### Visual/ interface designs  
•	For each design create a user interface  
•	Include a way to demonstrate user journey.  
•	The design should include justifications of the colours used.  
•	Follow the W3C guidelines.  
•	State the front-end requirements.  
•	State the back-end requirements.   
•	Evaluate the security of the system. In a general manner of who should do it and not how it should be done.  

### Algorithm  
•	Using pseudo code or any other appropriate method explain how functional parts like  
o	Login in
o	Registering a new user  
o	How booking an order would work.  
• Have a justification of each Algorith and put more context on how it should really work  
•	If needed create a table for each error that might happen for each algorithm and how it would be handled  
•	Create a Data table [Name, function, Data type and reason] of data that you will use.  
•	Create diagrams to explain the backend [Data Model].  
o	Conceptual  
o	Logical  
o	Physical  
•	Explain how you intend to test this system [Type, Who, data set, when, time, outcome]  

# Task 2  (Todo)
•	[Do your thing :)]  
• To save time writing sql commands use this site where you can just modify the command to your specific need (https://www.sitepoint.com/getting-started-sqlite3-basic-commands/)  
• If you are using sql and node sqlite you can use this starter template to speed up development  

// Define the login route
app.post('/login', async (req, res) => {
    const { username, password } = req.body;

    // Query the database for the user
    const query = 'SELECT * FROM users WHERE username = ?';
    db.get(query, [username], async (error, user) => {
        if (error) {
            console.error('Error executing query:', error);
            return res.status(500).json({ message: 'Internal server error' });
        }

        if (!user) {
            // User not found
            return res.status(401).json({ message: 'Invalid username or password' });
        }

        // Compare provided password with the stored hashed password
        const passwordMatch = await bcrypt.compare(password, user.password);

        if (passwordMatch) {
            // Password is correct
            return res.json({ message: 'Login successful', user });
        } else {
            // Password is incorrect
            return res.status(401).json({ message: 'Invalid username or password' });
        }
    });
});

// Start the server
const port = 3000;
app.listen(port, () => {
    console.log(`Server is running on port ${port}`);
});

![image](https://github.com/Ayblue004/revision/assets/96060807/4a004855-f265-4f17-8f5f-d3be17d543cf)  
![image](https://github.com/Ayblue004/revision/assets/96060807/65485710-ec4b-44e2-8f5b-5eee3983fa74)  
![image](https://github.com/Ayblue004/revision/assets/96060807/5b8de68a-9060-4d8b-bfef-292b610aaa4c)

• For the front-end, if you are using angular, this template could be used as well.
![image](https://github.com/Ayblue004/revision/assets/96060807/2207a2d6-c8a6-4678-9fdd-1b3340147102)  

•	For the code  
o	Use a consistent naming convention.  
o	Indent properly.  
o	Comment all the section.  
•	For tracking  
•	Document and explain your development process.  
• Create a table that explains your versioning ([Version, date, Changes Made and Reason])  
•	Add dates and use a versioning system.  
• After you change the version, Identify what the problems were and how you acted and fixed them  
•	For asset log use a table and  
o	Show the image if necessary.  
o	The source of the image  
o	Why you used this. Not how you got it but why you are using it regarding to the application.  
o	A table to link to external sites if necessary.  
•	For submission show and explain the interface of all your code  
• In the assets section, explain the images and links you have choosen regarding to legal, ethical and moral issues  
• For testing use a test Heuritics sheet  
•	The interface and labels that explains what “what” does.  
•	A document that shows your code and explain blocks and what you were doing.  
• A breif explanation on the type of testing you want to do like unit testing...  
•	[Create a test plan for each part of the application] this would be classified as unit testing.  
•	[Test the application]  test the whole application  
•	A table testing each part of the code.  
•	Show the outcome of the fixes you made after testing and explain how they are now better.  
### Guidance  
•	Make sure you use more than one programming language.  
• Ensure to collectt user input no matter how little so you can have something to test  
• Make sure to add commments to the code that explains the logic of what you are doing  
# Task 3A  
•	Get technical and non-technical users.    
• In the planning stage make sure to plan   
  o Who is your technical and non-technical user  
  o How will they give me feedback and how will I get the feedback forms, verbally ?  
  o What kind of questions to ask them ?  
  o What is my motive and what type of data am I hoping to get e.g about the functionality or about the interface  
  o Interview or observation... on what and on who?  
• Explain in details how you plan to gather high quality unbiased feedback  
• Add observational feedback, like what you noticed during interviews and stuff  
• Highlight the technical and none technical questions you will be asking each group  
•	Ask questions that you can act on [Apart from general questions]    
• For collectiing data you can use a table of [Name, type of audience, problem encountered, solution  
• You could have a rating of what they rate each section and like a google play store type format  
•	At the end of every individual feedback evaluate it and make sure you understand what they meant    
•	Have a list of things you need to improve due to the feedback that you received.  
### Guidance  
• The materials should allow for the gathering of high quality feedback for different aspect of the developed prototype  
• The use of the tools has resulted in feedback that consistently provides the opportunity for evidence- informed further iteration  
• Quality of communication is effective for both technical and non-technical audiences as a result of consistent use of appropriate techniques, methods and formats  
• The use of technical language that is consistently appropriate for the intended audience  
# Task 3B  
•	Talk about the key performance indicator in the essence of what the stake holder wanted and what you were able to deliver.  
• If possible lsit each KPI and state how you have met the requirement  
• While evaluating give examples and show proof like how that point as applied in the development  
•	Evaluate if all this have been met and how they have been met.  
• Talk about the legal implications of decisions you have made regarding  
  o Storing user data  
  o Assets used  
• Think about concepts like the GDPR, DPA, copyright and accessibility  
•	Talk about future developments which might have been highlighted during development or after development. Talk about how this will improve the application.  
### Guidance  
•	Consider how your solution meets these requirements rather than describing what you did.  
•	Make a valued judgment in relation to each of the bullets listed on the marking grid which are.  
  o	Functional and non-functional requirements of the system
  o	KPI’s  
  o	User acceptance criteria   
  o	Consideration of feedback  
•	Talk about the legal issues and why you feel your source is reliable regarding to assets.  
•	Evaluate how much have met the KPIs that you have set.  
•	Don’t lie.   



Task 1: 20 hours [Proposal – 24, Design and test plan – 34] <br>
Task 2: 30 hours [Prototype – 48] <br>
Task 3a: 15 hours [Feedback – 24] <br>
Task 3b: 2 hours [Evaluation – 15] <br>
