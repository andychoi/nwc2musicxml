[![Build Status](https://travis-ci.org/lasconic/nwc2musicxml.svg?branch=master)](https://travis-ci.org/lasconic/nwc2musicxml)

The primary goal of this project is to provide a library to convert NWC scores to MusicXML. Then, Noteworthy users will be able to share their scores with others scorewriters, especially free ones such as [MuseScore](https://musescore.org). For the time being, the library support only NWCtxt and you need a copy of NoteWhorthy composer to save a NWC file to NWCtxt.

The converter is also available online as a webservice on Google App Engine at https://nwc2musicxml.appspot.com/

If you find the software useful you can [donate](https://paypal.me/lasconic).

Features
==

* Multiple staves & voices, invisible staff not exported
* Notes, rests, accidentals, dots, time signature
* Key signature (not the customized ones)
* Clefs included octave shift
* Tie & slurs, triplets
* Line breaks
* Lyrics
* Metadata: Title, author, lyricist, copyright
* Staccato, tenuto & accent, noteheads
* Dynamics (mf, p ...) & custom texts
* Midi info for staff
* Beaming
* Flow control : Coda, Segno, ...


Not yet supported
---
* Chord symbols, grace notes
* Dynamic variation
* Layout information



## ✅ Final Build Command (to create a runnable JAR)

`nwcut.mf` manifest file clearly specifies the entry point of the JAR with:

```
Manifest-Version: 1.0
Main-Class: fr.lasconic.nwc2musicxml.convert.Nwc2MusicXML
```

This means your Ant build target `package.nwc.usertool` will create a runnable JAR file.

---

Run:

```bash
ant package.nwc.usertool
```

This will:

* Compile all Java sources from `src/`
* Use the `nwcut.mf` manifest to specify the main class
* Package everything under `bin/` into:

```
build/nwc2musicxml.jar
```

---

## ▶️ Run the JAR

Once built, execute the JAR from the command line:

```bash
java -jar build/nwc2musicxml.jar
```

Make sure any required external resources (files or input parameters) are passed correctly based on how your `main()` method in `Nwc2MusicXML` is designed.

---

## 🔍 Troubleshooting Tips

* **Class not found?**
  Ensure the `.class` file for `fr.lasconic.nwc2musicxml.convert.Nwc2MusicXML` exists under `bin/fr/lasconic/nwc2musicxml/convert/`.

* **Missing libraries?**
  If your app needs external JARs (e.g., in `lib/`), and they are not for tests only, they must be included in the runtime classpath or bundled via a "fat JAR" (can help if needed).

---

Let me know if you'd like to:

* Create a **fat JAR** including all dependencies.
* Add **arguments** to `java -jar`.
* Use **Gradle or Maven** for modern builds.
