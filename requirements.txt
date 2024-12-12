import os
from flask import Flask
from datetime import datetime

app = Flask(__name__)

@app.route("/")
def show_date():
    today_date = datetime.now().strftime("%Y-%m-%d")
    return f"<h1>Today's Date: {today_date}</h1>"

if __name__ == "__main__":
    port = int(os.environ.get("PORT", 5000))
    app.run(host="0.0.0.0", port=port)
