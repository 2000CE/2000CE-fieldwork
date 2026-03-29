Swadesh List & Picture Book Elicitation — Automated Tool Proposal
1. Purpose of This Application
This proposal outlines the structure of an application that allows researchers to safely collect recordings of basic vocabulary (200–3000 words) simply by having a speaker look at illustrations and produce utterances.

Extremely simple operation

Automatic data organization

Robust against interruptions and misoperations

No loss of word‑initial segments

Resistant to failure in fieldwork environments

2. Basic Operation
Launch the app → START screen appears

Press START → recording session begins

Illustration 001 is displayed

A 0.6‑second black screen follows the illustration

After the black screen, the app enters recording‑ready mode

Speaker produces the utterance

User selects Y / R / N

App proceeds to the next item

When finished, a folder is automatically generated

3. Recording Mechanism
● Continuous background recording
The app continuously records while running. This serves as a safety backup.

● Segment extraction (prevents loss of word‑initial sounds)
Previous word ends

Input volume exceeds threshold

Recording begins 0.2 seconds before the threshold crossing

Recording ends when the user presses the confirmation button

If no threshold is set, recording begins at the moment the confirmation button is pressed.

4. Recording Threshold (Volume Detection)
The volume threshold used to detect the beginning of an utterance can be adjusted according to the recording environment.

A higher threshold reduces background noise triggers.

A lower threshold is suitable for quiet environments or soft‑spoken speakers.

If no threshold is set, the system automatically switches to manual‑start mode, where recording begins at the moment the confirmation button is pressed.

This allows the application to adapt to a wide range of fieldwork conditions without requiring complex calibration.

5. Handling of Illustrations
Illustrations are stored in an external folder with numbered filenames
Example: 001_original.png

When Y is pressed, the illustration and audio file are saved in a folder such as:
words/001/

A 0.6‑second black screen is inserted between illustrations

6. Meaning of Y / R / N
Y (Yes / Accept)
Save audio and illustration

Save metadata

R (Redo)
Re‑record the current item from the beginning

Overwrite only when the new recording is complete

N (None / Not applicable)
Record "none" in meta.json

Do not save audio

※ Button assignments can be changed.

7. Interruptions & Navigation
ESC: pause menu

F key: temporary pause

← arrow: go back to previous item (if speaker can operate it)

8. Autosave & Auto‑exit
If there is no operation for 15 minutes:

Autosave

Folder generation

App exits

A session folder is always preserved, even if interrupted.

9. Folder Structure
コード
Session_YYYYMMDD/
├─ master_audio/
│   ├─ full_01.wav
│   └─ full_02.wav
├─ words/
│   ├─ 001/
│   │   ├─ original.png
│   │   ├─ audio.wav
│   │   └─ meta.json
│   ├─ 002/
│   └─ ...
├─ metadata.json
└─ session_log.txt
10. Behavior in Case of Errors
Forced termination → individual files remain

master_audio may be discarded

If an illustration cannot be loaded → record in log and skip

If storage is insufficient → generate folder with whatever was saved

11. Overhead Video
Recorded on a separate device

Completely independent from the app

No synchronization required

Intended Use
University laboratories

Linguists

Programmers

Student projects

Fieldwork teams

This proposal is published so that anyone can freely implement it.

March 30, 2026 — 2000CE
