# Sonar Vision

**An early-stage accessibility prototype by Team Zenith**

Sonar Vision explores how AI might help blind and low-vision people understand more about their surroundings through camera-based visual processing and spoken interaction.

> **Prototype notice:** This is an initial testing version. Features may be incomplete or unreliable. Sonar Vision is not a certified assistive device and must not be used for navigation or other safety-critical decisions.

## Our idea

Our long-term vision is a phone-based assistant that lets a user ask questions about what the camera sees and hear a spoken response. We are also exploring relative-depth cues and audio feedback as ways to communicate visual information.

For example, a future version might let someone ask, “What is in front of me?” and hear a concise description of the camera view. This is a development goal—not a claim that the current prototype can safely or reliably provide navigation guidance.

## Current prototype

The project is being developed with Python and Gradio. Depending on the current setup, it may include:

- A prototype interface
- Experimental camera, image, or video input
- Early-stage visual processing and relative-depth cues
- A TinyFish web-search feature, if configured and verified
- Demo or fallback content for testing when live camera access is unavailable

A visible button or panel does not necessarily mean its feature is complete or connected. Please check the current app behavior and report issues.

## Technologies and AI components

The team is exploring or evaluating the following components. **The exact role and implementation status of each should be confirmed against the current code before being described as active functionality.**

- **Python and Gradio** — prototype application and interface
- **TinyFish** — web-search integration, when configured and verified
- **Kokoro** — speech generation / text-to-speech experimentation
- **Deep Think** — reasoning or model-assisted experimentation; exact provider and implementation to be confirmed
- **VT** — [write the full name and role of this component]
- **Smol** — [write the exact model name and role, such as vision, language, or another task]
- **Computer vision / depth estimation** — experimental analysis of camera or image input

Models and services may have different licenses, hardware requirements, privacy implications, and network needs. Consult their official documentation before deployment. Do not include API keys, access tokens, or other secrets in this repository.

## What we are exploring

Existing accessibility products already offer valuable features such as text reading, scene descriptions, object finding, and AI or human assistance. Sonar Vision does not claim to replace or outperform them.

Our design hypothesis is to explore a phone-first combination of:

1. Camera-based visual input
2. Relative-depth cues and optional audio feedback
3. Future spoken questions and spoken responses
4. Optional source-linked web information through TinyFish

These are hypotheses and development goals. We have not yet demonstrated that this combination is more useful, accurate, safe, or accessible than existing options. We hope to learn from blind and low-vision people and accessibility specialists as the project develops.

## Camera behavior

Camera access depends on where the Python app is running:

- A local OpenCV mode attempts to use a camera attached to the computer running the Python process.
- A shared web app needs browser-based webcam input to request permission and send the viewer’s frames to the app.
- A failed OpenCV camera-index check alone does not prove that a camera is missing or broken.

Camera integration is still being tested. When reporting a camera issue, include your operating system, how you launched the app, which camera mode you selected, and the error message. Remove API keys and personal information from logs or screenshots.

## Safety and limitations

Sonar Vision is experimental and is **not a certified assistive device**. Do not rely on it for navigation, obstacle avoidance, crossing streets, or other safety-critical decisions.

Relative-depth output is not a calibrated distance measurement. Results can be affected by lighting, camera position, model errors, processing delays, network conditions, and device differences. Users should continue to rely on their established mobility tools and support.

Do not test the prototype in traffic or other hazardous settings.

## Development status

This project is in its initial stage. The team is developing and testing the interface, camera integration, backend processing, and possible speech interaction.

Phone-camera use, spoken questions, spoken answers, and reliable real-time assistance are future goals unless a feature is implemented and tested in the current version.

## Running locally

Follow the current project files for the exact Python version, dependencies, API setup, and start command. A typical setup may look like this:

```bash
git clone <YOUR_PUBLIC_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>

python -m venv .venv

