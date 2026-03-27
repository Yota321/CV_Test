# ✦ Interactive CV — Learning Animation & System Thinking

## 🧭 Overview

This project started from a simple curiosity.

I came across a YouTube video that demonstrated scroll-based animations and dynamic UI transitions. At first, it felt complex, almost like something reserved for high-end portfolio sites. But after watching it closely, I realised something important.

It wasn’t magic.

It was structure, state, and timing.

So instead of just watching, I decided to rebuild the idea in my own way.

This CV is not just a resume. It is a learning experiment where I explored how animation systems actually work, and how interaction design shapes perception.

🔗 Live Project:  
https://yota321.github.io/CV_Test/

---

## 🎥 Learning Source

Inspired by this video:  
https://youtu.be/4yBxb5RQxPs

But I didn’t copy the code directly.

Instead, I focused on understanding:
- how scroll input is handled  
- how sections transition  
- how animation states are controlled  
- how UI elements stay in sync  

Then I rebuilt everything from scratch in my own structure and design language.

---

## 🧠 My Approach (Thinking Process)

At first glance, the animation feels continuous.

But while building it, I realised something interesting.

It’s not continuous. It’s a sequence of controlled state changes.

So I broke everything down.

---

### 1. Sections as States

Instead of thinking:

> scroll = movement

I reframed it as:

> scroll = change of state

Each section (About, Experience, Projects, etc.) is treated as a separate state.

---

### 2. Two Systems Working Together

The layout is built using two independent but synchronized systems.

#### ◼ Left Panel
- Functions like a flipping book
- Uses `rotateX()` for vertical transitions
- Only one section is visible at a time

#### ◼ Right Panel (Card Deck)
- Functions as a stacked card system
- Uses `translate`, `scale`, and `rotate`
- Multiple cards create depth and hierarchy

Separating these systems made the logic much cleaner.

---

### 3. Animation = State + Transition

I stopped thinking of animation as motion.

Instead:

> animation = state change + timing

Example:

```css
.state-active
.state-next
.state-prev

transition: transform 0.65s cubic-bezier(...)
```

The illusion of motion comes from switching between these states.

---

### 4. Scroll Handling

Scroll is not used for normal page movement.

Instead:
- Default scrolling is disabled
- Wheel input is captured
- Delta values are accumulated
- Transitions trigger after a threshold

So effectively:

> scroll → interpreted → converted into navigation

---

### 5. Card Deck Logic

Each card has a relative position:

- `active`
- `peek-1`
- `peek-2`
- `hidden`
- `gone`

This creates a layered depth effect without complex 3D rendering.

---

### 6. System Thinking

This was probably the biggest shift for me.

I stopped designing individual screens.

Instead, I designed:
- rules
- states
- relationships

For example:
- any card can become active  
- any section can be entered or exited  
- animations are reusable, not hardcoded  

This makes the system scalable and consistent.

---

## ⚙️ Features

- Scroll-driven navigation (no default page scroll)
- 3D-like vertical panel flip animation
- Card stack with depth illusion
- Keyboard navigation support
- Mobile swipe interaction
- State-based animation system

---

## 📚 What I Learned

### 1. Animation is Logic, Not Decoration

Earlier, I treated animation as something you add later.

Now it feels like:

> animation is part of the structure

---

### 2. Breaking Complex UI into Systems

Complex interactions become manageable when broken into:
- states  
- transitions  
- triggers  

---

### 3. Small Details Matter

Subtle elements like:
- easing curves  
- timing  
- opacity  

They significantly affect how polished the experience feels.

---

### 4. Learning by Rebuilding

Watching gives understanding.

Rebuilding gives control.

---

## 🚧 Future Improvements

- Improve scroll smoothing (especially trackpads)
- Add accessibility support (reduced motion, focus states)
- Optimize performance for low-end devices
- Expand into a reusable portfolio template
- Add micro-interactions or subtle feedback

---

## 🧩 Final Thought

This project is less about a CV and more about how I learn.

I think the best way to understand something is to break it down and rebuild it in your own way. That process is not always clean, but it is effective.

This is one of those projects where I didn’t just make something.

I actually understood something.
