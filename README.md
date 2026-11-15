# Rock Paper Scissors: data collection app and server

An Android app and a Python server I built at IDSIA (Lugano) between October 2017 and January 2018. They let people take labelled photos of rock, paper and scissors hand gestures with their phone and send them to a server, to grow the dataset of an educational machine learning activity.

The activity itself, the neural network and the paper are the work of others (see below). This repository holds only the part I built, so that it is clear who did what.

## The original project

- Repository: [alessandro-giusti/rock-paper-scissors](https://github.com/alessandro-giusti/rock-paper-scissors)
- Paper: A. Giusti, D. Huber, L. M. Gambardella, *Introducing Machine Learning Concepts by Training a Neural Network to Recognize Hand Gestures*, Proc. of the AAAI Symposium on Educational Advances in Artificial Intelligence (EAAI), 2018.

Students train a neural network that recognizes the three gestures from a camera, and see it work live. The original repository lists the app and server as its supporting software for data collection.

## Who did what

**Already there before I started (September to October 2017, Alessandro Giusti):** the training notebook, the neural network model, the first photo datasets, the real-time demo and the presentation.

**What I built (October 2017 to January 2018):**

- **Android app** (`RPS_App`): camera preview, a photo button with a rock / paper / scissors / testing label, upload to the server, deletion of the last photo, a connection indicator, and a test mode that shows the network's prediction for the photo just taken.
- **Server** (`RPS_Server/server.py`): a small Python API (built with [hug](https://www.hug.rest/)) that receives photos, stores them by label with a timestamp and the device id, approves devices through allow / pending / block lists, deletes photos on request, and in test mode runs the existing model on the photo and returns the prediction. My first server was written in Java (October 2017) and replaced by this Python one at the end of that month.
- **CrowdImaging** (January to February 2018): a design for a general platform where ordinary people collect images for any image recognition problem, with ideas on rewarding participants, scoring the reliability of users and photos, and avoiding duplicates, plus a first server with login and a database. It continued in a private repository and is not included here.

**After me:** David Huber cleaned up the server folder in March 2018. The notebooks, datasets and paper were developed by Alessandro Giusti, David Huber, Fabrizio Patuzzo and other contributors.

### My commits in the original repository

| Date | Commit | What |
|---|---|---|
| 2017-10-16 | [04c7333](https://github.com/alessandro-giusti/rock-paper-scissors/commit/04c7333) | First app and server (committed as HorseEmbedded, my SUPSI student account) |
| 2017-10-26 | [ef7babe](https://github.com/alessandro-giusti/rock-paper-scissors/commit/ef7babe) | Small preview and label over it |
| 2017-11-12 | [f981bbe](https://github.com/alessandro-giusti/rock-paper-scissors/commit/f981bbe) | Python server and app working together |
| 2017-11-22 | [5815a12](https://github.com/alessandro-giusti/rock-paper-scissors/commit/5815a12) | Updates |
| 2018-01-10 | [2c85967](https://github.com/alessandro-giusti/rock-paper-scissors/commit/2c85967) | App graphics fixed |
| 2018-01-18 | [6c7f8f5](https://github.com/alessandro-giusti/rock-paper-scissors/commit/6c7f8f5) | First step towards the CrowdImaging server |
| 2018-01-18 | [d848646](https://github.com/alessandro-giusti/rock-paper-scissors/commit/d848646) | Removed the old Java server |
| 2018-01-31 | [f660cca](https://github.com/alessandro-giusti/rock-paper-scissors/commit/f660cca) | Web service for CrowdImaging |
| 2018-01-31 | [ee4b903](https://github.com/alessandro-giusti/rock-paper-scissors/commit/ee4b903) | Renamed folders and Android packages |
| 2018-01-31 | [d2dcdd4](https://github.com/alessandro-giusti/rock-paper-scissors/commit/d2dcdd4) | Removed the old names |

## What is in this repository

The code of `RPS_App` and `RPS_Server` exactly as it was at commit `d2dcdd4` (31 January 2018), unchanged, with these exceptions:

- the photos collected by the server are left out, for the privacy of the people who took them
- the trained model file (`rps.model`) is left out, because it comes from the original project's notebook
- the device lists (`allowed.txt`, `black.txt`, `pending.txt`) are empty
- Android Studio settings and build output are left out

## Status

Historical code, kept as a record and not maintained. It uses Python 2, an old version of Keras and the old Android camera API.
