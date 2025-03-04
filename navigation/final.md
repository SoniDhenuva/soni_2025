---
layout: page
title: Final
permalink: /final/
---

# DOSCE Bullet points (12 week summary)
<br>
<br>

### Chat Bot with CRUD Operations  
<br>

- Implemented **GET and POST** methods for handling user interactions.  
- Integrated **user stories** to ensure a structured approach to development.  
- [User Story](https://github.com/vibha1019/holiday_frontend/issues/6#issue-2719627668)  [Issue](https://github.com/vibha1019/holiday_frontend/issues/10#issue-2733774931)
<br>
<br>

### Survey System with CRUD Operations  
<br>

- Built a survey feature with **Create, Read, Update, and Delete (CRUD)** capabilities.  
- Built and developed a survey feature **GET, POST, and DELETE** requests for managing survey responses.  
- [Issue] (https://github.com/vibha1019/holiday_frontend/issues/31#issue-2843199625) 
<br>
<br>

### Frontpage Enhancements  
<br>

- Designed and optimized the front page for a **user-friendly experience**.  
- Added **snow animation** and dynamic background elements, like the background
- [Issue] (https://github.com/vibha1019/holiday_frontend/issues/34#issue-2883582384)
<br>
<br>

### API and Model Development
<br>

- Developed API endpoints for **both the Chat Bot and Survey System**.  
- Designed and implemented models to structure **data flow** efficiently.  
- Ensured API consistency and security.
<br><br>  

### Video Coordination & Demo  
<br>

- Organized and coordinated a **video summary** showcasing key developments.  
- Included a **demo of features** to highlight functionality.  
- Learned how to Summarize key points and talk efficiently


<br>
<br>
<br>
<br>
<br>

# N@TM
<br>


![Image](https://github.com/user-attachments/assets/1a329d9a-0d15-4dbf-b211-0899a4b7f447)
<br>

Here are our Reviews:
<br>

![Image](https://github.com/user-attachments/assets/4b73a795-9558-4a1e-bb7a-059d66978d75)
<br>

###  Positive Feedback (Pros) 
<br>

- **Front Page Animation** – The interactive animations on the home page were well-received.  
- **Gift Recommendation Concept** – Reviewers liked the idea of a site that **suggests gifts** based on user preferences. 
<br><br>


###  Areas for Improvement (Cons)  
<br>

- **Product Listings in Chat Bot** – Users wanted the chat bot to display **specific products with direct links** on the page.  
- **Consistent Theme Across Pages** – Reviewers suggested applying the design **theme uniformly across all pages** for better fluidity.  
- **Seamless Shopping Experience** – Users expressed interest in an option to **purchase items directly** from the site. 
<br><br> 

## Other Cool Websites at N@TM
<br>

![Image](https://github.com/user-attachments/assets/05802120-847e-43cb-9bed-e02a9621946b)
This was one of Period #1 CSP Classes for F! race lovers. I really loved their CSS and how all the page flow so smoothly. I also was discussing to them about how they integrated their style and learned that instead of CSS they used SASS style giving the website a more professional appeal.
<br><br>

![Image](https://github.com/user-attachments/assets/6408292e-8153-4fcf-8c74-22becb68d98f)
This was from CSA class. I really liked the idea of this website and how you can generate ideas using AI for your team teach, something that all CSSE, CSP, CSA students can utilize!


<br>
<br>
<br>
<br>
<br>

# MCQ 2020 Practice + Improvements
<br>

![Image](https://github.com/user-attachments/assets/6a761588-ba9d-49a5-90b2-ecd804b682a4)
I went up 5 points from last practice test i took
<br><br>

## My Analytics
<br>

![Image](https://github.com/user-attachments/assets/c50cbffb-d57b-46fb-a550-f1400cfbdaf4)
- I improved on the algorithms 16% from the last test
- I improved the computing systems and network 20% because of watching the CPT requirements in the videos in college board.
<br><br>

## Main Topics/Questions I struggled on
<br>

- Impact of Computing which was a 67%, Binary Numbers, Cybersecurity
<br><br>


![Image](https://github.com/user-attachments/assets/797eb7f2-5b13-47c8-9dc9-4ac7e1fe1b4a)
Incorrect. The binary RGB triplet for neutral gray is (01111111, 01111111, 01110000).
<br><br>

![Image](https://github.com/user-attachments/assets/3202ffd8-a31c-40f4-85fa-03e6d2b29e10)
Incorrect. Action I is helpful in program development. Consultation and communication with program users is an important aspect of program development.
<br><br>

![Image](https://github.com/user-attachments/assets/140082ad-a0d0-4e4a-a930-6f4cc9c0adf5)
Incorrect. Flooding an account with fraudulent traffic is considered a denial-of-service attack.
<br><br>

## What do I need to improve on:
<br>

### Impact of Computing 
<br>

- Focus more on **real-world applications and consequences** of computing decisions.
<br><br>  

### Binary Numbers & Representation
<br>

- Struggled with binary conversions, especially in RGB triplets.  
- Need to practice how different values represent shades of colors and binary arithmetic operations. 
<br><br>  

### Cybersecurity: Denial-of-Service (DoS) Attacks
<br>

- Incorrectly classified a **DoS attack**, mistaking it for another type of security breach.  
- Need to revisit different cyber threats, attack types, and security measures.

<br>
<br>
<br>
<br>
<br>

# 📌 Survey Feature (Leave a Review) Fulfillment Table  

| **Requirement**            | **How My Feature Fulfills the Requirement** |
|----------------------------|---------------------------------------------|
| **Input**                  | Users submit reviews by entering their feedback, ratings, and optional comments, which are processed and stored in the system. |
| **Use of List/Collection Type** | Reviews are stored in a collection that includes attributes like user name, rating, review text, and timestamps, allowing for easy retrieval and management. |
| **Procedure**              | The feature follows a structured process where users submit a review, the system processes and stores it, and the reviews are later displayed dynamically. |
| **Algorithm**              | The review system applies CRUD operations: Create (adding new reviews), Read (fetching and displaying reviews), and Delete (removing reviews). |
| **Output**                 | Submitted reviews are displayed in an organized format, showing the user's rating, feedback, and relevant details in real-time. |
| **Functionality Demonstration** | The survey feature’s ability to collect, manage, and display reviews using CRUD operations will be demonstrated through a video walkthrough. |

## 1. Input
``` python
@token_required()
def post(self):
    """Create a new survey response."""
    current_user = g.current_user
    data = request.get_json()

    if not data or 'message' not in data:
        return {'message': 'Survey message is required'}, 400

    # Create a new Survey response
    survey_response = Survey(
        message=data['message'],
        user_id=current_user.id
    )
```

### What it does

- request.get_json(): Captures the user’s survey response (message) as JSON input.  
- Validation (`if not data or 'message' not in data:`): Ensures that a message is provided before proceeding.  
- User ID association (`user_id=current_user.id`): Links the input to the authenticated user.  

## 2. **Use of List/Collection Type:**
<br>

   - **Line 63:** `surveys = Survey.query.all()` retrieves a list of all survey responses from the database. This is a collection of survey objects that will be returned as a list of responses.
   ``` python
   # Retrieve survey by ID
            survey_response = Survey.query.get(survey_id)
            if not survey_response:
                return {'message': 'Survey response not found'}, 404
<br><br><br>

## 3. **Procedure:**
<br>

   - **Procedure for Handling Survey Responses (CRUD operations):**
   <br>
     - **POST** (`post()` method): 
       - It starts by checking if the required data (`message`) is present.
       - Then, it creates a new survey response, tries to save it, and returns the result.
       <br>
     - **GET** (`get()` method): 
       - Retrieves a survey response by its `id` from the query parameters.
       - Returns the survey data or an error message if not found.
       <br>
     - **DELETE** (`delete()` method): 
       - Deletes the survey with the provided ID.
       <br>
       ``` python

       def create(self):
        """Adds a new survey response to the database."""
        try:
            db.session.add(self)
            db.session.commit()
        except IntegrityError:
            db.session.rollback()
            raise IntegrityError("Survey response creation failed due to a database error.")

    def read(self):
        """Returns a dictionary representation of the survey response."""
        return {
            'id': self.id,
            'message': self.message,
            'user_id': self.user_id
        }
    def delete(self):
        """Deletes the survey response from the database."""
        try:
            db.session.delete(self)
            db.session.commit()
        except IntegrityError:
            db.session.rollback()
            raise IntegrityError("Survey response deletion failed due to a database error.")
    ```
<br><br>

## 4. **Algorithm:**
<br>

   - **The sequence of operations in each HTTP method** forms an algorithm for handling survey data:
     - **POST**: Validate input → Create Survey object → Try saving → Return created data or error.
     - **GET**: Retrieve ID from query params → Query the database for the survey → Return survey data or error.
     - **DELETE**: Retrieve ID from query params → Locate the survey → Delete and return success or failure.
<br><br>

## 5. **Output:**
<br>

   - **In the `get()` methods**:
     - The output is a survey response (or a list of responses) that is returned as a JSON object, formatted using the `read()` method.
   - **In the `post()` method**:
     - The output is the updated survey response, or an error message if the update fails.
   - **In the `delete()` method**:
     - The output is a success message when the survey is deleted, or an error message if the deletion fails.

<br>
<br>
<br>
<br>
<br>

# Self-Grading
<br><br>

| **Concept**                | **Grade** | **Notes**                                                                                                                                                   |
|----------------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Dosce Bullets**           | 5/5       | Included burndown lists and issues for each of the 5 main tasks completed during my 12-week project, with explanations.                                      |
| **Fullstack Demo, CPT, N@TM Future Additions** | 1/2       | Need more logic-based code and should focus on improving the user-friendliness of the UI interface.                                                          |
| **Feature + FRQ**           | 1/1       | Clearly explained all parts of my feature and how it applies to each CPT requirement.                                                                       |
| **MCQ Reflection**          | 1/1       | Discussed my improvements on weak topics I struggled with before and addressed weaknesses in newer topics, along with strategies for improvement.            |
| **Presentation 10th Point** | 1/1       | N@TM, reviewed it with Ms. Pataki, sparked my interest in AI/ML, and led to an internship opportunity.                                                        |
| **Total**                   | 9/10      |                                                                                                                                                             |

---
<br>

### Growth
- Gained experience in providing code and algorithms for Fullstack development and Chatbots.
- Learned how to collaborate with teammates to resolve issues.
- Realized the importance of thorough planning before jumping into new projects (e.g., Chatbot project).
<br>

### Areas for Improvement
- Become more organized with tracking regular issues and burndown tasks.
- Avoid leaving all coding to the last minute, and handle the resulting stress when things break.
<br>

### Applying Skills to the Future
-Will integrate skills gained into future projects, focusing on improving project workflows, enhancing team collaboration, and applying the lessons learned to more advanced systems and algorithms..









<script src="https://utteranc.es/client.js"
        repo="SoniDhenuva/soni_2025"
        issue-term="title"
        label="blogpost-comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>