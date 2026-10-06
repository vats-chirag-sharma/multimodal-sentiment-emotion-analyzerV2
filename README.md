# EmotionAI — Multimodal Sentiment & Emotion Analyzer

A browser-based multimodal demo combining:

- Live facial-expression estimation with face-api.js
- 3-class text sentiment: Positive / Neutral / Negative
- Clause-Level Sentiment Conflict Score
- Qualitative text-face comparison: Consistent / Mismatch / Ambiguous

## Deployment

This project is static and can be deployed directly to Vercel.

Required files in the repository root:

- `index.html`
- `text_model.json`

No Python server, Streamlit app, TensorFlow backend, WebRTC relay, API key, or payment method is required.

## Text model

`text_model.json` is an exported form of the supplied scikit-learn:
- `TfidfVectorizer` with unigram + bigram features, sublinear TF and L2 normalization
- `LogisticRegression` classifier

The browser implementation reproduces the same TF-IDF and softmax inference logic for the supplied model.

## Facial model

The existing camera implementation is preserved and uses face-api.js in the browser for:
Happy, Sad, Angry, Fearful, Disgusted, Surprised and Neutral.

Facial-expression output estimates visible expression patterns only and should not be treated as proof of a person's true internal emotion, intent, or honesty.

## Privacy

Camera frames remain in the browser. Text inference also runs in the browser using the local `text_model.json` file.
