Social Network Survey/Analysis Setup
================

<span style="color: red;">**This is a work in progress\!**</span>

## Intro

I’m hoping this will serve as a “starter kit” for setting up and
analyzing a social network survey.

## What’s here

  - .qsf files to import template questions into Qualtrics
  - .csv contact file to import participant lists into Qualtrics
  - .csv sample survey data
  - .rmd sample survey data cleaning code

## Template questions

Qualtrics is a very common online survey platform for collecting social
network data. There is quite a bit of set up (including display logic)
that needs to happen both within the survey and also using some embedded
contact information (from participant contact information), so having a
starting template to import could save some time. If it doesn’t, then I
have probably wasted both your and my time\!

Social network data also comes with some unique aspects of cleaning the
survey data. Here, I will offer some very basic examples that also might
save you some time (verdict is still out I guess\!).

There are two example .qsf files (at the moment). One that is geared
toward *individuals* (in this case, researchers) and another geared
toward *organizations*.

### Contact

In both, the first question is a “contact” question. This is often used
in social network surveys to whittle down to the smaller list of people
(through carry forward logic) that will be assessed further on in the
survey. It is meant to reduce some respondent burden (and some use it
for analyzing frequency of contact). Subsequent sections use the contact
question to determine which names will show.

It is important to note that the contact question itself includes
display logic as initially, you want to be sure that people/orgs are not
shown their own name to rate. This is where you need to be sure to
include a “sortID” or something alike in your uploaded contact sheet.
You will need to reference this embedded data for survey display logic.

### Collaboration

In the organizations template, two different collaboration questions are
offered:

  - The first allows just one activity per person/org e.g. the type of
    collaboration in an ordinal fashion (where one type is considered
    “stronger” or of more value than another). For example, in the
    template, we are saying that Cooperation is stronger than
    Communication only, and so on. On the back end, Communication will
    be assigned an edge weight of 1, Cooperation 2, Collaboration 3, and
    Partnership 4. To look at edge weights, you could look at average in
    vs. out, or decide to take the average between.

  - The alternative question version allows a person to choose multiple
    options. In this example, we are saying that we have separate
    activities that people can be involved in simultaneously. Notice if
    they select “None” here, it is exclusive (meaning they won’t be able
    to select it AND another activities). For this one, you could also
    choose not to include a “None” category and assume that if no
    selection is chosen, then no activities are engaged in. Removing
    also reduced the burden for a long survey (with many people to have
    to scroll through/select for). *Notice the removal of “only” from
    the Communication column.*
