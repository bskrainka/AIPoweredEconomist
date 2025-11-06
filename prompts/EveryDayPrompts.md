#   Everyday Prompts

##  Working with Documents

```
You are a Principal Economist with deep knowledge of causal inference and reduced form
methods. Your task is to critically assess both experimental and observational models to ensure
that they maintain a high bar for science and software engineering. All models
should be supported by strong evidence when validated vs. RCTs. Assess models for both
the evidence that was provided and is missing. Good observational models can successfully rank RCTs
and also do not detect a signal during placebo tests.

Evaluate the quality of the model described in this 
pdf: resources/Skrainka.pdf.  List the strengths and weaknesses. How trustworthy is
the evidence to supporting this model and whether it we should trust it
for a competition analysis?
```

##  Adding context

```
/context add ~/.aws/amazonq/contexts/PrincipalEconomistContext.md

Evaluate the quality of the model described in this 
pdf: resources/Skrainka.pdf.  List the strengths and weaknesses. How trustworthy is
the evidence to supporting this model and whether it we should trust it
for a competition analysis?
```

##  Many things are possible

```
In the directory resources/whiteboard you will find several image files. Read each file and convert each image to notes.
Then write the notes to one markdown file.
```

##  Code reviews

```
list scripts

run initial-code-review
```

##  Evaluating Posters

```
You are a Principal Economist and need to review submissions for a poster
session on Generative AI. Your task is to rate each submission. You can
find the submissions in the spreadsheet in resources/papers.csv.

Your task is:

1.  Process each row in the spreadsheet which corresponds to one submission.
2.  For each row, read the abstract and customer impact statement.
3.  Rate the Innovate Score using the rubric below.
4.  Rate the Impact using the rubric below.
5.  Compute the total score.

Here are the evaluation rubrics:

##  Impact (1-5):

5: Significant impact across multiple applications
4: Significant impact for specific application
3: Potential impact, but unclear application
2: Clear application, minimal impact
1: No impact, no clear application

##  Innovation Score (-1 to 3):

3: Must-include, extremely innovative
2: Innovative
1: Somewhat innovative
0: Neutral
-1: Should not include

The Total Score = Impact Score + Innovative Score
```
