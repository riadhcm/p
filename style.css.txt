/* General body styling */
body {
  font-family: 'Arial', sans-serif;
  background-color: #000000; /* Black background */
  color: #ffffff; /* White text for contrast */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

/* Main container */
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #000000; /* Black background */
  padding: 20px;
  border-radius: 20px;
  box-shadow: 0 4px 10px rgba(255, 255, 255, 0.5); /* White shadow */
  text-align: center;
}

/* Timer display */
#timer-display {
  font-size: 72px;
  margin: 20px 0;
  font-weight: bold;
  color: #ffffff; /* White text */
}

/* Buttons styling */
button {
  background-color: #000000; /* Black background */
  color: #ffffff; /* White text */
  border: 2px solid #ffffff; /* White border */
  padding: 10px 25px;
  margin: 10px;
  border-radius: 25px;
  cursor: pointer;
  font-size: 18px;
}

button:hover {
  background-color: #333333; /* Darker shade of black */
}

/* Break buttons specific styling */
#break-options button {
  background-color: #000000; /* Black background */
}

#break-options button:hover {
  background-color: #333333; /* Darker shade */
}

/* Break options styling */
#break-options {
  display: flex;
  gap: 10px;
  margin-top: 20px;
}

/* Start and Reset buttons container */
#buttons {
  display: flex;
  gap: 20px;
  margin-top: 10px;
}
