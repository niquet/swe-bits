# [RFC] Title

**Author:** Maximilian Niquet

**Status:**
- [X]  Draft
- [ ] Skipped
- [ ] Reviewing
- [ ] Approved
- [ ] Rejected
- [ ] Superseded

**Date:** YYYY-MM-DD

## Table of Contents
- [Context]()
- [Problem Statement]()
- [Proposed Solutions]()
- [Implementation Overview]()
- [Remarks and Open Questions]()
- [Summary]()

## Context
- Start with a high-level summary - that way, readers can quickly decide if this is relevant to them or not and whether they should keep reading
- Provide some context - Explain a bit about the current state of the world, as it is right now. This can be a single sentence or a whole chapter, depending on the intended audience

## Problem Statement
- Clearly state the problem/goal - explain why there is a problem and connect it with the user’s/company’s pain, so that motivation is clear
- The better you define the problem or the goal/feature you need to implement, and why you need to do it, the easier all the following steps will be
- Make sure you talk to all the involved parties (e.g., product owner, other developers, and even users) to refine your understanding of the issue you’re about to tackle
- Provide extra details if possible - diagrams, code examples, … → anything that can help the reader get faster to that “aha” moment. Extra points for using collapsible sections, so the central part of the RFC remains of digestible length
- Non-goals - Writing what we don't want or will not be doing in this codebase change can help set the expectations and better define its scope

---

- Document proposing a codebase change to solve a specific problem
- Its main purpose is to find the best way to solve a problem, as a team effort, before the implementation starts
- Structure
  - Title
  - Metadata
    - Status
    - Created at
  - Comments from the team
  - RFC body
    - Problem
    - Implementation
    - Summary
- When to write an RFC
  - If you are introducing a completely new concept
  - If you are altering the project’s architecture
  - If there is more than one obvious way to implement a feature
  - Is there a new library/service you have to pick
- When not to write an RFC
  - Whenever it’s very clear what you must do and doesn’t affect project structure
  - E.g. if you’re dealing with a bug or a relatively simple feature
- Why to write an RFC
  - You will organize your thoughts and get clarity. If you’ve decided to write an RFC, that means you’re dealing with a non-trivial, open-ended problem. Writing things down will help distill your thoughts and have an objective look at them.
You will learn more than if you just jumped into coding. You will give yourself space to explore different approaches and oftentimes discover something you haven’t even thought of initially.
You will crowdsource your team’s knowledge. By asking your team for feedback (hence Request For Comments), you will get a complete picture of the problem you’re solving and fill in any remaining gaps.
You will advance your team’s understanding of the codebase. By collaborating on your RFC, everybody on the team will understand what you’re doing and how you eventually did it. That means next time somebody has to touch that part of the code, they will need to ask you much less questions (=== more uninterrupted coding time!).
PR reviews will go much smoother. Remember that situation from the beginning of this article, when your PR got rejected as "too complex"? That’s because the reviewer is missing the context, and you made a sizeable change without a previous buy-in from the rest of the team. By writing an RFC first, you’ll never encounter this type of situation again.
Your documentation is already 50% done! To be clear, RFC is not the final documentation, and you cannot simply point to it, but you can likely reuse a lot - images, diagrams, paragraphs, etc.

---

- When to write an RFC
  - Whenever a net new system with structured documentation and community is required
  - Or whenever (sustained) team input is required
- When not to write an RFC
  - Work that already has an agreed-upon system
  - Small bugs
  - Other cases in which simple Slack message or referencing existing standards will do
- A thoughtful structure is the bread and butter of writing the RFC as it enhances its readability and impact
  - Metadata: List key stakeholders, timelines and important dates, status, etc.
  - Title: This should be clear and easily identifiable
  - Abstract: AKA a tl’dr; this should succinctly summarize your proposal
  - Introduction: Here’s where you set the context of your proposal
  - Problem statement: This should articulate the issue at hand; why is a proposal even needed in the first place?
  - NOTE: The better and more clear you articulate this problem statement, the easier it will be to write the rest of your RFC
    - Start with a quick summary
    - Give background context
    - Clearly state the problem
  - Proposed solution/recommendation: This is the meat of your RFC
    - Dig into the proposed solution to your problem and get as detailed as you can
    - This section and the one above are where the research you completed earlier will come in handy
    - NOTE: This is a great place to add diagrams and other visual representations
  - Technical details: Are there any special technical considerations to take into account? List that here
  - Implementation plan: Put words into action by detailing your plan of action. Bonus points for suggested timelines in each area
  - Planned impact and benefits: What do we anticipate will occur from building this? And what are the benefits of it
  - Considerations: This is the area to address any other considerations (security, legal, community, etc.)
  - References: This is the place to add references to the research discussed in the last section
- Overall, use clear, simple language when writing to keep everyone on the same page
- Include relevant examples and diagrams will help bring your audience into the conversation and clearly convey ideas or complex concepts
- Make sure the flow of your RFC – the use of headings/subheadings – will help organize your content and increase overall readability
- 

## Purpose and Scope
- After you’ve determined you need an RFC and before you get to work, take a step back and define the purpose and scope of your project
- Start by identifying the problem or need your proposal aims to address
- Consider your audience and stakeholders, understanding their perspectives and requirements
- If you’re part of a wider team, consider how this project fits into the wider product or team goals
- Setting clear objectives and goals that take into account the wider picture ensures that your RFC document remains focused and actionable

## Research
- Thorough research and background information are essential for crafting a well-informed RFC document
  - Gather relevant data,
  - existing standards,
  - and precedents to inform your proposal
- Answer questions before they’re even asked
  - Did another company release a similar project?
  - What do they do right?
  - Does this particular project require a specific set of systems to build?
  - Dig into how those systems work and what the team needs to successfully build it from the ground up
  - Or is there a way to plug and play certain elements?
- Talk to key stakeholders – teammates who will ultimately give feedback or help build the project
  - Run your initial ideas by them
  - Further refine your proposal based on the feedback,
  - shine light on valuable insights,
  - and garner support for your proposal before you’ve even sent it out

## Credits
- R. Golden, "A guide to creating an effective Request For Comments (RFC) document," *HackMD Blog*, 05-Apr-2024. [Online]. Available: [https://blog.hackmd.io/blog/2024/04/05/creating-effective-request-for-comments-rfc-document](https://blog.hackmd.io/blog/2024/04/05/creating-effective-request-for-comments-rfc-document) [Accessed: 15-May-2024]
- M. Sosic, "On the Importance of RFCs in Programming," *Wasp Beta*, 05-Dec-2023. [Online]. Available:[https://wasp-lang.dev/blog/2023/12/05/writing-rfcs](https://wasp-lang.dev/blog/2023/12/05/writing-rfcs) [Accessed: 15-May-2024]
- 
