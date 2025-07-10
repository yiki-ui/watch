Xabi Agent - AI Receptionist Platform

An AI Receptionist, Built For You.

Xabi Agent is a full-stack web application that allows users to create, train, and deploy custom AI agents for their businesses. These agents can handle customer inquiries via a chat widget, answer questions based on a provided knowledge base, and even take appointment bookings 24/7.

The platform features a sleek, modern landing page to attract clients and a secure, multi-tenant dashboard for registered users to manage their AI agents.

![alt text](https://i.ibb.co/Lp2p7sX/xabi-landing.png)


![alt text](https://i.ibb.co/n6zR70t/xabi-dashboard.png)

✨ Key Features
User-Facing & Public Features:

    Interactive Landing Page: A modern, responsive, and animated single-page design to showcase the service.

    Live AI Chat Widget: A persistent chat bubble allows visitors to interact with a demo or a client-specific AI agent.

    Real-time Communication: Utilizes WebSockets for instant, bi-directional chat communication.

    One-Time Setup Model: A clear pricing and service model offering a lifetime agent for a one-time fee.

    Contact & Feedback Forms: Integrated forms for service requests and general feedback.

Client Dashboard Features:

    Secure Authentication: JWT-based user registration and login system.

    Knowledge Base Management:

        Text-based: Clients can paste their core business information (services, hours, location, etc.) into a large text area for the AI to learn from.

        File-based: Clients can upload .txt and .pdf documents (e.g., menus, price lists, detailed FAQs) to expand the AI's knowledge.

    AI Personalization: Users can customize their agent's tone (professional, friendly, casual), default response length, and primary language.

    Live Activity Feed: See a real-time feed of interactions and summaries of conversations your agent has had with customers.

    Embeddable Widget: Automatically generates an <iframe> code snippet for clients to easily embed their personalized chat agent on their own websites.

    Account Management: Users can view their plan status and deactivate their account.

🛠️ Tech Stack

This project is a full-stack application built with modern technologies.

    Frontend:

        HTML5

        Tailwind CSS: For rapid, utility-first styling.

        Vanilla JavaScript: For all client-side logic, interactivity, and API communication. No frontend frameworks needed.

        Font Awesome: For icons.

        Google Fonts: For the 'Inter' typeface.

    Backend:

        Python 3.x

        FastAPI: For creating a high-performance, asynchronous RESTful API.

        WebSockets: For the real-time chat functionality.

        JWT (JSON Web Tokens): For secure user authentication and authorization.

        SQLAlchemy: As the ORM for database interactions.

        Pydantic: For data validation and settings management.

    Database:

        PostgreSQL (or any other SQLAlchemy-compatible database like SQLite for development).

    Deployment & Services:

        Vercel / Render: Ideal platforms for deploying the FastAPI backend.

        Supabase: Provides a hosted PostgreSQL database and authentication services.

        Formspree: Used for the "Send a Message" contact form on the landing page.

🚀 Getting Started

To get a local copy up and running, follow these simple steps.
Prerequisites

    Python 3.8+

    A code editor (e.g., VS Code)

    A PostgreSQL database (or you can modify the code to use SQLite for simple testing)

Backend Setup

    Clone the repository:
    Generated bash

          
    git clone https://github.com/your-username/xabi-agent.git
    cd xabi-agent

        

    IGNORE_WHEN_COPYING_START

Use code with caution. Bash
IGNORE_WHEN_COPYING_END

Create a virtual environment:
Generated bash

      
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END

Install dependencies (assuming a requirements.txt file exists in the backend directory):
Generated bash

      
pip install -r requirements.txt

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END

Set up environment variables:
Create a .env file in the root of the backend directory and populate it with your configuration details. Use .env.example as a template:
Generated ini

      
# .env.example
DATABASE_URL="postgresql://user:password@host:port/dbname"
SECRET_KEY="your_super_secret_key_for_jwt"
ALGORITHM="HS256"
ACCESS_TOKEN_EXPIRE_MINUTES=43200 # 30 days

# API Keys for AI and other services
AI_PROVIDER_API_KEY="sk-..."
FORMSPREE_ENDPOINT="https://formspree.io/f/YOUR_CODE"

    

IGNORE_WHEN_COPYING_START
Use code with caution. Ini
IGNORE_WHEN_COPYING_END

Run the database migrations (if using a tool like Alembic):
Generated bash

      
alembic upgrade head

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END

Start the backend server:
Generated bash

      
uvicorn main:app --reload

    

IGNORE_WHEN_COPYING_START

    Use code with caution. Bash
    IGNORE_WHEN_COPYING_END

    The backend API will now be running, typically on http://127.0.0.1:8000.

Frontend Setup

    Update the API URL:
    Open the index.html file and find the API_BASE_URL constant in the <script> tag. Change it to your local backend URL:
    Generated javascript

          
    const API_BASE_URL = 'http://127.0.0.1:8000';

        

    IGNORE_WHEN_COPYING_START

    Use code with caution. JavaScript
    IGNORE_WHEN_COPYING_END

    Open the file in your browser:
    Simply open the index.html file in a modern web browser. All frontend assets are loaded from CDNs, so no build step is required.

💡 How It Works

    Trial Signup: A new user signs up for a 14-day trial. Their details are stored in the database, and they are given a "trial" subscription tier.

    Dashboard Access: The user logs in and receives a JWT access token, which is stored in localStorage. This token is used to authenticate all future API requests.

    AI Training:

        In the Knowledge Base tab, the user provides their business information. This text is saved to their user profile in the database.

        The user can also upload .txt or .pdf files. These files are stored, and their content is vectorized and saved in a vector database (like PGvector) for efficient searching.

    Chat Interaction:

        When a customer (or the client testing) uses the chat widget, a WebSocket connection is established.

        The user's query is sent to the backend.

        The backend retrieves the client's business knowledge (text and file-based) and uses it to create a context-rich prompt for a large language model (LLM).

        The LLM's response is streamed back to the user in real-time.

    Embedding: The user copies the <iframe> snippet from the Embed Agent tab and pastes it into their own website's HTML to make the chat widget publicly available.

📞 Contact

Chris - prodyiki@gmail.com
