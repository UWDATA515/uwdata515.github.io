---
layout: page
title: Projects
collection: winter2026
---

## Overview
The course project is a "capstone" that pulls together all elements of the course: data, programming, coding style, version control, testing, design, and team collaborations. This is a team effort, often with members drawn from different disciplines.

Projects will address a science or business question of interest. For example, a business question related to the bike sharing company Pronto might be "How should bicycles be allocated among stations?" An **analysis project** would seek data to answer this question directly. However, you may choose not to answer the question yourself. Rather, you might do a **tool project** that builds a tool to help others to answer the question. For example, one such tool might be a package that better organizes the Pronto data for analysis. Still another possibility is that you will build a system that teaches others the skills needed to do analysis, which we call an **instructional system project**. An example here would be a system that teaches about logistics for businesses in the sharing economy. Finally, you might choose to build a piece of software that allows people to interact with and gain insights into your data set, which we will call a **data presentation project**. In this case, you might build an interactive website with visualizations comparing Pronto station usage over space and time. Other types of projects are possible as well.

## Project Schedule

* Week 5: Project Proposals & team formation (presentations in class)
* Week 6: Software & Use Case Design (exercise in class)
* Week 6-10: Standups & project work
* Week 8: First demo & technology review (in class)
* Week 10: Practice presentation, consultations with instructors
* Finals: Presentation (presentations)

## Project Workflow

We will talk through each of these stages in lectures. Step 3 will be a dedicated lecture.

### Step 1: Pick Your Data (Weeks 1-5)
You must have **two** distinct data sets so that you can demonstrate an ability to join data with different characteristics (e.g., granularity in time and/or space). The data must be available immediately, without concerns about access rights for team members or the instructors.

### Step 2: Define the Problem (Weeks 1-5)
Determine the type of project (e.g., analysis project) and the questions of interest.

### Step 3: Write the Specification (Week 6)
The specification details:

* who are the users and what do they know (e.g., business analyst)
* what information users want from the system (e.g., where to put bicycles)
* use cases - how users interact with the system to get the information they want
* components - what pieces do you need to build
* milestones

For tool projects, the users are typically programmers, and so the functional specification describes the programming interface.

For research projects, you'll have people using the research tools as well as people consuming the research result.

See below for the details about what design documents we expect from your functional specifications.

### Steps 4 and beyond: Iteratively Develop And Refine the Project (Week 7+)
You will organize the project as a set of short-term deliverables. Typically, you focus first on those parts where you have the most uncertainty since projects typically fail because of "unknown unknowns". For some projects, this will be a data-first focus to make sure that your data can answer the questions that you pose. For others, it may be exploring a python package that you hope will provide key features (e.g., visualizations).

## Project Structure
Projects should have a online github repository with the project name. Top level folders/files within the repository include:

* README.md file that gives an overview of the project
* LICENSE file
* [setup.py script](https://docs.python.org/3/distutils/introduction.html#an-introduction-to-distutils) or [pyproject.toml](https://packaging.python.org/en/latest/tutorials/packaging-projects/#packaging-python-projects) that initializes the project (we will discuss this in Lecture 9)
* `docs` folder that contains documentation (including the functional specification, the design specification, the technology review, and the final project presentation)
* python package folder (with the same name as the repository) that is structured as one or more python modules/subpackages (e.g., with `__init__.py` files) and test files that begin with "test_".
* examples folder that contains examples of using the packages. An example is a step-by-step walkthrough of how a user would interact with your project - all the users that you've identified as part of your functional specification.

## Design Documents

You will create at least three **Markdown documents** describing the design of your project. These documents should be in your project `docs` folder, and the first draft (for grading) is due as specified in the timeline above.

- **Functional Specification**. The document should have the following sections:
  - Background. The problem being addressed.
  - User profile. Who uses the system. What they know about the domain and computing (e.g., can browse the web, can program in Python)
  - Data sources. What data you will use and how it is structured.
  - Use cases. Describing at least two use cases. For each, describe: (a) the objective of the user interaction (e.g., withdraw money from an ATM); and (b) the expected interactions between the user and your system. Additional use cases are recommended, if applicable!

- **Component Specification**. The document should have sections for.
  - Software components. High level description of the software components such as: *data manager*, which provides a simplified interface to your data and provides application specific features (e.g., querying data subsets); and *visualization manager*, which displays data frames as a plot. Describe at least 3 components specifying: what it does, inputs it requires, and outputs it provides. If you have more significant components in your system, we highly suggest documenting those as well.
  - Interactions to accomplish use cases. Describe how the above software components interact to accomplish your use cases. Include at least one interaction diagram per use case.

- **Milestones**. A preliminary plan - a list of milestones, each with a list of tasks in priority order.

## Technology Review
The technology review is about making decisions about the choice of a python library to address a technology need in the project. For example, many projects make use of map visualizations. There are many python libraries that support these visualizations such as Bokeh, Dash, and googlemaps. The libraries have different capbilities, such as what (if any) interactions users can have with the map. You will want to choose a library that: (a) addresses the requirements of your project; (b) is compatible with other elements of your project (e.g., runs on python 3); (c) is relatively easy to use; (d) is computationally efficient for the scale of data you use; and (d) doesn't have software bugs that will impair your use cases.

The technology review is a group assignment. It will consist of two pieces: a writeup, and a demo.

The writeup should be a **Markdown document** and include the following components:
- Background on the problem you're solving to motivate a technology for which you need a python library (e.g., interactive maps), with the use case for which the technology is required.
- Description of 2-3 (no more) python libraries that potentially address your technology requirement (name, author, summary, etc).
- A side-by-side comparison of the technologies. This will require that you actually install and use the technologies.
- The final choice you've made and why.
- Description of the drawbacks or areas of concern on your choice.

The demo should be either a screen recording or output as a result of you using the package, for example input=>code=>output, or a visual demonstration. Be prepared to demonstrate the package live to instructors during the "First Project Demo" in Lecture 8.

Upload both the writeup and the demo to a `docs/technology_review` folder in your GitHub repository.

## Final Project Presentation

Teams will present their projects using slides in 10 minute oral presentations. We are STRICT on this time limit, and we will cut you off if you go over. We STRONGLY RECOMMEND that you practice your presentation beforehand. The presentation should include:

- Background. Describe the problem or area being addressed, as well as any previous work by other people or organizations that might overlap with the project or be related.
- Data used. What data did you use? How was it obtained? What are its limitations?
- Use cases. How users will interact with your system in a way that addresses the problem area.
- Design. Describe the components and how they interact to accomplish the use cases.
- Demo. Demonstrate your software. **Do not omit this!** If you don't want to risk a live demo, feel free to include a screen recording of the demo.
- Lessons learned and future work. Focus on *software engineering* lessons.

You should add a PDF of your presentation in the `docs` folder of your project BEFORE the final presentation during finals week, as well as a screen capture recording of your demo (we want this in case there are issues with attaching your computer to the podium during the presentation).

## Grading Rubric
Projects will be evaluated based on the following criteria:

* Organized as described in the section on project structure
* Uses PRs (with good descriptions and test plans) and code reviews.
* Quality of the documentation (especially the functional
specification and design specification), including how to run the
project so that the instructors can understand how to make it work.
* Uses at least two data sources
* Code quality, especially consistent coding standard (e.g., ``pylint``).
* Has a `tests` folder and has comprehensive tests, with high test coverage. Note however that test coverage is NOT sufficient on its own - for instance, you must test your code's behavior in addition to edge tests.
* Quality of the example of using the package (in the examples
folder of the project repository)
* Supports a virtual environment to enable easy collaboration, including how to set up the virtual environment.
* Implements continuous integration (e.g., via GitHub Actions), and all tests pass (lint, tests, and code coverage). Must also include badges in your project's overall README file reporting your continuous integation status AND code coverage.
* Completeness of the [setup.py script](https://docs.python.org/3/distutils/introduction.html#an-introduction-to-distutils) or [pyproject.toml](https://packaging.python.org/en/latest/tutorials/packaging-projects/#packaging-python-projects)
* Features implemented (ie the code should be functional, even if the project did not accomplish all the goals that it set out to)
* Creativity and technical challenge
* Technology review
* Final presentation

Grades for the project will be assigned to the entire team, although
there will be adjustments
for significant discrepancies in
the relative contributions of team members.
The latter will be assessed by commit logs and by
a survey students will submit
at the end of the quarter.

## Examples of previous projects
These examples are fantastic, though they may not be perfect. They should be considered examples of what kinds of projects are possible and not necessarily examples to be precisely emulated.  The examples below include an analysis project, a visualization project and a reusable data project.

### Winter 2024
* [Box Office Prediction](https://github.com/c0zimb4tm4n/box-office-prediction) - an innovative tool designed to aid the movie production industry. Aimed at producers, directors, casting directors, and industry insiders, this tool leverages predictive analytics to forecast the potential revenue of movies that are still in the conceptual phase.
* [TLDhubeR](https://github.com/apeled/TLDhubeR) - an application that allows users to search for and summarize content in the Huberman Lab Podcast using a chat interface, all from the comfort of their browser.

### Winter 2023
* [Smogon API](https://github.com/ramirostUW/SmogonAPI) - This is an example of a **tool project**. It provides an API to access Pokemon data from the Smogon platform.
* [UW Alerts](https://github.com/evanyfyip/uw-alert-web) - A web application and visualization of the UW campus and surrounding area that parses real-time information from the UW alerts system and displays the alert's origin. Also explores alert trends over time and location.
* [Wisconsin Wolf Analysis](https://github.com/mohammap22/WisconsinWolfAnalysis) - This **analysis project** explores the wolf population in Wisconsin and its impacts on the local ecosystem.

**ALL INFORMATION MUST BE POSTED TO YOUR REPO BY THE DEADLINE**
