# Coauthor Comment Resolution Review

Reviewed latest manuscript: `manuscript/lucy-remeasurement-289fccb-20260607.docx`

Compared against:

- `manuscript/lucy-remeasurement-289fccb-20260528-zak.docx`
- `manuscript/lucy-remeasurement-289fccb-20260528-naveed.txt`
- `manuscript/lucy-remeasurement-289fccb-20260528-kcsantiago.pdf`
- `manuscript/lucy-remeasurement-289fccb-20260528.pdf`

## Executive Summary

The latest manuscript addresses many substantive coauthor comments, especially around threshold terminology, HAZ definition, ROC presentation, generic naming of the 10% rule, and stronger discussion of the lack of real-world clinical validation.

However, the comments are not fully resolved. The latest DOCX still contains 13 active comments, 198 tracked insertions, and 147 tracked deletions. The rendered manuscript also shows tracked changes visibly throughout the document. Before submission or broader circulation, the document should be cleaned by resolving comments and accepting/rejecting tracked changes.

Open substantive items remain:

- The 10% rule alert rate of 27.2% remains in the manuscript, but Naveed's request to double-check Epic behavior/date-window behavior is not addressed in text.
- Naveed's request/question about the distribution of height deltas is not addressed in text.
- Methods readability improved but remains dense; the latest DOCX still contains active comments indicating parts are hard to understand.
- "Reference measurement" terminology was reduced but not eliminated, despite Zak's objection.
- Karl's suggestion to name Hyperspace/Epic Systems was not incorporated, likely because it conflicts with Naveed's request to avoid making the 10% rule sound Epic-specific.

## Structural Status of Latest DOCX

- Active comments: 13
- Tracked insertions: 198
- Tracked deletions: 147
- LibreOffice render: successful via DOCX to PDF, then PDF to PNG
- Rendered page count: 29 pages
- Visual layout: figures and references render legibly; I did not see the earlier reference URL margin overflow in the rendered latest version.
- Visual issue: tracked changes are visible throughout, making the document look like an editing draft.

## Zak Comments

### Threshold clarity

Status: addressed in content, but comment remains active.

Zak commented that "default threshold" was hard to understand because the kind of threshold was unclear. The latest draft now uses "alert-confidence threshold" in the abstract/results and describes the threshold in the methods.

Remaining action: resolve the lingering comment in Word after confirming wording.

### Abstract conclusion clarity

Status: mostly addressed, but comment remains active.

Zak's "What are you saying?" comment on the abstract conclusion appears to have been addressed by adding a clearer statement that no real-world benchmark of confirmed pediatric height error exists, that the EHR cohort lacks ground-truth labels, and that the analysis estimates operational alert volume rather than deployed predictive value.

Remaining action: decide whether this abstract conclusion is now too long. It is clearer, but dense.

### "Reference measurement" / recoverability language

Status: partially addressed.

Zak objected that the issue is not whether a "reference measurement" is recoverable, but whether the accurate clinic measurement is recoverable. The latest draft removes some of the strongest "recoverable reference measurement" language and now says "original measurement uncertainty can often still be reduced."

Remaining issue: the latest manuscript still uses "reference measurement" or similar language in several places, including "external reference measurement," "contemporaneous reference measurements," and "imperfect but useful references." If Zak's objection is meant globally, this remains unresolved.

Recommended action: replace most instances with "repeat clinic measurement," "contemporaneous repeat measurement," or "accurate clinic measurement" where appropriate.

### Undefined terms / fused confidence

Status: partially addressed.

The latest methods now define confidence estimates between 0 and 1, introduce weighted noisy-OR fusion, and cite Pearl. That addresses Zak's request for method description/citation.

Remaining issue: active comments remain at the conceptual-framing paragraph, and the paragraph still says "continuous error confidence and a categorical label indicating whether to alert error," which is not very clear for a clinical reader.

Recommended action: rewrite the paragraph in plain language before the formal detector/fusion details.

### HAZ definition

Status: addressed.

The latest draft defines HAZ as "height-for-age z-score (HAZ)." The active comment should be resolved.

## Naveed Comments

### Verbosity / LLM-style prose

Status: partially addressed.

The specific examples Naveed flagged appear removed or rewritten:

- "This limitation is not primarily an algorithmic shortcoming..." is no longer present.
- "not because the field has been methodologically incautious..." is no longer present.

Remaining issue: the latest DOCX still has an active Naveed comment: "Classic LLM writing construct. I would rewrite this" on the Discussion opening. The current text is improved but still broad and somewhat generic.

Recommended action: rewrite the Discussion opening more directly around the concrete result and limitation, rather than restating the high-level framing.

### Journal / venue fit

Status: not a manuscript-edit item.

Naveed suggested the work may fit a technical conference or methods-focused journal such as JBI, rather than a clinical journal. The manuscript does not need to incorporate this unless the cover letter/submission target is being decided.

### Methods 2.1-2.7 readability

Status: partially addressed.

Definitions and explanatory detail were added, but the methods remain technically dense. Active comments in the latest DOCX still include "Further define" and "I didn't understand this part."

Recommended action: add a short "plain-language pipeline summary" before the detector details, or simplify Section 2.1 so a physician reviewer understands the workflow before seeing equations and detector names.

### ROC curve suggestion

Status: addressed.

The latest draft adds a ROC curve discussion and `Figure 2b: Zoomed ROC curve of the streaming pipeline across the alert-confidence threshold.`

### 10% rule / 27.2% alert-rate concern

Status: not addressed.

Naveed was surprised by the 27.2% alert rate and suggested double-checking whether Epic's 10% rule applies only under certain prior-visit timing conditions. The latest manuscript still reports the 27.2% alert rate and does not mention any validation of the local Epic rule behavior or timing-window assumptions.

Recommended action: either verify the rule implementation and add a short methods sentence, or qualify the comparator as a reimplementation of a 10% prior-height-change rule rather than confirmed Epic production behavior.

### Height-delta distribution

Status: not addressed.

I did not find a height-delta distribution, figure, table, or text response in the latest manuscript.

Recommended action: add a supplementary figure/table or a short descriptive sentence if the distribution was inspected.

## Karl Santiago PDF Comments

### BIV terminology

Status: addressed.

Karl suggested clarifying "BIV." The latest draft uses "Population biologically implausible value check" rather than only "Population BIV check."

### "Based on our literature review"

Status: addressed by removal/rewrite.

I did not find the suggested phrase in the latest draft.

### Hyperspace / Epic Systems Corporation

Status: not incorporated.

Karl suggested adding "Hyperspace (Epic Systems Corporation)." The latest draft instead says "local EHR (Epic)" and uses generic "10% rule" terminology.

This is probably intentional because it conflicts with Naveed's request not to make the 10% rule sound proprietary to Epic.

### Curly quotes and punctuation

Status: mostly addressed.

The latest rendered document uses typographic quotes in most places, though some extracted text still shows straight quotes in examples. This is not a major unresolved issue unless journal style requires typographic quotes consistently.

### HAZ confusion

Status: addressed.

HAZ is now defined as "height-for-age z-score (HAZ)."

### Carry-forward wording

Status: addressed.

The carry-forward duplicate check now explicitly explains copied-forward/repeated measurement behavior.

### Reference margin break / long URLs

Status: addressed visually.

The latest LibreOffice render did not show the prior margin-breaking URL issue in the references.

### Optional CDC/AMIA links

Status: not incorporated, optional.

Karl suggested optional URLs for CDC and AMIA references. These were not added. Because the comments were phrased as "if desired," this does not need to block completion.

## Conflicting Suggestions

### Epic-specific wording vs generic 10% rule

Conflict:

- Naveed asked not to refer to the comparator as the "Epic 10% rule" because the rule is generic/configurable.
- Karl suggested adding "Hyperspace (Epic Systems Corporation)."

Current draft mostly follows Naveed by using "10% rule" and only parenthetically noting local EHR/Epic context.

Recommendation: keep "10% rule" throughout. If product context is needed, include one narrow sentence such as: "Our local Epic EHR implementation uses this configurable fixed-change concept for height." Avoid naming the comparator "Epic 10% rule."

### Reference measurement terminology

Conflict or unresolved preference:

- Zak objected to "reference measurement" and wanted emphasis on the accurate clinic measurement.
- The manuscript still uses "reference measurement" language in places.

Recommendation: decide whether "reference measurement" is methodologically necessary. If not, replace with "repeat clinic measurement" or "contemporaneous repeat measurement."

## Recommended Cleanup Checklist

1. Resolve all 13 active comments in the latest DOCX.
2. Accept/reject all tracked changes before submission or circulation.
3. Verify the 10% rule implementation, especially prior-visit timing behavior, or qualify it clearly as a reimplementation.
4. Add or mention the height-delta distribution if it was reviewed.
5. Simplify the opening methods/conceptual-framing paragraphs for clinical readers.
6. Decide globally whether to retain or replace "reference measurement" terminology.
7. Keep generic "10% rule" naming, with only limited local Epic context.
