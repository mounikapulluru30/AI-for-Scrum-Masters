# 📅 Sprint Planning Experiment: Using ChatGPT to Support Sprint Planning

## 📌 1. Scenario

A Scrum Team is preparing for a new two-week Sprint.

The Product Owner has a prioritized Product Backlog, but the team needs to determine what can realistically be taken into the Sprint while creating a meaningful Sprint Goal.

The Scrum Master wants to explore whether ChatGPT can help the team prepare for Sprint Planning without making the planning decisions on behalf of the team.

## 🎯 2. Objective

Explore how ChatGPT can support Sprint Planning by:

- Helping identify factors the team should consider when selecting work
- Suggesting questions to clarify Sprint Planning inputs
- Helping identify potential risks, dependencies, and constraints
- Supporting discussion around Sprint Goal formulation
- Helping the Scrum Master prepare for an effective Sprint Planning session

The objective is not to use AI to decide Sprint scope or create the Sprint Goal automatically. The Scrum Team remains responsible for making these decisions based on its context, capacity, and understanding of the work.

## 🤖 3. AI Prompt — Sprint Planning Analysis

> Act as an experienced Agile Coach and Scrum Master.
>
> A Scrum Team is preparing for a two-week Sprint. The Product Owner has provided a prioritized Product Backlog, and the Developers need to determine what they can realistically take into the Sprint.
>
> Analyze how ChatGPT could support the Scrum Team during Sprint Planning.
>
> Identify:
> 1. Important inputs the team should consider before selecting work
> 2. Questions the Scrum Master should facilitate during Sprint Planning
> 3. Factors that could affect the team's capacity
> 4. Risks and dependencies the team should discuss
> 5. How ChatGPT could help the team formulate a meaningful Sprint Goal
> 6. What ChatGPT should NOT decide on behalf of the Scrum Team
>
> Do not assume that past velocity alone should determine Sprint scope. Consider capacity, complexity, dependencies, risks, and the team's current context.

## 💬 4. AI Response — Sprint Planning Analysis
Absolutely. This is a strong **practical ChatGPT-for-Scrum-Master experiment** because Sprint Planning is an area where AI can support preparation and facilitation without replacing Scrum Team accountability.

## Sprint Planning: How ChatGPT Can Support a Scrum Team

### 1. Important inputs to consider before selecting Sprint work

The team should look beyond simply asking, **“What did we complete last Sprint?”**

Important inputs include:

| Input                               | Why it matters                                                                             |
| ----------------------------------- | ------------------------------------------------------------------------------------------ |
| **Product Backlog priority**        | Ensures the team works on the most valuable items first                                    |
| **Sprint Goal / product objective** | Helps determine which items belong together around a common outcome                        |
| **Team capacity**                   | Determines how much work the team can realistically handle                                 |
| **Availability of Developers**      | Leave, holidays, training, meetings, onboarding, etc. affect capacity                      |
| **Complexity and uncertainty**      | High-uncertainty items may require more investigation or spikes                            |
| **Dependencies**                    | External teams, APIs, vendors, environments, approvals, etc. can affect delivery           |
| **Technical risks**                 | Architecture, legacy code, integration problems, infrastructure constraints                |
| **Unfinished work**                 | Work carried over from the previous Sprint should be understood before selecting more work |
| **Definition of Done**              | The team must consider the actual effort required to produce a Done Increment              |
| **Current product/team context**    | Production issues, technical debt, changing requirements, team changes, etc.               |
| **Historical data**                 | Velocity or throughput can provide context, but should not mechanically determine scope    |

### Key Scrum principle

**Capacity is not the same as velocity.**

For example, if a team's historical velocity is 30 points but two Developers are on leave, blindly selecting 30 points would be inappropriate.

Likewise, if the team has unusually high capacity but the selected items contain significant technical uncertainty, simply increasing the scope because "capacity is available" may also be risky.

---

# 2. Questions the Scrum Master should facilitate

The Scrum Master shouldn't tell the team what to select. Instead, they should facilitate conversations that help the Developers make an informed decision.

### Understanding the Sprint Goal

* What valuable outcome are we trying to achieve this Sprint?
* What is the most important objective for the Product?
* Which backlog items contribute directly to that objective?
* Are we selecting work because it supports the goal or simply because it is high priority?

### Understanding capacity

* Who will actually be available during the Sprint?
* Are there planned holidays, training, ceremonies, support activities, or other commitments?
* Are there any known production/support responsibilities?
* Is anyone new to the team or taking on unfamiliar work?

### Understanding complexity

* Which items are well understood?
* Which items have significant uncertainty?
* Are any stories too large for the Sprint?
* Do we need a spike or investigation before committing to implementation?

### Understanding dependencies

* Does any item depend on another team?
* Are there external approvals?
* Are APIs, environments, data, infrastructure, or vendors involved?
* Could another team's delay prevent us from achieving the Sprint Goal?

### Challenging assumptions

A particularly useful Scrum Master question is:

> **"What are we assuming right now that could turn out to be wrong?"**

This can expose hidden risks that a velocity-based discussion may miss.

---

# 3. Factors that could affect team capacity

Capacity is much more than the number of Developers multiplied by the number of working days.

Consider:

### People-related factors

* Planned leave
* Public holidays
* Training
* Onboarding new members
* Part-time availability
* Unplanned support responsibilities
* Meetings or organizational commitments

### Technical factors

* Production support
* Technical debt
* Infrastructure work
* Environment instability
* New technology/framework
* Complex integrations

### Organizational factors

* Dependency on other teams
* Approval processes
* Vendor availability
* Business events
* Release constraints

### Team maturity

A newly formed team may have lower predictability than an established team.

Similarly, a team going through a major change may temporarily experience reduced capacity even though the number of Developers hasn't changed.

---

# 4. Risks and dependencies the team should discuss

The team should actively look for things that could prevent the Sprint Goal from being achieved.

### Dependency example

Suppose the team selects:

> "As a customer, I want to receive an OTP so that I can verify my identity."

The work might depend on:

**Application → Authentication Service → SMS Provider**

Even if the Developers have enough capacity, the Sprint could be at risk if the SMS provider integration isn't ready.

### Questions to ask

* What external systems do we depend on?
* Are required APIs available?
* Are test environments ready?
* Do we need another team's support?
* Are requirements sufficiently understood?
* Are there technical unknowns?
* Is there a single point of failure?
* What happens if this dependency is delayed?

The Scrum Master can also help the team distinguish between:

**Risk:** "The API may not be ready."

and

**Dependency:** "We cannot complete the story until Team B provides the API."

That distinction helps the team determine appropriate actions.

---

# 5. How ChatGPT can help formulate a meaningful Sprint Goal

This is where ChatGPT can be particularly useful as a **thinking partner**.

The Scrum Team can provide:

* Product objective
* Top backlog items
* Business value
* Customer problem
* Known constraints
* Dependencies
* Risks

Then ask ChatGPT to identify the common outcome behind those items.

### Example

Suppose the selected items are:

1. Password reset
2. Email verification
3. Account recovery notification

Instead of creating a Sprint Goal such as:

> ❌ "Complete password reset, email verification and notifications."

ChatGPT could help the team recognize the broader outcome:

> **"Enable customers to securely recover access to their accounts without contacting support."**

That is much more meaningful because it expresses the **outcome**, rather than simply listing work.

### Useful ChatGPT prompt

> "Act as an Agile Coach. Based on the following Product Goal, prioritized backlog items, customer problem, dependencies and constraints, suggest 3 possible Sprint Goals. Make them outcome-oriented rather than a list of tasks. Explain how each proposed goal connects the selected backlog items. Do not decide which goal the team should choose."

The Scrum Team can then discuss the suggestions and decide.

---

# 6. What ChatGPT should NOT decide

This is probably the **most important part of the experiment**.

ChatGPT can provide analysis, questions, alternatives and identify potential risks.

But **the Scrum Team remains accountable for the Sprint Backlog and Sprint Goal.**

ChatGPT should **not**:

❌ Automatically decide how many story points the team should take.

❌ Tell the team:

> "Your velocity is 30, therefore select exactly 30 points."

❌ Decide that a particular backlog item must be included.

❌ Make commitments on behalf of Developers.

❌ Determine that the team has sufficient capacity without knowing the real context.

❌ Override the Product Owner's ordering of the Product Backlog.

❌ Estimate work as though its estimate is authoritative.

❌ Decide whether a technical risk is acceptable.

❌ Make commitments regarding external dependencies.

❌ Replace the team's conversation and negotiation.

❌ Turn Sprint Planning into an AI-generated plan that the team simply accepts.

---

# A good mental model

Think of ChatGPT as:

**AI = Facilitator's Thinking Partner**

not

**AI = Sprint Planner**

A Scrum Master could use ChatGPT before or during Sprint Planning to:

**Prepare → Analyze → Question → Challenge assumptions → Generate alternatives → Facilitate**

The Scrum Team then:

**Discusses → Negotiates → Decides → Creates the Sprint Goal and Sprint Backlog**

---

## Practical experiment you can actually perform

Since you're building your **AI-for-Scrum-Master practical experiment portfolio**, I'd mark this experiment complete only after actually running a scenario through ChatGPT.

You could create a hypothetical two-week Sprint with:

* 8–10 Product Backlog Items
* Priority
* Story descriptions
* Estimates
* Team size
* Developer availability
* Known dependencies
* Technical risks
* Planned leave
* Previous Sprint context

Then ask ChatGPT to:

1. Analyze the inputs.
2. Identify capacity considerations.
3. Identify risks/dependencies.
4. Ask Sprint Planning questions.
5. Suggest possible Sprint Goals.
6. **Explicitly avoid selecting the final Sprint scope.**

Then compare ChatGPT's analysis with **your own Scrum Master judgment**.

### The key learning you can demonstrate

> **ChatGPT can improve the quality of Sprint Planning conversations, but it should not replace the Scrum Team's decision-making authority.**

That distinction makes this a much stronger AI/Scrum experiment than simply asking ChatGPT, *"How many stories should we take into the Sprint?"*

## ✅ 5. What AI Did Well

- AI correctly emphasized that Sprint Planning should consider more than historical velocity.
- It identified practical inputs such as capacity, availability, dependencies, risks, uncertainty, unfinished work, and the Definition of Done.
- It provided useful facilitation questions rather than telling the Scrum Master what decisions to make.
- It clearly distinguished **capacity from velocity**.
- It showed how AI could help the team think about an outcome-oriented Sprint Goal.
- It clearly explained what AI should **not** decide on behalf of the Scrum Team.
- It reinforced the idea of using AI as a thinking partner rather than a replacement for Scrum Team decision-making.

## ⚠️ 6. What AI Missed / Areas to Validate

- AI provides useful planning guidance, but it cannot know the team's actual capacity or organizational context without accurate inputs.
- The Scrum Team should validate whether identified risks and dependencies are genuinely relevant.
- AI-generated Sprint Goal suggestions should be discussed and refined by the Scrum Team rather than accepted as-is.
- Historical data such as velocity can provide useful context, but the team should avoid treating it as a fixed commitment.
- The Scrum Master should ensure that AI does not become a substitute for the Developers' discussion and decision-making.
- Any AI-generated recommendation should be validated against the team's actual situation and Scrum principles.

## 🧠 7. Scrum Master Analysis

The AI response provides a useful framework for preparing and facilitating Sprint Planning, but the Scrum Master should not use it as a formula for deciding Sprint scope.

My focus would be on helping the Scrum Team have the right conversations around:

- The Product Goal and desired outcome
- The Sprint Goal
- Product Backlog ordering
- Developer availability and capacity
- Dependencies and risks
- Complexity and uncertainty
- Work that can realistically contribute to a Done Increment

I would use ChatGPT before Sprint Planning to identify questions, challenge assumptions, and explore possible Sprint Goal options.

However, the Developers should determine what they can accomplish, and the Scrum Team should collaborate on the Sprint Goal and Sprint Backlog.

The key responsibility of the Scrum Master is to facilitate an effective conversation—not to use AI to make the planning decisions.

## 💡 8. Key Learning

### 🌱 What I Learned From This Experiment

1. Sprint Planning should consider capacity, context, risks, dependencies, and uncertainty—not just historical velocity.
2. AI can help the Scrum Master prepare better questions and challenge assumptions.
3. ChatGPT can help generate possible Sprint Goal options, but the Scrum Team must decide the final goal.
4. AI should not determine Sprint scope or make commitments on behalf of Developers.
5. The value of AI in Sprint Planning is in improving the quality of the conversation, not replacing the conversation.

## 🚀 9. Final Scrum Master Approach

I would use ChatGPT as a **Sprint Planning preparation and thinking tool**, not as a decision-maker.

My approach would be:

1. Review the Product Backlog and available Sprint Planning inputs.
2. Use ChatGPT to identify potential risks, dependencies, capacity considerations, and questions.
3. Validate those points against the team's actual context.
4. Facilitate discussion around the Product Goal, Sprint Goal, and available capacity.
5. Allow the Developers to determine what work they can realistically accomplish.
6. Use AI-generated Sprint Goal suggestions only as discussion starters.
7. Help the Scrum Team make the final decisions collaboratively.

### 🔑 Key Takeaway

> **AI can help the Scrum Team have a better Sprint Planning conversation, but the Scrum Team must own the decisions.**
