# HTandel993.github.io
<!DOCTYPE html>
<html lang="en">
<title> My Basic Portfolio </title>

<style>
    /* 1. GENERAL STYLES */
    body {
        font-family: Arial, sans-serif;
        background-color: #d69dfc;
        color: #3c0c0c;
        margin: 0;
        padding: 0;
    }
    /* 2. HEADER STYLES */
    header {
        background-color: #5b43c4;
        color: white;
        text-align: center;
        padding: 40px 20px;
    }

    header h1{
        margin: 0;
        font-size: 36px;
    }

    header p {
        margin-top: 10px;
        font-size: 18px;
        color: #eacbff;
    }

    /* 3. MAIN CONTENT STYLES*/

    main{
        padding: 40px 20px;
        max-width: 1000px;
        margin: 0 auto;
    }

    /* 4. FLEXBOX CONTAINER FOR CARDS*/
    #skills-container {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
        justify-content: center;
    }

     /* 5. INDIVIDUAL CARD STYLES */
        /* These rules will apply to the divs we create with JavaScript */
        .skill-card {
            position: relative;
            background-color: white;
            border-radius: 8px; /* Rounds the corners of the cards */
            padding: 20px;
            width: 250px; /* Gives each card a fixed width */
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Adds a soft drop shadow behind the card */
            text-align: center;
            border-top: 5px solid #3498db; /* Adds a nice blue line at the top of each card */
        }

        .toggle-icon {
            position: absolute;
            top: 14px;
            right: 16px;
            font-size: 1.25rem;
            font-weight: bold;
            color: #64748b;
            line-height: 1; /* Prevents unwanted vertical spacing */
        }

        .skill-card h3 {
            margin-top: 0;
            color: #2c3e50;
        }

        .skill-card p {
            font-size: 14px;
            color: #666666;
            line-height: 1.5; /* Adds a bit of space between lines of text */
        }

        .skill-card.selected {
            border: 2px solid #2563eb;
            background-color: #f0f7ff;
            transform: scale(1.03);
        }
    


    </style>
<head>
    <metas charset="UTF-8">
    <meta name="viewport" content="width = device-width, initial-scale= 1.0">
    <title>Doctument</title>
</head>

<body>

    <header>
        <h1 style="text-align: center; margin-bottom: 30px; ">Hashe</h1>
        <p style="text-align: center; margin-bottom: 30px; "> A beginner web developer learning to code</p>
    </header>

    <main>
        <h2 style="text-align: center; margin-bottom: 30px; ">My Skills</h2>
        <!-- JavaScript will add the cards here later -->
         <div id="skills-container">
         </div>
         <p>
    </main>

    <script>
    // java script goes here
    //making an array below - defining data
    const mySkills =[
        {
            name:  "HTML",
            description: "The building blocks of the web. I use this to structure my websites. "
        },
        {
            name: "CSS",
            description: "The styling language. I use this to add colours, layouts, and make things look pretty. "
        },
        {
            name: "JavaScript",
            description: "The brain of the website. I am learning to make my websites interactive. "
        },
        {
            name: "problem Solving",
            description: "Breaking down complex problems into smaller, manageable steps. "
        },
        {
            name: "Teamwork",
            description: "Being able to work effectively as part of a team. "
        },
        {
            name: "Time-Management",
            description: "Knowing how to prioritise tasks to work to a deadline and meet goals. "
        }
        ];

    //find the container
    const container = 
        document.getElementById("skills-container");

    //loop through data and create cards
        mySkills.forEach(function(skills) {
            //a) create an empty <div>
            const cardElement = document.createElement("div");

            //b) give it the class our CSS styles
            cardElement.className = "skill-card";
    
            //c) put HTML inside the card
            cardElement.innerHTML = `
            <span class = "toggle-icon">+</span>
            <h3>${skills.name}</h3>
            `;
            //d) inside the loop - the description, hidden at first const details = document.createElement('p');
            const details = document.createElement('p');
            details.textContent = skills.description;
            details.style.display = 'none';

            cardElement.appendChild(details);

            //f) react to a click
            cardElement.addEventListener('click', function() {
                // the click goes here
                const icon = cardElement.querySelector(' .toggle-icon');
                const isHidden = details.style.display === 'none';
                details.style.display = isHidden ? 'block': 'none';
                cardElement.classList.toggle('selected');
                if (isHidden) {
                    details.style.display = 'block';
                    icon.textContent = '-';
                }  else {
                    details.style.display = 'none';
                    icon.textContent = '+';
                }
            });

            //e) puts card on page
            container.appendChild(cardElement);

        });


    
    </script>

<footer>
    <p>&copy; 2026 My Website - built with HTML, CSS, and JavaScript, by Hashe. All Rights Reserved.</p>
</footer>




</body>
</html>
