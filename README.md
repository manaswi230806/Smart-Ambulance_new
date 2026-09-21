1) Unzip Smart-Ambulance-v2.zip somewhere convenient, e.g. your Downloads folder. You'll get a Smart-Ambulance-main folder.
2)Open a terminal in that folder. In File Explorer, navigate into Smart-Ambulance-main, click the address bar, type cmd, and press Enter — that opens Command Prompt already inside the folder.
3)Create a virtual environment (skip this if you already have a venv folder in there from before):
  python -m venv venv
4)Activate it:
  venv\Scripts\activate
  Your prompt should now start with (venv).
5)Install the dependencies:
  python -m pip install -r requirements.txt
  (Use python -m pip, not plain pip, since your machine's Device Guard policy blocks pip.exe directly.)
6)Get your own OpenRouteService key (optional but recommended): the key baked into app.py is dead. Sign up free at openrouteservice.org, then open app.py and replace the ORS_API_KEY value near the top. Without this, everything still works — you just won't see the route line drawn on the driver's map.
7)Run the server:
  python app.py
  Leave this terminal window open — it's running your server.
8)Open it in your browser:
  http://127.0.0.1:5000/ — the patient page (request an ambulance)
  http://127.0.0.1:5000/driver — the driver dashboard, open in a second tab
9)Try it end to end: on the patient tab, allow location access (or click the map to set one) and hit "Request ambulance." Switch to the driver tab, click Accept, and step through the status buttons — you should see the step tracker update on both tabs.
10)To stop the server later, go back to the terminal and press Ctrl+C.
