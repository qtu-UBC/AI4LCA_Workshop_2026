# AI4LCA Workshop 2026: Deriving Actions for Decarbonization from Verifiable LCAs
<p align="center">
  <img src="workshop materials/Climate Pledge Arena.jpg" alt="Reception at Climate Pledge Arena" width="1000">
</p>

**Disclaimer: The following summary is generated using AI tools (e.g, ChatGPT, Google Gemini) and revised by workshop organizers**

## *TL’DR*

The field of AI-assisted Life Cycle Assessment (LCA) has shifted the core challenge from *automation* to **verification**.

The consensus across the workshop and practitioner survey is that ensuring credibility and quality in AI-assisted LCAs requires a focus on:
- **Validation**: Outputs must be evaluated across three dimensions: Procedural Quality (ISO conformity), Empirical Validity (plausibility), and Technical Correctness (proper tool usage).
- **Context and Judgment**: Practitioner decisions are highly nuanced and context-dependent, leading to significant variability in results that AI alone cannot resolve.
- **Scalable Oversight**: To validate the expected high volume of AI-generated LCAs, the community must move beyond manual review by developing a groundtruth dataset of expert reasoning. This dataset will allow for automated validation, embedded uncertainty and sensitivity analysis, and the flagging of unconventional choices to strategically focus human oversight where it matters most.
- **Human Responsibility**: Responsibility and liability for LCA declarations ultimately remain with human experts, not the AI tool.

## Day 1 Highlights
### Dr. Sangwon Suh’s Keynote Speech
Dr. Suh positioned AI and LCA at an inflection point where the central challenge has shifted from whether to use AI to how to evaluate its outputs responsibly, using the Tiangong Initiative's large-scale automated LCI dataset generation as evidence that AI fundamentally transforms LCA infrastructure from static to dynamic while raising critical quality and trust questions. He argued the field is transitioning from speed-focused automation to precision engineering, acknowledging that despite technical improvements through prompt engineering, RAG, fine-tuning, and multi-agent workflows, the community faces a "ground truth paradox" where even human experts show ±20% or greater variability due to methodological choices rather than arithmetic errors—meaning AI cannot resolve disagreements the field hasn't settled over decades. Suh proposed reframing evaluation objectives away from forcing convergence to single answers toward defining boundaries of plausible methodological choices across three domains: procedural quality (ISO compliance), empirical validity (physical plausibility), and technical correctness (proper tool usage), operationalized through synthetic Q&A datasets from ISO standards, property-based validation checks, machine-readable goal and scope definitions, structured audit trails, and strategically focused human oversight on high-impact decisions. He concluded that the historical ISO emphasis on consistency over accuracy can now be revisited given modern computational capacity that enables embedded uncertainty analysis and scenario distributions, but cautioned that as LCA scales through AI, evaluation methods must evolve beyond pen-and-paper reviews to leverage computational resources, ultimately aiming not just for faster LCAs but for credible, defensible measurements that support real decarbonization decisions. <br>
[**Link to Dr. Suh's slides**](https://github.com/qtu-UBC/AI4LCA_Workshop_2026/blob/main/workshop%20materials/AI4LCA_Suh_keynote_public.pdf)

### Key Takeaways from Panel Discussion
- ISO compliance alone does not guarantee quality; validation must go beyond procedural conformity.
- Task-specific AI applications are currently more mature and defensible than fully autonomous end-to-end systems.
- Responsibility and liability remain human, even in AI-assisted systems.
- Automation must be evaluated holistically to avoid shifting bottlenecks to review stages.
- Open, structured, and interoperable data infrastructure is foundational to trustworthy AI-LCA.
- Uncertainty and sensitivity analysis are promising areas for AI-enabled enhancement of LCA rigor.
- Standards may need to evolve toward outcome-based requirements rather than prescriptive methods.

### Key Takeaways from Open Discussion
  - **Focus on Guardrails:** The discussion has decisively shifted from whether to use AI to establishing clear guardrails and defining the necessary level of documentation and review based on the AI's scope (narrow, task-specific function vs. full end-to-end model generation).
  - **Uncertainty and Sensitivity as Core Requirements:** All AI-assisted LCAs should be required to include uncertainty and sensitivity analysis, especially in areas with ambiguous modeling choices (e.g., allocation method). AI should be used to run multiple plausible options, quantify outcome sensitivity, and flag high-impact decisions for human review.
  - **Validation Beyond Compliance:** ISO compliance is necessary but insufficient. Validation frameworks must go beyond formal procedural alignment to also address **numerical correctness**, interpretability, traceability, and model robustness.
  - **Minimum Documentation Standards:** Documentation must clearly support transparent reasoning trails, explicitly identify modeling assumptions, and indicate where the AI made interpretive decisions, while also managing the risk of the automation accelerating modeling but simultaneously overburdening the human review process.
  - **Responsibility is Human:** Responsibility and legal liability for the final LCA declaration ultimately rest with human experts, not the AI tool. This reinforces the need for "human-in-the-loop" architectures.
  - **Acceptable Risk:** The community must define an *acceptable level of modeling error* in exchange for the benefits of scalability, shifting the focus from demanding perfection to establishing explicit error thresholds and escalation rules for high-risk cases.
  - **Data is a Constraint:** The performance of AI-assisted LCA is fundamentally constrained by the lack of **open, well-structured LCI datasets**. Community collaboration on data transparency is critical.
  - **Evolving Standards:** Existing ISO standards may not be fully AI-ready. Future revisions should focus on **outcome-based criteria** (demonstrating traceability, reproducibility, and uncertainty characterization) rather than prescriptive methods.

## Day 2 Highlights
### Research Presentations
The three presentations showcase a significant potential for scaling LCA generation and validation through the use of AI and agent-based systems. **Below are the insights summarized by the notetaker (i.e, not the viewpoints from the presenters)**: <br>
*Potential for Scaling LCA Generation*
- **Process Flow Graph Generation ([SpiderGen](https://arxiv.org/abs/2511.10684))**: The project is directly focused on generating Process Flow Graphs (PFGs) "at scale" by leveraging the world knowledge and reasoning models of Large Language Models (LLMs), even when starting with sparse and noisy public data.
- **Scalable PCF Modeling (Trace2Cradle)**: This approach aims to achieve "scalable PCF modeling without sacrificing granularity" by digitizing expert heuristics into a multi-agent framework. 
- **Agentic, Evidence-Grounded LCI Assembly (Sustainable Electronics)**: This work treats inventory building as an iterative, multi-agent workflow that uses a structured “data abstraction” to enforce completeness, and leverages multimodal public evidence (e.g., teardowns/specs/images) plus similarity-based estimators (kNN) to fill gaps and produce fast, budgeted results with quantified uncertainty.
  
*Potential for Scaling LCA Validation*
- **Generating a consistent “reference” PFG**: Both SpiderGen and Trace2Cradle have the potential to generate a reference PFG for a given Product Category Rule (PCR). Such reference PFGs would explicitly encode all required processes and linkages—minimizing subjective omissions—while still allowing controlled customization where the PCR permits flexibility. This has an important implication for strengthening PCR specification, for example by supporting the development of Complementary PCRs (c-PCRs): specialized guidelines that supplement broader “main” or “core” PCRs. For scaling LCA validation, these reference PFGs provide a machine-checkable benchmark that enables automated completeness and conformance checks across, rather than relying on manual review.
- **Performing embedded, evidence-linked validation checks**: The approach developed for sustainable electronics LCAs has the potential to support validation at scale by building review checkpoints directly into the workflow—checking structural completeness against the underlying abstraction, linking each modeled choice to supporting evidence (e.g., observed through direct retrieval from public records vs inferred from statistical estimation), propagating uncertainty via neighbor-based estimates, and using feature-driven emission-factor matching to reduce subjective proxy selection—thereby enabling automated flagging and tiered audits instead of manual, case-by-case review.

### Key Takeaways from Panel Discussion
*Framing the Baseline & Validation Categories*

| Question                                                                                                                                          | Key Insight / Answer                                                                                                                                                                                                                                       |
| :------------------------------------------------------------------------------------------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **What are two key aspects of modeling assumptions to verify in an LCA report?**                                                                  | The **functional unit** (including technical performance and reference flows) and **recycled content** or **allocation decisions** (subdivision) are critical checks. Inventory data and ISO standards conformance are also key.                           |
| **How do examples of verification fall into the three validation categories (Procedural Conformity, Empirical Validity, Technical Correctness)?** | The **Functional Unit (FU) check** was noted to potentially overlap all three categories. **Inventory data** is primarily Empirical but can overlap with Technical Correctness. **Bill of Materials (BoM) completeness** is a Procedural Conformity check. |
| **What is the single largest source of ambiguity when validating empirically?**                                                                   | Ambiguity of **what the product is** (e.g., defining a heat pump or the level of input granularity of BoM), **data quality** (e.g., poor geographic representation of a unit process flow), and **uncertainty in key parameters** (hotspots).              |

*Ground Truth Data & AI's Role*

| Question                                                                               | Key Insight / Answer                                                                                                                                                                                                                        |
| :------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **How do you define what should be considered 'ground truth' data?**                   | Ground truth must be **transparent** (trace of calculations), **verifiable, representative, and consensus-based**. It should also be within a **credible range of sources** and aligned with technical standards and procedural conformity. |
| **What are the key features for an automated ground truth data generation pipeline?**  | AI should be used to **point out where** it is most valuable to gather primary data and to **gather a wide range** of data. It can also run statistical analysis at scale to provide guidance on data quality issues.                       |
| **What is the human's role in automated ground truth collection?**                     | The human must be an **expert in the domain** to build guardrails, **own the product carbon footprint (i.e., responsibility)**, and do a **spot-check on AI-escalated red flags** (not every single assumption).                            |
| **Under what circumstances will you trust the validation result from an AI workflow?** | Trust is based on an **auditable trace of reasoning** and complete **transparency** in the approach and data. A system needs a rigorous methodology, with all assumptions and emission factors associated with a ground truth database.     |
| **Who should own, maintain, and govern the ground truth database?**                    | The consensus suggests that it should not be in the private domain. A **non-profit organization** structure, learning from other domains like OpenStreetMap, was suggested.                                                                 |

### Groundtruth Data Creation
The session was structured around a sequence of concrete steps designed to build consensus on the criteria and process for generating a high-quality groundtruth Question-Answer (QA) dataset for AI-assisted LCA validation.

**Defining Core Principles ("Tenets"):**
- Attendees started with a discussion on the **"tenets"** (core principles) for accepting groundtruth QA data, which guided the initial quality check.
- The focus was on ensuring QA pairs were **reasonably nuanced**, **sufficiently specific**, had a **single interpretation**, and centered on a **modeling choice** (rather than a trivial or common fact).

**Developing an Evaluation Rubric:**
The group then moved to defining an **evaluation rubric** for data quality. This resulted in distinct sets of metrics for **Question Quality** and **Answer Quality**.

**Applying the Rubric to Generate New Data:**
After establishing the quality criteria, attendees organized into breakout groups to **create new groundtruth QA data** in specific areas of LCA methodology, such as:
- Input contribution analysis.
- Model results validation.
- Temporal and spatial resolution.
- Handling multifunctional processes and allocation methods.

**Collective Data Input and Evaluation:**
- Attendees **filled out their newly created QA pairs in a shared Google Sheet**.
- The data from the sheet was then used to **populate a Google Form via Apps Script**, allowing attendees to apply the consensus-based evaluation rubric and evaluate each other’s generated groundtruth QA pairs.

### We wrapped up the workshop with a brainstorming session on “What’s next?” ([survey result](https://github.com/qtu-UBC/AI4LCA_Workshop_2026/blob/main/workshop%20materials/scaling_groundtruth_data_creation_with_ai_-_interactive_brainstorm.pdf)) 
- **How AI can help scale groundtruth data creation**: Use AI to extract/standardize evidence, generate diverse scenarios, and codify decision rules while humans curate and validate the critical choices.
- **Virtual methods/tools to keep it going remotely**: Participants want a lightweight collaboration stack (Zoom/Notion) plus shared repositories (GitHub) and common libraries/scenario sets to coordinate work.
- **Challenges (ranked)**: The biggest barriers are data quality/accuracy, time/budget limits, and limited access to diverse data sources (with technical complexity and engagement also noted).
- **Best strategies to improve virtual collaboration (ranked)**: Priorities are clear guidelines/training, AI-assisted collaborative annotation platforms, and automated quality checks—supported by regular workshops and contributor recognition.
- **One-word opportunity signal**: The dominant opportunity framing is “scale/speed/efficiency/consistency,” with some concern signals also present.
- **Support/resources people need**: Respondents most want training, prompt/answer validation support, open/shared data infrastructure, community communication channels, and more structured co-working sessions. 

## Call for Actions
- **Scale up groundtruth data generation**: We must move beyond simply acknowledging practitioner variability and begin to systematically document the expert reasoning that underpins it. Here, AI can play a practical scaling role—not by replacing expertise, but by accelerating it: assisting with drafting structured “decision + rationale” records from practitioner inputs, normalizing terminology, extracting evidence links, and proposing candidate QA pairs or rubric labels that experts can quickly verify and refine. We urge the LCA community—researchers, practitioners, and technology developers—to collaborate on building this essential dataset, using AI-enabled workflows to reduce the time burden per contribution while keeping humans firmly in charge of what counts as defensible practice. It is the critical step needed to prepare for the future and ensure that the next generation of LCA modeling is not only powerful but also trustworthy. <br>
<p align="center">
  <img src="workshop materials/Illustration of a synthetic QA groundtruth data generation workflow.png" alt="Illustration of a synthetic QA groundtruth data generation workflow" width="800">
  <br>
  <em>Illustration of a synthetic QA groundtruth data generation workflow</em>
</p>

- **Build platform for collaboration**: Our experiment approach (Google Sheet + App Script -> Google Form) may not be scalable to meeting the workload from the large crowd-sourcing effort by the entire LCA community. Therefore, we need to build a platform that is accessible to all to contribute groundtruth data, with transparency and proper data governance structure.
- **Reduce ambiguity in inventory modeling**: Explicitly defined specifications for inventory data and models (example here) can enable AI to efficiently check structural completeness and rule conformance (e.g., required fields, unit/flow consistency, mandatory processes, and allowable substitutions) before human review. Similarly, create a “reference model” that explicitly encodes all required processes and linkages for a given product category, has an important implication for scaling LCA validation. These reference models provide a machine-checkable benchmark that enables automated completeness and conformance checks.
- **Standardize agentic workflow development for LCA applications**: Agentic workflows are expected to be the core of the next generation LCA applications, therefore, it is important to standardize how we design, evaluate and update them. 


### For more details, please read the full summary [here](https://docs.google.com/document/d/1empRD6m71BJ8kgIowzI8YblMx21TuBwQeNZBzh3zfBM/edit?tab=t.0) 

-----------
## [Archived] Overview
In an era where artificial intelligence (AI) is increasingly integrated into life cycle assessment (LCA), verifying the integrity and trustworthiness of LCA results has become paramount. This verifiability is the foundation for deriving actionable solutions from LCA to decarbonize business operations, product manufacturing, and supply chain networks through data-driven prioritization and targeted interventions.

We welcome participants from academia, LCA/sustainability consulting firms, AI solution providers, industrial associations and many other groups of the broad LCA/sustainability modeling community, to address this critical challenge. Together, we will explore standardized AI solutions that will transform how we validate LCA and derive actionable insights- making it faster, more consistent, and significantly more scalable. 

This workshop’s conceptual focus examines how verifiability serves as a cornerstone for credible LCA studies and how aligning AI-driven analyses with established standards (such as ISO 14040/44) can build stakeholder trust. Attendees will conduct focused discussions on the best practices in validation and transparency, as well as the definition of actionability in the context of LCA/carbon accounting.

Key outcome of the workshop includes (1) developing a template that captures core reasoning steps in LCA model construction and review (e.g., boundary setting, dataset selection, cutoff rules), (2) developing a small “golden dataset” (i.e., a curated set of LCA modeling questions with expert-annotated answers) for LCA validation


## Registration

This **in-person only** workshop is free to attend, there will be no virtual attendance option. Attendees need to cover their own travel expense.

**Registration Closed**

## Date and Location
**Date:** February 2-3, 2026 (Monday & Tuesday) <br>
**Location:** 05.301 in Amazon DAY 1 building (Room 301 on 5th floor at 2121 7th Ave, Seattle, WA 98121) <br>
- Please note that All external guests (i.e., non-Amazon employees) will need to check in at the reception desk and **provide physical government-issued photo ID or Passport**.
- Point of contact onsite: Nicole Nakashima (Exectuive Assistant I)
- [**Chatham House Rule is enforced in this workshop**](https://www.chathamhouse.org/about-us/chatham-house-rule)

## Agenda
### Keynote Speaker
Dr. Sangwon Suh (Tsinghua University): *From theoretical scale to precision engineering in sustainability data*

### Research Presentations
- SpiderGen: Towards Procedure Generation from Carbon Life Cycle Assessments with Generative AI (Anu Sitaraman, Carnegie Mellon University)
- Trace2Cradle: Building Infrastructure for Reliable Carbon Footprinting (Jinliang Xie, Tsinghua University)
- Designing Sustainable Electronics using AI-Driven LCA (Dr. Vikram Iyer, University of Washington & Amazon)

### Panelists
- Day 1: Andrew Dumit (Watershed), Zaid Thanawala (Amazon), Susan Sanchez (UL), Julie Rapoport (Google)
- Day 2: Erika Odmark (Muir.ai), Jeremy Gregory (MIT), Bogachan Gungor (Amazon), Valentina Prado (Sphera)

### Focused Discussions
#### [Discussion #1] Evaluating AI-Assisted LCA & PCF: procedural aspects and standard conformity
- Refine key decision points distilled from ISO 14044 to determine which are most relevant for AI agents versus human practitioners.
- Develop consensus-based quality criteria (rubrics) to assess the performance of AI on these decision points, focusing on reliability, transparency, and relevance.
- Establish standardized evaluation template and checklist to facilitate AI-led and/or human-led verification of procedural and methodological quality.
- Define documentation requirements to ensure traceability of AI decisions, prompts, and data sources.
- Define standard protocol for Goal and Scope statement for contextual embedding of decisions.

#### [Discussion #2] Define validation dataset for common LCA modeling assumptions
- Format of groundtruth data: We will focus on "Question-Answer" (QA) pairs
- Define tenets to determine when a particular QA pair is acceptable as groundtruth data. This is crucial for maintaining the quality of the groundtruth data
- Explore key categories of LCA modeling practices for which we need groundtruth data
- Develop evaluation matrix for evaluating the quality of the generated QA pairs

### Day 1 Schedule

| Time | Session |
|------|---------|
| 08:30-09:30 | Breakfast & Networking |
| 09:30-09:50 | Welcome and Opening Remarks |
| 09:50-10:20 | Keynote |
| 10:20-11:00 | *Coffee Break* |
| 11:00-11:45 | Panel Discussion #1 (Moderator: Dr. Sangwon Suh, Tsinghua University)|
| 11:45-13:15 | *Lunch* |
| 13:15-16:15 | Focused Group Discussion #1: Solution Development |
| 16:15-16:45 | *Coffee Break* |
| 16:45-17:30 | Focused Group Discussion #1 Results Sharing and Improvement |
| 18:00-20:30 | Private welcome reception at Climate Pledge Arena ([**RSVP**](https://forms.gle/oLTehkG2ErbmN6Jy8) preferred by Friday, January 30, 2026) |

### Day 2 Schedule

| Time | Session |
|------|---------|
| 08:30-09:30 | Breakfast & Networking |
| 09:30-10:30 | Research presentations |
| 10:30-11:00 | *Coffee Break* |
| 11:00-11:45 | Panel Discussion #2 (Moderator: Dr. Qingshi Tu, University of British Columbia & Amazon) |
| 11:45-13:00 | *Lunch* |
| 13:00-16:00 | Focused Group Discussion #2 Solution Development |
| 16:00-16:15 | *Coffee Break* |
| 16:15-17:00 | Focused Group Discussion #2 Results Sharing and Improvement |
| 17:00-17:15 | Closing Remarks |
