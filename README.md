# de-vecchis-neuronal-verse
Asistente cognitivo personalizado que potencia la mente humana mediante IA
git clone https://github.com/Carlo-De-Vecchi/de-vecchis-verse-neuronal.git
cd de-vecchis-verse-neuronal
git add neuroverse_mvp.py
git commit -m "Agregar MVP inicial de De Vecchi’s Verse Neuronal"
git push origin main
python3 -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install Flask
from flask import Flask, jsonify, request
from flask_cors import CORS

app = Flask(__name__)
CORS(app)

@app.route('/analyze', methods=['POST'])
def analyze():
    data = request.get_json()
    input_text = data.get('text', '')
    # Lógica de análisis aquí
    response = {
        'response': f"Análisis de '{input_text}': Esta es una respuesta simulada."
    }
    return jsonify(response)

if __name__ == '__main__':
    app.run(debug=True)
    python app.py
    npx create-react-app frontend
cd frontend
npm install axios
import React, { useState } from 'react';
import axios from 'axios';

function App() {
  const [input, setInput] = useState('');
  const [response, setResponse] = useState('');

  const handleSubmit = async () => {
    const res = await axios.post('http://localhost:5000/analyze', { text: input });
    setResponse(res.data.response);
  };

  return (
    <div>
      <h1>De Vecchi’s Neuronal Versel</h1>
      <input value={input} onChange={(e) => setInput(e.target.value)} />
      <button onClick={handleSubmit}>Analizar</button>
      <p>{response}</p>
    </div>
  );
}

export default App;
npm start
