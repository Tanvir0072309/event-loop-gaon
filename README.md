# 🌾 Event Loop Gaon — JavaScript Event Loop Visualizer

<p align="center">
  <strong>Where JavaScript Execution Comes to Life!</strong>
  <br/>
  An interactive 3D village that turns JavaScript's Event Loop into a visual experience.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/JavaScript-ES6%2B-yellow?logo=javascript" />
  <img src="https://img.shields.io/badge/Three.js-r128-black?logo=threedotjs" />
  <img src="https://img.shields.io/badge/Acorn-8.11.3-orange" />
  <img src="https://img.shields.io/badge/Status-Experimental-orange" />
</p>

---

## 🎮 Live Demo

👉 **[Launch Event Loop Gaon](https://event-loop-gaon-6go8.vercel.app/)**

## 🌄 Project Preview

<p align="center">
  <img src="https://res.cloudinary.com/dat8orrws/image/upload/v1793698944/Screenshot_From_2026-11-03_15-09-57.png" alt="Event Loop Gaon - Interactive 3D JavaScript Event Loop Visualizer" width="100%" />
</p>

<p align="center">
  <i>A living 3D village where every JavaScript callback has a destination!</i>
</p>

---

## 🚀 What is Event Loop Gaon?

**Event Loop Gaon** is an interactive 3D JavaScript Event Loop visualizer where asynchronous JavaScript execution is represented through a living village.

Instead of staring at abstract diagrams, you can write your own JavaScript code and watch **Chintu**, the village's little explorer, demonstrate how JavaScript executes your code.

Every function call, timer, Promise callback, and asynchronous operation becomes a visual event inside the village.

**Understand JavaScript's Event Loop by watching it happen.**

## 🏡 The Village — JavaScript Architecture

| Village Element | JavaScript Concept | What It Represents |
|---|---|---|
| 🏠 Blue Tower | Call Stack | Currently executing functions |
| ☕ Yellow Café | Web APIs | Timer operations and waiting |
| 📮 Pink Post Office | Task Queue | Macrotasks such as `setTimeout` |
| ⭐ Golden VIP House | Microtask Queue | Promise callbacks and `await` continuations |
| 🧑 Chintu | Event Loop | Coordinates execution flow |
| 📦 Parcels | Scheduled Tasks | Callbacks waiting to execute |

### How the visualization works

1. JavaScript code starts executing.
2. Function calls enter the Call Stack.
3. Timer operations are delegated to the simulated Web APIs.
4. Completed timer callbacks enter the Task Queue.
5. Promise callbacks enter the Microtask Queue.
6. Once the Call Stack is empty, the Event Loop processes pending microtasks before the next task.
7. Chintu travels through the village to visualize each execution step.

## ✨ Features

### 🧠 Interactive JavaScript Execution

- Write and execute your own JavaScript code.
- Visualize actual execution order.
- Watch function calls enter and leave the Call Stack.
- Track `console.log()` operations.
- Explore synchronous and asynchronous execution.
- Understand Promise and timer scheduling.

### 🌳 Immersive 3D Village

- Fully interactive Three.js environment.
- Procedurally generated textures using Canvas.
- Four uniquely designed village houses.
- Trees, forests, farms, fences, ponds, and wells.
- Windmill, hot-air balloon, and village decorations.
- Animated chickens, sheep, birds, butterflies, and fireflies.
- Village family members who react to Chintu.

### 🌦️ Dynamic Environment

- Day and night cycles.
- Rain, lightning, and thunder.
- Animated clouds and atmospheric effects.
- Fireworks and confetti.
- Procedural sound effects using Web Audio API.

### 🎥 Camera & Exploration

- Interactive camera controls.
- Follow Chintu mode.
- Free village exploration.
- Zoom, rotate, and pan.
- Automatic movement mode.

### ⚙️ Execution Controls

- Visualize: Execute JavaScript code.
- Edit Code: Modify your program.
- Next: Advance one execution step.
- Auto: Automatically play the execution sequence.
- Reset: Restart the visualization.
- Example: Load sample JavaScript programs.
- Code: Toggle the code editor.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| JavaScript (ES6+) | Application logic and simulator |
| Three.js r128 | 3D rendering and animations |
| Acorn 8.11.3 | JavaScript parsing and AST instrumentation |
| HTML5 | Application structure |
| CSS3 | UI styling |
| Canvas API | Procedural textures |
| Web Audio API | Procedural sound effects |

### External Dependencies

- [Three.js](https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js)
- [Acorn](https://cdn.jsdelivr.net/npm/acorn@8.11.3/dist/acorn.js)

## 🏗️ How It Works Internally

Event Loop Gaon uses a custom JavaScript execution simulator to transform code execution into visual events.

### 1. JavaScript Parsing

Acorn parses the user's JavaScript source code into an Abstract Syntax Tree (AST).

### 2. AST Instrumentation

The simulator instruments relevant execution points with hooks to track:

- Function entry and exit.
- Console logging.
- Timer scheduling.
- Promise callbacks.
- Async/await continuations.
- Loop execution.

### 3. Instrumented Execution

The instrumented program executes using custom implementations of selected JavaScript APIs.

These implementations record execution events such as:

- `push`
- `pop`
- `log`
- `timer`
- `sched`
- `run`

### 4. Task Scheduling

The simulator uses the browser's native Promise microtask mechanism for microtask execution and a simulated clock for timer operations.

This allows timer-based examples to run without waiting for their actual durations.

### 5. Visual Event Generation

Recorded execution events are converted into individual visualization steps.

Each step contains:

- Execution event.
- Village destination.
- Character movement.
- Parcel animation.
- Hinglish explanation.

## 💻 Getting Started

### Prerequisites

- A modern web browser.
- Internet connection for external CDN dependencies.
- No Node.js installation or build process required.

### Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/event-loop-gaon.git
```

Navigate into the project:

```bash
cd event-loop-gaon
```

Open `event-loop-gaon.html` in your browser.

Alternatively, start a local development server:

```bash
python -m http.server 5500
```

Open:

```text
http://localhost:5500/event-loop-gaon.html
```

## 🧪 Try It Yourself

Paste this JavaScript program into the editor:

```javascript
console.log("Start");

setTimeout(() => {
    console.log("Timeout callback");
}, 0);

Promise.resolve().then(() => {
    console.log("Promise callback");
});

console.log("End");
```

Expected output:

```text
Start
End
Promise callback
Timeout callback
```

Watch Chintu travel between the village buildings as the execution progresses!

## ⚠️ Current Limitations

This project is an experimental educational simulator, not a complete JavaScript runtime.

- `fetch()` is not supported.
- `requestAnimationFrame()` is not supported.
- `process.nextTick()` is not supported.
- Some rejected Promise and `await` scenarios may not be visualized accurately.
- Internal Promise operations such as those used by `Promise.all()` and `finally()` can produce additional visualization events.
- Execution is limited to 200,000 loop iterations.
- Execution traces are limited to 700 events.
- Maximum 40 timers are supported.
- `setInterval()` is simulated for up to four iterations.
- Mobile performance may be limited by 3D rendering and shadows.

**Security note:** User-provided JavaScript runs in the browser. This project does not currently provide a hardened sandbox for executing untrusted code. Avoid pasting code from unknown sources.

## 🗺️ Roadmap

- [ ] Improve Promise rejection and `await` visualization.
- [ ] Add `fetch()` simulation.
- [ ] Add code editor line numbers.
- [ ] Implement syntax highlighting and error highlighting.
- [ ] Add execution speed controls.
- [ ] Improve mobile rendering performance.
- [ ] Expand JavaScript API coverage.
- [ ] Add more interactive village animations.
- [ ] Improve execution trace debugging.

## 🎯 Learning Objectives

- JavaScript Runtime Environment.
- Call Stack and Execution Context.
- Synchronous vs Asynchronous JavaScript.
- Web APIs.
- Event Loop.
- Task Queue and Microtask Queue.
- Promises and Async/Await.
- AST Parsing and Code Instrumentation.
- Three.js and Real-time 3D Rendering.

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome!

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Push your branch.
5. Open a Pull Request.

## 👨‍💻 Author

**Tanvir Pathan**

BCA (Honors) Software Engineering Student | Full Stack Developer

- GitHub: [@Tanvir0072309](https://github.com/Tanvir0072309)

---

<p align="center">
  <strong>🌾 Welcome to Event Loop Gaon!</strong>
  <br/>
  <i>Where every callback has a destination, every Promise has a home, and Chintu keeps JavaScript running.</i>
</p>

<p align="center">
  ⭐ If you find this project interesting, consider giving it a star!
</p>
