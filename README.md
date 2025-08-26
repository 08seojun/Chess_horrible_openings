# Chess_horrible_openings
가장 역겨운 체스 오프닝 대회
chess_horrible_openings/
├─ app.py
├─ templates/
├─ static/
└─ db.sqlite (초기 데이터가 필요하면 포함)
from flask import Flask, render_template, request

app = Flask(__name__)

posts = []

@app.route('/', methods=['GET', 'POST'])
def index():
    if request.method == 'POST':
        post = request.form['post']
        posts.append(post)
    return render_template('index.html', posts=posts)

if __name__ == '__main__':
    app.run(debug=True)
