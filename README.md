# Sonar Vision

**An early-stage accessibility prototype by Team Zenith**

Sonar Vision is an experimental project exploring how AI might help blind and low-vision people get more information about their surroundings through a phone camera and spoken interaction.

This repository contains an **initial testing version only**. It is a work in progress. Features may be incomplete, unreliable, or unavailable depending on the code, device, permissions, and network setup.

## The idea

Our longer-term vision is a phone-based assistant that lets a user ask questions about a camera view and hear spoken responses. We are also exploring whether relative-depth visualizations and audio cues could make nearby scene information easier to interpret.

For example, a future version might let someone ask, “What is in front of me?” and hear a concise description based on the camera image. This is a product direction—not a claim that the current prototype can safely or reliably provide navigation guidance.

## Current prototype

The current project is being developed with Python and Gradio. Depending on the version and configuration, it may include:

- A prototype user interface
- Experimental camera, image, or video input
- Early-stage visual or relative-depth processing
- A TinyFish web-search feature, if configured and verified
- Demo or fallback content for testing when live camera access is unavailable

A visible button or panel does not necessarily mean its feature is fully implemented or connected. Please check the actual app behavior and report issues.

## How we think Sonar Vision could differ

Existing accessibility products already provide valuable features such as reading text, describing scenes, answering questions about images, finding objects, and spoken interaction. For example, Microsoft Seeing AI describes people, text, currency, colors, objects, and scenes. Be My Eyes offers AI assistance as well as access to volunteers. Envision offers smart-glasses features including scene descriptions, object finding, reading, and an AI assistant. Sonar Vision does **not** claim to replace or outperform these products.

Our current design hypothesis is to explore a different combination and interaction:

1. **Phone-first experimentation:** investigate whether a standard phone camera can support an accessible prototype without requiring dedicated smart-glasses hardware.
2. **Relative-depth cues:** test whether a simple visual depth representation and audio alerts can communicate that an area appears nearer or farther. These estimates are not calibrated measurements.
3. **Conversational interaction:** explore a future voice interface where the user can ask follow-up questions about a camera view and receive spoken responses.
4. **Web information alongside camera input:** test whether a separate TinyFish-powered panel can retrieve public, source-linked information relevant to a user’s query. Web search does not verify a route or establish that a place is safe.

These are hypotheses and development goals. We have not yet demonstrated that this combination is more useful, more accurate, safer, or more accessible than existing options. We intend to seek feedback from blind and low-vision people and accessibility specialists before making such claims.

## Technical direction

The current prototype uses Python and Gradio for the interface. Depending on how it is launched, camera input may come from a local camera attached to the machine running Python, or from a browser webcam component that sends frames to the app. These are different camera paths.

The longer-term concept may involve:

- A mobile app that requests camera and microphone permissions
- On-device or server-side computer vision for scene understanding and relative-depth estimation
- Speech recognition for spoken questions
- A language model to formulate concise answers based on image-analysis results
- Text-to-speech for spoken responses
- Optional web retrieval through TinyFish, with source links shown or announced where appropriate

These components are not all present or validated in the current version. The model, hosting, privacy, latency, accessibility, and safety choices remain under development.

## Safety and limitations

Sonar Vision is an experimental prototype. It is **not a certified assistive device** and must not be used as the sole source of information for navigation, obstacle avoidance, crossing streets, or other safety-critical decisions.

Relative-depth output is not a calibrated distance measurement. Camera coverage, lighting, model errors, latency, network connectivity, and device differences can all affect results. Users should continue to rely on their established mobility tools and support.

Do not use the prototype to make safety-critical decisions. Do not test it in traffic or other hazardous settings.

## Development status

This project is in its initial stage. The team is still building and testing the interface, camera integration, backend processing, and possible voice interaction.

Phone-camera use, spoken questions, spoken answers, and reliable real-time assistance are **future goals unless a specific feature is implemented and tested in the current version**.

## Camera notes

Camera behavior depends on how the app is launched:

- When Python runs locally, an OpenCV camera mode attempts to access a camera attached to the computer running Python.
- When someone opens a shared web link, the Python process may still be running on the developer’s computer. Accessing the viewer’s camera requires a browser webcam input that requests permission and sends frames to the app.
- A failed OpenCV camera-index check does not by itself prove that a camera is physically missing or broken.

Camera integration is still being tested. When reporting a problem, include your operating system, how you launched the app, which camera mode you selected, and the exact error message. Remove API keys and other secrets from logs or screenshots.

## TinyFish and API keys

If TinyFish is enabled in your copy of the project, configure its API key locally using the method documented in the code. Never commit API keys, `.env` files, passwords, or other secrets to GitHub.

If a secret is accidentally published, revoke or rotate it immediately.

TinyFish results are web information with sources. They do not certify a location, confirm that a route is accessible, or establish that a route is safe.

## Possible sustainability and revenue models

We have not selected or validated a business model. Any future model would need to be designed with input from blind and low-vision users, accessibility organizations, and potential partners. Possibilities to investigate—not promises—include:

- A free core app with optional paid features, if user research shows that a paid tier is useful and equitable
- Institutional licensing or support contracts with schools, rehabilitation organizations, employers, or service providers
- Grants, research funding, or sponsored accessibility pilots
- Partnerships with organizations that want to improve accessible services

We do not claim that Sonar Vision can generate more revenue than existing products. Established products may have different costs, hardware, partnerships, subscriptions, and support models. Before choosing a model, the team would need to evaluate development and inference costs, privacy and safety obligations, affordability, accessibility, and willingness to pay. Any paid feature must not make essential safety or accessibility information misleadingly exclusive.

## Running locally

The exact setup may change as the project develops. Follow the current dependency files and entry-point instructions in the repository.

1. Install a compatible version of Python.
2. Clone the repository:

   ```bash
   git clone <YOUR-GITHUB-REPOSITORY-URL>
   cd <YOUR-REPOSITORY-FOLDER>
