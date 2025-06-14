# Rock-Paper-Scissors-Game-using-MobileNetV2-Gradio-GUI
This project allows users to play Rock-Paper-Scissors with an AI opponent in real-time. A **trained CNN model (MobileNetV2)** classifies your hand gesture from webcam input, and the AI responds with its move. The result is shown live on a **Gradio GUI interface**

# 🤖 Rock-Paper-Scissors Game using MobileNetV2 + Gradio GUI

Welcome to the **Rock-Paper-Scissors (RPS) Game powered by Deep Learning**!  
This project uses **transfer learning** with **MobileNetV2** to classify hand gestures (rock, paper, or scissors) and lets you play a live game using your **webcam via Gradio**.

---

## 📌 Project Title

**"RPS Vision Showdown: A Deep Learning-Based Gesture Recognition Game with Transfer Learning and GUI Integration"**

---

## 🎯 Project Description

This project allows users to play Rock-Paper-Scissors with an AI opponent in real-time. A **trained CNN model (MobileNetV2)** classifies your hand gesture from webcam input, and the AI responds with its move. The result is shown live on a **Gradio GUI interface**.

---

## 🔍 How It Works

- The model classifies an uploaded or webcam image of a hand as **rock**, **paper**, or **scissors**
- The AI randomly selects its own move
- The winner is determined and displayed instantly

---

## 🧠 Techniques & Models Used

| Technique | Description |
|----------|-------------|
| 🧠 Transfer Learning | Used `MobileNetV2` pre-trained on ImageNet and fine-tuned on RPS dataset |
| 🧪 Image Augmentation | Applied `ImageDataGenerator` to improve model robustness |
| 📊 Evaluation Metrics | Accuracy, Loss, and Validation Accuracy over 25 epochs |
| 🎮 GUI Framework | Built with `Gradio` in Google Colab for user interaction |
| 🖼️ Real-Time Prediction | Accepts webcam or uploaded image input |
| 🔄 AI Logic | AI's move is generated randomly (can be upgraded to pattern-based later) |

---

## 🛠️ Tech Stack

- Python
- TensorFlow / Keras
- Gradio
- OpenCV (optional, for local image handling)
- Google Colab

---

## 💬 Challenges & Clarifications (Your Doubts Solved)

| Doubt | Clarification |
|-------|---------------|
| ⚠️ Continuous Execution of GUI | Caused by Gradio `.launch()` running in Colab — fixed with correct interface handling |
| 😵 AI Move Source? | AI's move is **random**, not from a model. Your DL model only predicts **your move** |
| 🚫 Grad-CAM Heatmaps | Skipped by choice as you preferred GUI over explainability features |
| ❌ Gradio Errors | `"source"` and `"tool"` arguments caused errors — resolved using latest Gradio syntax |
| 📸 Webcam Not Working | `gr.Camera` was removed in new versions — used `gr.Image` with webcam input instead |
| 🔥 model.compile_metrics warning | Harmless warning — model loads for inference, so no metrics needed |
| ❓AI doesn't predict its move? | Yes — AI is randomly choosing `rock/paper/scissors`, not using ML |

---

## 🖥️ Game Logic

```python
# Random AI move
ai_move = random.choice(['rock', 'paper', 'scissors'])

# Determine winner
if player_move == ai_move:
    result = "It's a draw!"
elif (player_move == "rock" and ai_move == "scissors") or \
     (player_move == "scissors" and ai_move == "paper") or \
     (player_move == "paper" and ai_move == "rock"):
    result = "You win! 🎉"
else:
    result = "AI wins! 🤖"
```

## 🚀 How to Run

- Open the notebook in Google Colab
- Train the model or upload mobilenetv2_rps.h5 if already trained
- Run the Gradio interface block
- Show your hand sign to webcam or upload image
- Click “Play!” and see the result 🎮

## 🙌 Credits
- Made with ❤️ by **Leekhith Nunna**
- Special thanks to TensorFlow, Keras, and Gradio devs!
