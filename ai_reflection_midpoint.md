# Reflection on AI use — Phase I

## AI-Aided Pair

- **First name:** Prasam Sanjay  
  **Last name:** Toliya  
  **Student ID:** k51850933
- **First name:** Ergi  
  **Last name:** Meda  
  **Student ID:** k12112984

## How AI helped

An AI assistant helped develop the analysis, write the plotting code and draft explanations of the results. The work used the dataset and model outputs that the group had already prepared.

One useful suggestion was to look at changes from the neutral framing instead of only comparing overall accuracy. Leading wording fixes 168 judgments of true answers, but also makes 147 judgments of myths wrong. These effects partly cancel out in the average score. Showing them separately makes the model's behavior easier to understand.

AI assistance also helped expand the analysis to include categories, changes in each question's answer pattern, and the uncertainty question raised in the team discussion. This gave the investigation more depth than an accuracy table alone.

## What needed checking

The uncertainty analysis was a good example of why the first explanation needs checking. A low Yes probability can mean that the model is confident about No. Confidence was therefore measured using `max(p, 1−p)`.

The analysis also compared decision changes with changes in probability and log odds. Uncertain judgments changed decision more often, but under leading wording the average log-odds changes were similar across confidence groups. The conclusion was adjusted: uncertain decisions are easier to flip, but that does not always mean a stronger influence on the model's score.

There were also code and plotting issues. A prompt check failed because of Windows line endings, and the category heatmap initially had an overlapping colorbar. Some uncertainty intervals needed a different method when the observed rate was zero or 100%. These problems were corrected during the analysis. They show that AI-generated code and explanations still need verification.

## Comparing the two approaches

The team discussion describes scatter plots grouped by answer type and category, as well as the same question about uncertainty. This AI-aided contribution includes those questions and adds paired error changes, uncertainty intervals and a check of the probability scale.

The other pair's actual notebooks were not available for this analysis, so a direct comparison of findings is still needed. The group should compare the notebooks together and discuss which results each approach found, what was missed and how much checking was required. There is no recorded evidence here for claiming that either approach was faster or better.

## Main lessons

- Start from the shared data and keep the comparisons consistent.
- Check what a model score actually measures before interpreting it.
- Look at individual changes as well as average results.
- Check AI-generated code, figures and explanations rather than accepting the first version.
- Keep a record of suggestions that were changed or rejected, as well as those that were used.

AI assistance was useful for expanding the analysis, but the results still depend on clear definitions and careful checks. The pair should review this reflection and add its own experiences during the joint discussion. For Phase II, the pairs will switch AI-use roles as required by the assignment.
