---
layout: default
permalink: /legacy/faq
title: Frequently asked questions (FAQ)
---
[← Back to start](/legacy)

## Frequently asked questions (FAQ) <!-- omit in toc -->

- [General questions](#general-questions)
  - [Where to start](#where-to-start)
  - [How to connect two components](#how-to-connect-two-components)
  - [How to change a model](#how-to-change-a-model)
  - [How to run an analysis](#how-to-run-an-analysis)
  - [No valid results](#no-valid-results)
  - [I am getting an error message "Unable to connect to the Glotaran Update Center because of Zero sized file reported at"](#i-am-getting-an-error-message-unable-to-connect-to-the-glotaran-update-center-because-of-zero-sized-file-reported-at)
  - [My question about Glotaran is not answered by this FAQ](#my-question-about-glotaran-is-not-answered-by-this-faq)
- [Technical issues](#technical-issues)
  - [How to fix tcl/tk errors in Mac OS X](#how-to-fix-tcltk-errors-in-mac-os-x)

### General questions

#### Where to start

This [Glotaran screencast - getting started with Glotaran](https://www.youtube.com/watch?v=ZeVuBustiYQ) video from 2012 may answer your question.

#### How to connect two components

To connect two components/containers together in the analysis scheme editor: press CTRL, click on the name of the container and drag towards another (on the Mac: CMD+CTRL). In this way, a model container can be linked to a dataset container and a dataset container can be linked to an output container.

#### How to change a model

From the Palette (App Menu -> Window -> Glotaran Tools -> Palette) modelling components can be dragged onto the model contains (inside the Parameters container). From there the aspects of each properties can be edited using the property editor (App Menu -> Window -> Glotaran Tools -> Properties). At minimum you need a Kinetic Parameter component with one rate specified and/or a IRF Parameter (Gaussian).

#### How to run an analysis

Once an analysis scheme is [fully connected](#how-to-connect-two-components) and a [valid model](#how-to-change-a-model) is specified. Right click the analysis file from the project explorer and select 'Run analysis' from the pop-up menu.

#### No valid results

If you are getting an error "the analysis did not return valid results, try again with different parameters" when you try to run an analysis with more than 0 iterations, there are two primary reasons.

- The starting values for your parameters are way off
- There is too much freedom in your model for the fitting algorithm to function and you need to simplify your model or introduce constraints in the model somehow

Constraints can be imposed by fixing certain parameters, or by imposing additional spectral constraints - what is best depends on your specific situation. You are more likely to encounter this problem when using target models (KMatrix component), in which you try to estimate more parameters than was possible in global analysis.

#### I am getting an error message "Unable to connect to the Glotaran Update Center because of Zero sized file reported at"

- A: If your network setting are correct, this is most likely due to a mis-configured update center. The easiest solution to this problem is to go to [http://glotaran.org/downloads](http://glotaran.org/downloads "wikilink") and download the latest version of Glotaran in which this problem has been fixed.

#### My question about Glotaran is not answered by this FAQ

Browse through the list of known technical issues, or reach out by e-mail.

### Technical issues

#### How to fix tcl/tk errors in Mac OS X

1. Download and install: <http://xquartz.macosforge.org/landing/>

2. [Download Xcode](https://developer.apple.com/xcode/downloads/) for your version of Mac OS X and install
3. [Download Command line Tools](https://developer.apple.com/downloads/index.action) for Xcode. You will need an Apple ID to sign in.

For instance, if you are running OS X 10.7 (Lion) then you would need

- Xcode 4.6.3
- Command Line Tools (OS X Lion) for Xcode - April 2013

If you are running OS X 10.8 (Mountain Lion) then you would need

- Xcode 5.1.1
- Command Line Tools (OS X Mountain Lion) for Xcode - April 2013

If you are running OS X 10.9 (Mavericks) then you would need

- Xcode 6.1.1
- Command Line Tools (OS X 10.9) for Xcode - Xcode 6.1.1

If you are running OS X 10.10 (Yosemite) then you would need

- Xcode 6.1.1
- Command Line Tools (OS X 10.10) for Xcode - Xcode 6.1.1

etc ...
