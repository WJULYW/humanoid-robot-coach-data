# Data for "What Makes a Humanoid Robot a Coach?"

This repository contains the anonymized data used for the statistical analyses in the paper:

> Jiyao Wang, Haozhe Li, Haoyu Ruan, Zhijie Yi, Jinghao Huang, Yanying Zhu, Dengbo He, and Jiangbo Yu. *What Makes a Humanoid Robot a Coach? Understanding Novices' Experiences and Expectations in Resistance Training.* Manuscript under review.

## Study

Forty-eight adults new to structured resistance training took part in a 2 × 2 between-participant Wizard-of-Oz study. A certified fitness trainer teleoperated a Unitree G1 humanoid robot, which coached participants through four dumbbell exercises. The study varied whether the robot could use physical contact (**Contact**: Contact vs. No Contact) and whether the trainer could see the participant's heart rate (**Guidance Basis**: Physiology Guidance vs. Visual Guidance), with 12 participants per condition. Each exercise had a Technique episode followed by a heavier Challenge episode, giving eight episodes per participant and 384 episodes in total.

The study was approved by the Human and Artefacts Research Ethics Committee at The Hong Kong University of Science and Technology (Guangzhou) (protocol: HKUST(GZ)-HSP-2025-0395).

## Files

| File | Rows | Content |
| --- | --- | --- |
| `data/episode_data.csv` | 384 | One row per episode: design variables, episode ratings, and expert-rated Movement Quality. Used for the mixed-effects models (Tables 2–4 and Appendix A of the paper). |
| `data/participant_data.csv` | 48 | One row per participant: condition, background characteristics, and post-session scales. Used for the robustness model with additional covariates (Appendix A) and the post-session analyses (Appendix B). |
| `materials/movement_quality_rubric.md` | | The five-point rubric used to rate Movement Quality. |

The two files are linked by `participant_id`.

## Variables

### `episode_data.csv`

| Variable | Values | Description |
| --- | --- | --- |
| `participant_id` | P01–P48 | Anonymized participant identifier. |
| `contact` | Contact, No Contact | Whether the robot could use physical contact. |
| `guidance_basis` | Physiology Guidance, Visual Guidance | Whether the trainer could view heart rate and individualized heart-rate zones. |
| `exercise` | A1, A2, B1, B2 | A1, seated bent-over bilateral dumbbell reverse fly; A2, seated dumbbell shoulder press; B1, single-arm dumbbell rear-delt row; B2, seated bilateral dumbbell curl. |
| `movement_visibility` | Limited, More Accessible | How directly the trainee can see the working limb and its trajectory (A exercises: Limited; B exercises: More Accessible). |
| `trunk_constraint` | Less Constrained, More Constrained | Extent to which the exercise setup limits trunk motion (exercises 1: Less Constrained; exercises 2: More Constrained). |
| `training_phase` | Technique, Challenge | Technique: light individual load with technique instruction; Challenge: heavier individual load. |
| `execution_position` | 1–4 | Position of the exercise in the participant's session. In the models it was centered and range-scaled as (position − 2.5) / 3. |
| `coaching_experience` | Yes, No | Previous experience working with a personal trainer. |
| `gender` | female, male | Self-reported gender. |
| `comfort` | 1–5 | Comfort and acceptability of the guidance in the episode. |
| `helpfulness` | 1–5 | Perceived support for performing the movement. |
| `judgement_trust` | 1–5 | Trust in the robot's judgement of the current movement. |
| `movement_quality` | 1–5 | Consensus rating of exercise execution by two licensed fitness coaches who were not told the assigned conditions (1 = Poor, 5 = Excellent; see `materials/movement_quality_rubric.md`). |

### `participant_data.csv`

| Variable | Range | Description |
| --- | --- | --- |
| `participant_id` | P01–P48 | Anonymized participant identifier. |
| `contact`, `guidance_basis`, `gender`, `coaching_experience` | | As above. |
| `robot_experience` | 1–5 | Self-rated prior experience with robots. |
| `nars_interaction` | 1–5 | Mean of six adapted Negative Attitudes toward Robots Scale (NARS) items on situations and interactions with robots. |
| `nars_social` | 1–5 | Mean of five adapted NARS items on the social influence of robots. |
| `nars_emotion` | 1–5 | Mean of three adapted NARS items on emotions in interaction with robots (reverse scored). Higher NARS scores indicate more negative attitudes. |
| `touch_aversion` | 1–5 | Mean of the adapted 11-item Social Touch Questionnaire; higher values indicate greater aversion. |
| `trust_propensity` | 1–5 | Mean of the six-item tendency to trust robotic systems. |
| `trust_in_automation` | 1–5 | Mean of the 12-item Trust in Automation scale (items 1–5 reverse scored), completed after the final episode. |
| `perceived_intelligence` | 1–5 | Mean of the five-item Godspeed perceived intelligence scale, completed after the final episode. |

In the robustness model with additional covariates, `robot_experience`, the three NARS subscales, `touch_aversion`, and `trust_propensity` were standardized (z-scores) before entering the model.

## Anonymization

Participant identifiers were reassigned at random and do not correspond to the participant codes quoted in the paper or to internal study records. Names, contact information, dates, age, and free-text responses were removed. Gender and previous personal-training experience are retained because they were used in the analyses.

## Data available on request

Video recordings, interview recordings and transcripts, ECG recordings, and item-level questionnaire responses are not publicly available, as they contain information that could compromise the privacy of research participants. In accordance with the ethics approval, these data are stored on a secure server of the Human-Integrated Systems Lab at The Hong Kong University of Science and Technology (Guangzhou).

Researchers who wish to use these data can contact Dengbo He (dengbohe@hkust-gz.edu.cn) with a brief description of the intended use. Requests are considered in line with the ethics approval and participants' consent, and access is limited to non-commercial research.

## License

The data in this repository are released under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Please cite the paper above when using the data.
