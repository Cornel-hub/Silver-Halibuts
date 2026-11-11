# AI interaction record — Phase I

Date: 11 November 2026

An AI coding assistant was used to help develop the analysis, write visualization code and draft explanations. This record summarizes the main requests and decisions. The prompt descriptions below are paraphrased, not exact quotations or a full chat transcript. The earlier AI-assisted shared setup is documented separately in the group repository.

## Main requests

| Request summary | How it affected the work |
|---|---|
| Review the assignment and the existing project, then help prepare the AI-aided Phase I contribution. | The analysis used the shared model outputs already in the repository. There was no additional model run. |
| Use the team discussion to identify the agreed dataset and the questions that still needed investigation. | The work followed the chosen 730-question setup and focused on framing effects, differences between true answers and myths, and the uncertainty hypothesis. |
| Develop the analysis and explain the findings clearly. | AI assistance was used to generate code, plots and draft interpretations. Follow-up checks added paired comparisons and separated changes that repair an error from changes that create one. |
| Reduce the material to what was needed for the team handoff. | The code, results and explanations were combined into one self-contained notebook, accompanied by this record and the reflection. |

## Suggestions and changes

The paired comparisons were kept because they follow the same proposed answer across different framings. This made it possible to see changes that an overall accuracy score would hide. True answers and myths were also shown separately, since increasing agreement can help one group and hurt the other.

The uncertainty analysis needed more care. A low probability of Yes can mean a confident No, so confidence was defined as `max(p, 1−p)`. The analysis then compared three measures: decision changes, changes in probability and changes in log odds.

The conclusion was narrowed after these checks. Uncertain judgments changed decision more often, but this did not always mean a larger change in the model's underlying Yes/No preference. The notebook therefore explains the role of the decision cutoff and the probability scale instead of making a general claim that uncertainty causes stronger influence.

The analysis also kept questions together when calculating uncertainty intervals. Treating every framed prompt as an independent example would ignore that several prompts come from the same question. Conditional error-change rates use Wilson intervals to handle observed rates of zero or 100%.

## Problems found and corrected

- A prompt check initially failed because of differences in Windows line endings. The comparison was adjusted without changing the original data.
- The category heatmap had an overlapping colorbar, which was corrected after inspecting the figure.
- Some initial bootstrap intervals had zero width at boundary rates. The interval method for conditional rates was changed.
- Interpretations about internal knowledge were left out because the Phase I outputs alone cannot establish what the model represents internally.

## Checks and limits

The data checks covered missing values, duplicate conditions and the expected eight records per question. The self-contained notebook was rerun, and its main counts and eight figures were reproduced using the team's existing CSV files.

The analysis uses 5,840 stored outputs from Qwen2.5-1.5B-Instruct. AI assistance contributed substantially to the code, visualizations and written interpretation. The notebook should be reviewed by the pair before submission. A direct comparison with the human-only pair's findings still needs their actual notebooks; the team messages alone were not enough to make that comparison.
