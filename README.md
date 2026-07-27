<img width="975" height="182" alt="image" src="https://github.com/user-attachments/assets/e04cd7ac-3022-4236-80a5-b3d1b757f6c6" />

# Computer Science ePortfolio   SNHU CS-499 by Beverly Vaughan

# Gaming Development * Coding * Java * C++ * 3D Modeling * Web Creation

#### July 1, 2026

### Introduction

Welcome to my ePortfolio. My name is Beverly Vaughan, and I am a computer science student developing skills in software engineering, algorithms and data structures, databases, computational graphics, and full-stack development. This portfolio highlights selected projects that demonstrate my growth as a programmer and problem solver. Through these artifacts, I show my ability to design, develop, test, and improve software solutions using industry-relevant tools and practices.

### Button Section

### Projects | Resume | GitHub

### Professional Assessment

  Throughout my computer science program, I have developed a stronger understanding of how to design, build, test, and improve software solutions. The work I completed in my courses has helped me grow as a problem solver, programmer, and technical communicator. My ePortfolio represents this growth by showing selected artifacts that demonstrate my ability to apply computer science concepts in practical ways. These artifacts highlight my skills in software design and engineering, algorithms and data structures, databases, and the use of modern development tools.
One of the most important skills I have developed is the ability to approach problems systematically.    In earlier projects, I often focused mainly on getting the program to work. As I progressed through the program, I learned that successful software development also requires planning, clean design, testing, documentation, and maintainability. My enhanced artifacts show this growth because I revisited previous work and improved it with a more professional mindset. This process helped me understand that software is rarely finished after the first version; it can always be refined to better meet user needs and technical standards.
  My coursework has also strengthened my ability to design and evaluate computing solutions. In software design and engineering, I learned how to organize code, improve functionality, and create applications that are easier to understand and maintain. These skills are important because professional software must be reliable, readable, and adaptable. Through my enhancements, I demonstrated that I can identify weaknesses in an existing project and make meaningful improvements that increase the value of the final product.
In algorithms and data structures, I developed a deeper appreciation for efficiency and logic. I learned that the way data is organized and processed can affect the performance and usability of an application. By improving algorithmic logic and applying more effective data structures, I was able to show my ability to think critically about how a program works behind the scenes. This skill is important in computer science because strong technical decisions can make software faster, more reliable, and easier to scale.
My database-related work helped me understand how applications store, retrieve, and manage information. I gained experience working with database operations, queries, and data-driven applications. These experiences showed me the importance of accuracy, security, and organization when handling data. The database artifact in my ePortfolio demonstrates my ability to connect an application to a data source and use that data in a meaningful way to support user needs.
Another major area of growth has been communication. Computer science professionals must be able to explain technical choices clearly to different audiences. Through code reviews, written narratives, and project documentation, I practiced explaining what I built, why I made certain design decisions, and how my work connects to broader course outcomes. This helped me become more confident in presenting my technical abilities in a professional way.
  Overall, my ePortfolio shows that I have grown into a more thoughtful and capable computer science student. I have learned how to combine creativity, logic, and technical skill to solve problems and improve existing work. While I still have areas where I want to continue growing, especially in advanced development practices and deeper testing strategies, I feel more prepared to enter the professional field. My completed artifacts demonstrate my ability to learn new technologies, troubleshoot challenges, communicate effectively, and build software solutions that reflect both technical knowledge and professional growth.

### Course Outcomes

1.	I will employ strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science.
2.	Design, develop, and deliver professional-quality written, and visual communication.
3.	Evaluate computing solutions while managing the trade-offs involved in designing.
4.	The ability to use innovative techniques, skills, and tools

### Code Review

A strong artifact for the Software Engineering and Design category would be your CS 340 Grazioso Salvare Animal Shelter Dashboard.
This artifact fits the category well because it demonstrates full-stack software design concepts, including database interaction, modular CRUD operations, dashboard development, filtering logic, and user-centered interface design.

### Artifact Selection and Origin

### A Category One: Software Engineering and Design

  For my Software Engineering and Design artifact, I selected the Grazioso Salvare Animal Shelter Dashboard that I originally developed in CS 340: Client/Server Development. The project was created to help the fictional rescue organization Grazioso Salvare identify dogs that may be good candidates for specialized rescue training. The dashboard connects to a MongoDB database containing Austin Animal Center shelter outcome data and allows users to filter animals by rescue type, view matching records in a data table, and visualize animal locations and breed distributions.
  The original artifact included a Python CRUD module that connected to MongoDB and supported create, read, update, and delete operations. It also included a Dash-based web dashboard that displayed animal shelter data through interactive components such as a data table, pie chart, and geographic map. This project originated as a course assignment focused on applying database management, client/server architecture, and software design principles to a real-world-style problem.

### Why This Artifact Fits Software Engineering and Design

T  his artifact aligns with the Software Engineering and Design category because it shows my ability to design and implement a software solution that connects a backend database to an interactive frontend interface. It demonstrates modular programming through the use of a separate CRUD class, database query design through MongoDB filters, and interface design through Dash components. The project also reflects software engineering practices such as separating concerns, organizing code into reusable functions, and designing the application around the needs of an end user.

### Enhancement Plan

  For my enhancement, I would improve the artifact by making the dashboard more maintainable, secure, and user-friendly. First, I would refactor the code so that database connection settings are stored in environment variables instead of being hard-coded into the program. This would improve security and make the application easier to deploy in different environments. Second, I would improve the CRUD module by adding stronger input validation, exception handling, and clearer return messages. This would make the backend more reliable and easier to debug.
  I would also enhance the dashboard interface by improving the filtering system, adding clearer labels, and making the visualizations more responsive. For example, I could allow users to select multiple rescue types or combine filters such as breed, age range, and sex. I would also add comments and documentation throughout the code so future developers could better understand how the dashboard works.

### File to Submit

For the required file, I will include the main code connected to the artifact. A good submission file could be named:

**AnimalShelterDashboard_EnhancementPlan**

**Artifact: Grazioso Salvare Animal Shelter Dashboard**

**A Category One: Software Engineering and Design**

**Origin:**

This artifact was originally created in CS 340: Client/Server Development.
The purpose of the project was to design a dashboard that connects to a
MongoDB animal shelter database and helps Grazioso Salvare identify dogs
that may be suitable for rescue training programs.

**Enhancement Plan:**

1. Improve security by moving MongoDB credentials into environment variables.
2. Refactor the CRUD module to improve modularity and maintainability.
3. Add input validation and exception handling to database operations.
4. Improve dashboard filtering options for rescue type, breed, age, and sex.
5. Improve user interface labels, chart responsiveness, and dashboard usability.
6. Add comments and documentation to make the code easier to understand.

**CODE:**

from pymongo import MongoClient
from bson.objectid import ObjectId

class AnimalShelterCRUD:

 """CRUD operations for the animal shelter MongoDB collection."""

     def __init__(self, username, password, host="localhost", port=27017, db="aac", collection="animals"):
        connection_string = f"mongodb://{username}:{password}@{host}:{port}/?authSource=admin"
        self.client = MongoClient(connection_string)
        self.database = self.client[db]
        self.collection = self.database[collection]

    def create(self, data):
        """Insert a new animal record into the database."""
        if data is not None and isinstance(data, dict):
            result = self.collection.insert_one(data)
            return result.inserted_id is not None
        raise ValueError("Data must be a non-empty dictionary.")

    def read(self, query):
        """Read animal records from the database based on a query."""
        if query is not None and isinstance(query, dict):
            return list(self.collection.find(query))
        raise ValueError("Query must be a dictionary.")

    def update(self, query, update_data):
        """Update animal records that match the query."""
        if isinstance(query, dict) and isinstance(update_data, dict):
            result = self.collection.update_many(query, {"$set": update_data})
            return result.modified_count
        raise ValueError("Query and update data must be dictionaries.")

    def delete(self, query):
        """Delete animal records that match the query."""
        if query is not None and isinstance(query, dict):
            result = self.collection.delete_many(query)
            return result.deleted_count
        raise ValueError("Query must be a dictionary.")

def build_query(filter_type):
    """Build MongoDB queries based on selected rescue category."""

    water_breeds = [
        "Labrador Retriever Mix",
        "Chesapeake Bay Retriever",
        "Newfoundland"
    ]

    mountain_breeds = [
        "German Shepherd",
        "Alaskan Malamute",
        "Siberian Husky"
    ]

    disaster_breeds = [
        "Doberman Pinscher",
        "German Shepherd",
        "Golden Retriever"
    ]

    if filter_type == "Water Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": water_breeds},
            "sex_upon_outcome": "Intact Female",
            "age_upon_outcome_in_weeks": {"$gte": 26, "$lte": 156}
        }


    elif filter_type == "Mountain/Wilderness Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": mountain_breeds},
            "sex_upon_outcome": "Intact Male",
            "age_upon_outcome_in_weeks": {"$gte": 26, "$lte": 156}
        }

    elif filter_type == "Disaster Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": disaster_breeds},
            "sex_upon_outcome": "Intact Male",
            "age_upon_outcome_in_weeks": {"$gte": 20, "$lte": 300}
        }

    else:
        return {}


**B. Category Two: Algorithms and Data Structures**

  For the Algorithms and Data Structures category, I selected my CS 330 2D Animation project. This artifact was originally created in CS 330: Computational Graphics and Visualization. The project used C++ and OpenGL to create an interactive 2D animation similar to a brick breaker game. The program included a paddle controlled by user input, moving balls, destructible and reflective bricks, collision detection, color changes, and object state updates.

  The original artifact included classes such as Brick and Circle. The Brick class stored information such as position, width, color, brick type, status, and remaining hits. The Circle class stored position, radius, color, velocity, and collision behavior. The program used arrays or collections of bricks and balls to update and render multiple objects during each frame of animation. It also used collision-detection logic to determine when a ball hit a wall, paddle, brick, or another ball.

  This artifact aligns with the Algorithms and Data Structures category because the main behavior of the program depends on algorithms for movement, collision detection, object interaction, and state management. It also uses data structures to organize multiple bricks and moving balls. The enhancement will focus on improving the efficiency and complexity of these algorithms and data structures rather than only cleaning up or commenting on the code.

   For the code file submission, I will include the original 2D animation source code along with my enhancement plan. A suitable file name would be: 

CS330_2DAnimation_AlgorithmsEnhancement.cpp

The file will contain the original classes and logic for the brick and ball objects, along with comments describing the planned algorithmic improvements.

Pseudocode for Planned Enhancement

Create grid with rows and columns
Each grid cell stores a list of brick references

FUNCTION buildSpatialGrid(bricks):
    Clear all grid cells

    FOR each brick in bricks:
        IF brick is active:
            Determine the grid cell based on brick.x and brick.y
            Add brick to that grid cell

FUNCTION updateGameFrame():
    Move each ball

    FOR each ball in balls:
        Check wall collision
        Check paddle collision

        Determine ball's current grid cell

        nearbyCells = current cell plus neighboring cells

        FOR each cell in nearbyCells:
            FOR each brick in cell:
                IF brick is active:
                    IF ball collides with brick:
                        Update ball direction
                        Update brick hit count
                        IF brick has no hits remaining:
                            Set brick status to inactive

    Render balls

    Render active bricks
    Render paddle

**C Category Three:Databases**

  For the Databases category, I selected my Grazioso Salvare Animal Shelter Dashboard from CS 340: Client/Server Development. This artifact was originally created as a Python Dash dashboard connected to a MongoDB database containing animal shelter outcome data from the Austin Animal Center. The project was designed for the fictional organization Grazioso Salvare, which needed a way to search animal shelter records and identify dogs that may be suitable for different rescue-training categories.

  The original artifact used MongoDB as the database and included a Python CRUD module to create, read, update, and delete animal records. The database collection stored information such as animal type, breed, age, sex, outcome type, location latitude, location longitude, and other shelter outcome details. The dashboard allowed users to filter records by rescue category and view matching animals in a data table, map, and chart.
  
  This artifact aligns with the Databases category because the main purpose of the project was to connect an application to a database, retrieve records, filter data, and display database results through an interactive interface. The original project demonstrated basic database connectivity and CRUD operations, but the enhancement will focus on improving the database layer by adding more advanced querying, indexing, aggregation, and data validation.
For the code file submission, I will include the Python CRUD module and the dashboard code that connects to MongoDB. A suitable file name would be:

GraziosoSalvare_DatabaseEnhancement.py

  The submitted code file will include the original database connection and CRUD operations, along with comments describing the planned database-focused enhancement. The enhancement will expand the database functionality beyond basic record retrieval by adding improved query logic, indexes, aggregation pipelines, and stronger validation.
Pseudocode for Planned Database Enhancement

START

Connect to MongoDB database

Create indexes on commonly searched fields:
    animal_type
    breed
    sex_upon_outcome
    age_upon_outcome_in_weeks
    outcome_type

User selects filter options from dashboard:
    rescue type
    breed
    sex
    minimum age
    maximum age
    outcome type

Build MongoDB query dynamically:
    IF rescue type is selected:
        Add rescue-type conditions to query

    IF breed is selected:
        Add breed condition to query

    IF sex is selected:
        Add sex condition to query

    IF age range is selected:
        Add age range condition to query

    IF outcome type is selected:
        Add outcome type condition to query

Send query to MongoDB

Retrieve matching animal records

Run aggregation pipeline:
    Count total matching animals
    Group matching animals by breed
    Calculate average age
    Group matching animals by outcome type

Return records and summary results to dashboard

Update data table, map, chart, and summary section

END

CODE REVIEW VIDEO FILE:

"C:\Users\waito\Downloads\Computer Science Video - Compressed (1).mp4"

**A Category One: Software Engineering and Design**
**Enhancement Plan**

For my enhancement, I would improve the artifact by making the dashboard more maintainable, secure, and user-friendly. First, I would refactor the code so that database connection settings are stored in environment variables instead of being hard-coded into the program. This would improve security and make the application easier to deploy in different environments. Second, I would improve the CRUD module by adding stronger input validation, exception handling, and clearer return messages. This would make the backend more reliable and easier to debug.

I would also enhance the dashboard interface by improving the filtering system, adding clearer labels, and making the visualizations more responsive. For example, I could allow users to select multiple rescue types or combine filters such as breed, age range, and sex. I would also add comments and documentation throughout the code so future developers could better understand how the dashboard works.

"""
Artifact: Grazioso Salvare Animal Shelter Dashboard
Category: Software Engineering and Design

Origin:
This artifact was originally created in CS 340: Client/Server Development.
The purpose of the project was to design a dashboard that connects to a
MongoDB animal shelter database and helps Grazioso Salvare identify dogs
that may be suitable for rescue training programs.

Enhancement Plan:
1. Improve security by moving MongoDB credentials into environment variables.
2. Refactor the CRUD module to improve modularity and maintainability.
3. Add input validation and exception handling to database operations.
4. Improve dashboard filtering options for rescue type, breed, age, and sex.
5. Improve user interface labels, chart responsiveness, and dashboard usability.
6. Add comments and documentation to make the code easier to understand.
"""

from pymongo import MongoClient
from bson.objectid import ObjectId


class AnimalShelterCRUD:
    """CRUD operations for the animal shelter MongoDB collection."""

    def __init__(self, username, password, host="localhost", port=27017, db="aac", collection="animals"):
        connection_string = f"mongodb://{username}:{password}@{host}:{port}/?authSource=admin"
        self.client = MongoClient(connection_string)
        self.database = self.client[db]
        self.collection = self.database[collection]

    def create(self, data):
        """Insert a new animal record into the database."""
        if data is not None and isinstance(data, dict):
            result = self.collection.insert_one(data)
            return result.inserted_id is not None
        raise ValueError("Data must be a non-empty dictionary.")

    def read(self, query):
        """Read animal records from the database based on a query."""
        if query is not None and isinstance(query, dict):
            return list(self.collection.find(query))
        raise ValueError("Query must be a dictionary.")

    def update(self, query, update_data):
        """Update animal records that match the query."""
        if isinstance(query, dict) and isinstance(update_data, dict):
            result = self.collection.update_many(query, {"$set": update_data})
            return result.modified_count
        raise ValueError("Query and update data must be dictionaries.")

    def delete(self, query):
        """Delete animal records that match the query."""
        if query is not None and isinstance(query, dict):
            result = self.collection.delete_many(query)
            return result.deleted_count
        raise ValueError("Query must be a dictionary.")


def build_query(filter_type):
    """Build MongoDB queries based on selected rescue category."""

    water_breeds = [
        "Labrador Retriever Mix",
        "Chesapeake Bay Retriever",
        "Newfoundland"
    ]

    mountain_breeds = [
        "German Shepherd",
        "Alaskan Malamute",
        "Siberian Husky"
    ]

    disaster_breeds = [
        "Doberman Pinscher",
        "German Shepherd",
        "Golden Retriever"
    ]

    if filter_type == "Water Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": water_breeds},
            "sex_upon_outcome": "Intact Female",
            "age_upon_outcome_in_weeks": {"$gte": 26, "$lte": 156}
        }

    elif filter_type == "Mountain/Wilderness Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": mountain_breeds},
            "sex_upon_outcome": "Intact Male",
            "age_upon_outcome_in_weeks": {"$gte": 26, "$lte": 156}
        }

    elif filter_type == "Disaster Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": disaster_breeds},
            "sex_upon_outcome": "Intact Male",
            "age_upon_outcome_in_weeks": {"$gte": 20, "$lte": 300}
        }

    else:
        return {}

"""
Artifact: Grazioso Salvare Animal Shelter Dashboard
Category: Software Engineering and Design

Origin:
This artifact was originally created in CS 340: Client/Server Development.
It was designed as a Python Dash dashboard connected to a MongoDB database
containing Austin Animal Center shelter data. The dashboard helped users
filter animal records for rescue-training suitability and view the results
through a data table, pie chart, and geographic map.

Planned Enhancement:
The enhancement will expand the dashboard from a basic filtering application
into a rescue-animal decision-support system. The enhanced version will include
more flexible multi-criteria filtering, improved software architecture, stronger
database error handling, secure environment-based credentials, and improved
dashboard visualizations. This enhancement increases the project’s complexity
and demonstrates software engineering and design skills beyond basic debugging
or code cleanup.
"""

**B. Category Two: Algorithms and Data Structures**
**Enhancement Plan**

For the enhanced version, update the project so the bricks are no longer simple static objects. Each brick should track its own status and number of hits remaining. The ball should also have improved movement logic, including speed limits, color changes, and better collision response. This makes the project a stronger algorithms and data structures artifact because the program now uses object state, collision algorithms, condition-based updates, and structured class behavior.
Add or Update the Brick Classenum BRICKTYPE { REFLECTIVE, DESTRUCTABLE };
enum ONOFF { ON, OFF };
class Brick
{
public:
	float red, green, blue;
	float x, y, width;
	BRICKTYPE brick_type;
	ONOFF onoff;
	int hitsRemaining;
	Brick(BRICKTYPE bt, float xx, float yy, float ww, float rr, float gg, float bb)
	{
		brick_type = bt;
		x = xx;
		y = yy;
		width = ww;
		red = rr;
		green = gg;
		blue = bb;
		onoff = ON;
		if (brick_type == DESTRUCTABLE)
		{
			hitsRemaining = 2;
		}
		else
		{
			hitsRemaining = 999;
		}
	}

	void drawBrick()
	{
		if (onoff == OFF)
		{
			return;
		}
		double halfside = width / 2;
		glColor3d(red, green, blue);
		glBegin(GL_POLYGON);
		glVertex2d(x + halfside, y + halfside);
		glVertex2d(x + halfside, y - halfside);
		glVertex2d(x - halfside, y - halfside);
		glVertex2d(x - halfside, y + halfside);
		glEnd();
		// Decorative stripes to show brick structure
		glColor3d(red * 0.7, green * 0.7, blue * 0.7);
		glBegin(GL_LINES);
		glVertex2d(x - halfside, y);
		glVertex2d(x + halfside, y);
		glEnd();
	}
	void OnHit()
	{
		if (brick_type == REFLECTIVE)
		{
			return;
		}
		hitsRemaining--;
		if (hitsRemaining == 1)
		{
			// Darken the brick after first hit
			red *= 0.5f;
			green *= 0.5f;
			blue *= 0.5f;
		}
		else if (hitsRemaining <= 0)
		{
			onoff = OFF;
		}
	}
};
This version improves ball movement, collision response, speed control, and color
changes.
class Circle
{
public:
	float red, green, blue;
	float radius;
	float x;
	float y;
	float velocityX;
	float velocityY;
	Brick* lastHitBrick;

	Circle(float xx, float yy, float rr, float vx, float vy, float r, float g, float b)
	{
		x = xx;
		y = yy;
		radius = rr;
		velocityX = vx;
		velocityY = vy;
		red = r;
		green = g;
		blue = b;
		lastHitBrick = nullptr;
	}
	void DrawCircle()
	{
		glColor3f(red, green, blue);
		glBegin(GL_POLYGON);
		for (int i = 0; i < 360; i++)
		{
			float degInRad = i * 3.14159f / 180.0f;
			glVertex2f(cos(degInRad) * radius + x, sin(degInRad) * radius + y);
		}
		glEnd();
	}
	void ChangeColor()
	{
		red = static_cast<float>(rand()) / RAND_MAX;
		green = static_cast<float>(rand()) / RAND_MAX;
		blue = static_cast<float>(rand()) / RAND_MAX;
	}
	void LimitSpeed()
	{
		float maxSpeed = 0.040f;
		if (velocityX > maxSpeed) velocityX = maxSpeed;
		if (velocityX < -maxSpeed) velocityX = -maxSpeed;
		if (velocityY > maxSpeed) velocityY = maxSpeed;
		if (velocityY < -maxSpeed) velocityY = -maxSpeed;
	}
	void IncreaseSpeedSlightly()
	{
		velocityX *= 1.01f;
		velocityY *= 1.01f;
		LimitSpeed();
	}
	bool CheckCollision(Brick* brick)
	{
		if (brick->onoff == OFF)
		{
			return false;
		}
		float halfside = brick->width / 2.0f;
		float closestX = max(brick->x - halfside, min(x, brick->x + halfside));
		float closestY = max(brick->y - halfside, min(y, brick->y + halfside));
		float distanceX = x - closestX;
		float distanceY = y - closestY;

		float distanceSquared = (distanceX * distanceX) + (distanceY * distanceY);
		if (distanceSquared < radius * radius)
		{
			if (lastHitBrick == brick)
			{
				return false;
			}
			lastHitBrick = brick;
			float overlapX = radius - abs(distanceX);
			float overlapY = radius - abs(distanceY);
			if (overlapX < overlapY)
			{
				velocityX = -velocityX;
			}
			else
			{
				velocityY = -velocityY;
			}
			brick->OnHit();
			ChangeColor();
			IncreaseSpeedSlightly();
			return true;
		}
		return false;
	}
	void CheckPaddleCollision(Brick* paddle)
	{
		float halfside = paddle->width / 2.0f;
		if (x + radius > paddle->x - halfside &&
			x - radius < paddle->x + halfside &&
			y - radius < paddle->y + halfside &&
			y + radius > paddle->y - halfside)
		{
			velocityY = abs(velocityY);

			// Changes horizontal direction based on where ball hits paddle
			float hitPosition = (x - paddle->x) / halfside;
			velocityX += hitPosition * 0.008f;
			ChangeColor();
			LimitSpeed();
		}
	}
	void MoveOneStep()
	{
		x += velocityX;
		y += velocityY;
		// Left and right wall collision
		if (x + radius > 1.0f || x - radius < -1.0f)
		{
			velocityX = -velocityX;
			ChangeColor();
			IncreaseSpeedSlightly();
			lastHitBrick = nullptr;
		}
		// Top wall collision
		if (y + radius > 1.0f)
		{
			velocityY = -velocityY;
			ChangeColor();
			IncreaseSpeedSlightly();
			lastHitBrick = nullptr;
		}
		// Bottom boundary reset
		if (y - radius < -1.0f)
		{
			x = 0.0f;
			y = -0.2f;
			velocityX = 0.012f;
			velocityY = 0.014f;
			lastHitBrick = nullptr;
		}
	}
};
Add a Vector to Store Multiple Balls
vector<Circle> balls;
bool spacePressed = false;
float paddlePos = 0.0f;
#include <vector>
#include <algorithm>
#include <cmath>
#include <cstdlib>
using namespace std;
Create the Paddle
Brick paddle(REFLECTIVE, 0.0f, -0.85f, 0.35f, 0.2f, 0.8f, 1.0f);
AddBrick brick1(DESTRUCTABLE, -0.70f, 0.70f, 0.20f, 1.0f, 0.0f, 0.0f);
Brick brick2(DESTRUCTABLE, -0.40f, 0.70f, 0.20f, 0.0f, 1.0f, 0.0f);
Brick brick3(DESTRUCTABLE, -0.10f, 0.70f, 0.20f, 0.0f, 0.0f, 1.0f);
Brick brick4(DESTRUCTABLE, 0.20f, 0.70f, 0.20f, 1.0f, 1.0f, 0.0f);
Brick brick5(DESTRUCTABLE, 0.50f, 0.70f, 0.20f, 1.0f, 0.0f, 1.0f);
Brick brick6(REFLECTIVE, 0.80f, 0.70f, 0.20f, 0.8f, 0.8f, 0.8f); Brick Objects
vector<Brick*> bricks = {
	&brick1,
	&brick2,
	&brick3,
	&brick4,
	&brick5,
	&brick6
};
Initialize the First Ball
balls.push_back(Circle(0.0f, -0.2f, 0.05f, 0.012f, 0.014f, 1.0f, 1.0f, 1.0f));
Enhance Keyboard Input
void processInput(GLFWwindow* window)
{
	if (glfwGetKey(window, GLFW_KEY_ESCAPE) == GLFW_PRESS)
	{
		glfwSetWindowShouldClose(window, true);
	}

	if (glfwGetKey(window, GLFW_KEY_LEFT) == GLFW_PRESS)
	{
		paddlePos -= 0.025f;
	}
	if (glfwGetKey(window, GLFW_KEY_RIGHT) == GLFW_PRESS)
	{
		paddlePos += 0.025f;
	}
	// Keep paddle inside screen bounds
	if (paddlePos < -0.85f)
	{
		paddlePos = -0.85f;
	}
	if (paddlePos > 0.85f)
	{
		paddlePos = 0.85f;
	}

	paddle.x = paddlePos;
	// Spacebar spawns a new ball
	if (glfwGetKey(window, GLFW_KEY_SPACE) == GLFW_PRESS && !spacePressed)
	{
		float randomRed = static_cast<float>(rand()) / RAND_MAX;
		float randomGreen = static_cast<float>(rand()) / RAND_MAX;
		float randomBlue = static_cast<float>(rand()) / RAND_MAX;
		balls.push_back(Circle(0.0f, -0.2f, 0.05f, -0.012f, 0.014f, randomRed, randomGreen, randomBlue));
		spacePressed = true;
	}
	if (glfwGetKey(window, GLFW_KEY_SPACE) == GLFW_RELEASE)
	{
		spacePressed = false;
	}
}
Update the Render Loop
for (int i = 0; i < bricks.size(); i++)
{
	bricks[i]->drawBrick();
}
paddle.drawBrick();
for (int i = 0; i < balls.size(); i++)
{
	balls[i].MoveOneStep();
	balls[i].CheckPaddleCollision(&paddle);
	for (int j = 0; j < bricks.size(); j++)
	{
		balls[i].CheckCollision(bricks[j]);
	}
	balls[i].DrawCircle();
}
What This Enhancement Demonstrates
Enhancement	                        Skill Demonstrated
Multi-hit bricks	                 Object state management
Improved collision detection	     Algorithmic problem-solving
Ball speed limit	                 Control logic and performance awareness
Paddle bounce angle	               Mathematical reasoning
Vector of balls	                    Data structure usage
Brick vector	                      Dynamic object management
Classes for bricks and balls	      Object-oriented design

**C Category Three: Databases**
**Enhancement Plan**

Enhanced animal_shelter.py CRUD Module
from pymongo import MongoClient, ASCENDING
from pymongo.errors import PyMongoError
class AnimalShelterCRUD:
    """CRUD operations for the AAC animal shelter MongoDB collection."""
    def __init__(self, username, password, host="localhost", port=27017,
                 database="AAC", collection="animals"):    """
        Initializes the database connection.
        Credentials are passed in instead of hardcoded to improve security.  """
        self.client = MongoClient(
            f"mongodb://{username}:{password}@{host}:{port}/?authSource=admin"
        )
        self.database = self.client[database]
        self.collection = self.database[collection]
    def create_indexes(self):
        """
        Enhancement:
        Adds indexes to fields commonly used in dashboard filters.
        This improves query performance for repeated searches
        try:
            self.collection.create_index([("animal_type", ASCENDING)])
            self.collection.create_index([("breed", ASCENDING)])
            self.collection.create_index([("sex_upon_outcome", ASCENDING)])
            self.collection.create_index([("age_upon_outcome_in_weeks", ASCENDING)])
            self.collection.create_index([("location_lat", ASCENDING)])
            self.collection.create_index([("location_long", ASCENDING)])
            return True
        except PyMongoError as error:
            print(f"Index creation failed: {error}")
            return False
    def create(self, data):
        """
        Inserts a new document into the collection.
        """
        if data is not None and isinstance(data, dict):
            try:
                result = self.collection.insert_one(data)
                return result.acknowledged
            except PyMongoError as error:
                print(f"Create operation failed: {error}")
                return False
        return False
    def read(self, query=None, projection=None, limit=0):
        """
        Reads documents from the collection.
        Enhancement:
        Supports projection and limit so the dashboard can retrieve
        only the data it needs.
        """
        if query is None:
            query = {}
        try:
            cursor = self.collection.find(query, projection)
            if limit > 0:
                cursor = cursor.limit(limit)
            return list(cursor)
        except PyMongoError as error:
            print(f"Read operation failed: {error}")
            return []
    def update(self, query, new_values):
        """
        Updates documents matching the query.
        """
        if query is not None and new_values is not None:
            try:
                result = self.collection.update_many(
                    query,
                   {"$set": new_values}
                )
                return result.modified_count
            except PyMongoError as error:
                print(f"Update operation failed: {error}")
                return 0
        return 0
    def delete(self, query):
        """
        Deletes documents matching the query.
        """
        if query is not None:
            try:
                result = self.collection.delete_many(query)
                return result.deleted_count
            except PyMongoError as error:
                print(f"Delete operation failed: {error}")
                return 0
        return 0
    def build_rescue_query(self, rescue_type):
        """
        Enhancement Filter Function for Dashboard
        Builds reusable MongoDB queries for each rescue category.
        This keeps database filtering organized and easier to maintain. ""
        water_breeds = [
            "Labrador Retriever Mix",
            "Chesapeake Bay Retriever",
            "Newfoundland"
        ]
        mountain_breeds = [
            "German Shepherd",
            "Alaskan Malamute",
            "Old English Sheepdog",
            "Siberian Husky",
            "Rottweiler"
        ]
        disaster_breeds = [
            "Doberman Pinscher",
            "German Shepherd",
            "Golden Retriever",
            "Bloodhound",
            "Rottweiler"
        ]
        if rescue_type == "Water Rescue":
            return {
                "animal_type": "Dog",
                "breed": {"$in": water_breeds},
                "sex_upon_outcome": "Intact Female",
                "age_upon_outcome_in_weeks": {
                    "$gte": 26,
                    "$lte": 156
                }
            }

        elif rescue_type == "Mountain/Wilderness Rescue":
            return {
                "animal_type": "Dog",
                "breed": {"$in": mountain_breeds},
                "sex_upon_outcome": "Intact Male",
                "age_upon_outcome_in_weeks": {
                    "$gte": 26,
                    "$lte": 156
                }
            }
        elif rescue_type == "Disaster Rescue":
            return {
                "animal_type": "Dog",
                "breed": {"$in": disaster_breeds},
                "sex_upon_outcome": "Intact Male",
                "age_upon_outcome_in_weeks": {
                    "$gte": 20,
                    "$lte": 300
                }
            }

        else:
            return {}
    def read_by_rescue_type(self, rescue_type):
        """
        Enhancement:
        Reads animals using rescue-category filter logic.
        """
        query = self.build_rescue_query(rescue_type)
        return self.read(query)
Enhanc def build_query(filter_type):
    """
    Builds MongoDB query based on selected rescue filter.
    """
    water_breeds = [
        "Labrador Retriever Mix",
        "Chesapeake Bay Retriever",
        "Newfoundland"
    ]
    mountain_breeds = [
        "German Shepherd",
        "Alaskan Malamute",
        "Old English Sheepdog",
        "Siberian Husky",
        "Rottweiler"
    ]
    disaster_breeds = [
        "Doberman Pinscher",
        "German Shepherd",
        "Golden Retriever",
        "Bloodhound",
        "Rottweiler"
    ]
    if filter_type == "Water Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": water_breeds},
            "sex_upon_outcome": "Intact Female",
            "age_upon_outcome_in_weeks": {
                "$gte": 26,
                "$lte": 156
            }
        }
    elif filter_type == "Mountain/Wilderness Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": mountain_breeds},
            "sex_upon_outcome": "Intact Male",
            "age_upon_outcome_in_weeks": {
                "$gte": 26,
                "$lte": 156
            }
        }
    elif filter_type == "Disaster Rescue":
        return {
            "animal_type": "Dog",
            "breed": {"$in": disaster_breeds},
            "sex_upon_outcome": "Intact Male",
            "age_upon_outcome_in_weeks": {
                "$gte": 20,
                "$lte": 300
            }
        }
    else:
        return {}
Enhanced Dashboard Callback
@app.callback(
    Output("datatable-id", "data"),
    [Input("filter-type", "value")]
)
def update_dashboard(filter_type):
    """
    Enhancement:
    Uses structured query-building logic to retrieve filtered records.
    """
    query = build_query(filter_type)
    data = shelter.read(query)
    df = pd.DataFrame.from_records(data)
    if "_id" in df.columns:
        df.drop(columns=["_id"], inplace=True)
    return df.to_dict("records")
Optional Enhancement: Add a Search Filter
def build_search_query(search_text):
    """
    Enhancement:
    Builds a search query for breed or animal name.
    """
    if search_text is None or search_text.strip() == "":
        return {}
    return {
        "$or": [
            {"breed": {"$regex": search_text, "$options": "i"}},
            {"name": {"$regex": search_text, "$options": "i"}}
        ]
    } def combine_queries(rescue_query, search_query):
    """
    Combines rescue filters and search filters.
    """
    if rescue_query and search_query:
        return {
            "$and": [
                rescue_query,
                search_query
            ]
        }
    if rescue_query:
        return rescue_query
    if search_query:
        return search_query
    return {}
What Makes This an Enhancement?
You can say your database enhancement includes:
Enhancement Code	                            What It Shows
create_indexes()	                            Database performance improvement
build_rescue_query()	                        Organized query design
read_by_rescue_type()	                        Reusable database access
Improved read() method	                        Better data retrieval control
Error handling with PyMongoError	            More reliable database operations
Removed hardcoded credentials from class	    Better security mindset
Optional search query	                        More useful database filtering


