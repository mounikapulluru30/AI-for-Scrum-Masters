# 📝 Backlog Refinement Experiment: Using ChatGPT to Improve User Stories

## 📌 1. Scenario:

A Scrum Team is preparing for the upcoming Sprint.

During Product Backlog Refinement, several user stories are unclear, too large, or missing important acceptance criteria.

The Scrum Master wants to explore whether ChatGPT can help the Product Owner and Developers prepare better stories for discussion.

## 🎯 2. Objective:

Explore how ChatGPT can assist during Product Backlog Refinement by:

- Identifying unclear or ambiguous user stories
- Suggesting questions for clarification
- Identifying missing acceptance criteria
- Suggesting ways to split large user stories
- Helping the Scrum Team prepare for a more effective refinement discussion

The objective is to use AI as a supporting tool while keeping the Product Owner and Developers responsible for understanding the requirements and deciding what is appropriate.

## 🤖 3. AI Prompt — User Story Analysis:

> Act as an experienced Agile Coach and Product Owner.
>
> Analyze the following user story for a Scrum Team preparing for Product Backlog Refinement:
>
> **User Story:**
> As a customer, I want to reset my password through my registered email address so that I can regain access to my account if I forget my password.
>
> Evaluate the story for:
> 1. Clarity
> 2. Completeness
> 3. Potential ambiguity
> 4. Missing acceptance criteria
> 5. Possible edge cases
> 6. Whether the story appears small enough for a Sprint
> 7. Questions the Scrum Team should discuss during refinement
>
> Do not rewrite the story immediately. First analyze what needs clarification or improvement.

## 💬 4. AI Response — User Story Analysis:
Absolutely. From an **Agile Coach + Product Owner perspective**, this is a reasonable candidate for refinement, but it is **not yet sufficiently detailed to confidently consider it Ready for Sprint Planning**.

### 1. Clarity

**Good:**

- The user/persona is clear: **customer**.
- The desired capability is clear: **reset a forgotten password**.
- The basic mechanism is identified: **registered email address**.
- The business value is clear: **regain account access**.

**What needs clarification:**

- What exactly does “reset through email” mean?
  - Does the customer receive a reset link?
  - A temporary password?
  - A verification code/OTP?
- Is the email address entered by the customer, or is it already known from the login attempt?
- What happens after the customer clicks the reset link?

**Assessment:** 🟢 Generally clear, but the actual workflow needs clarification.

---

### 2. Completeness

The story describes the **intent**, but not enough of the **behavior**.

Important details missing include:

- How the reset request is initiated.
- How the customer is verified.
- What is sent to the registered email.
- How long a reset link/code remains valid.
- Password rules.
- What happens after successful reset.
- Whether the customer can immediately log in with the new password.
- What happens if the email address isn't registered.

So the story is **functionally incomplete** for development and testing.

---

### 3. Potential Ambiguity

Several terms could mean different things to different team members:

| Ambiguous areaQuestions |                                                                      |
| ----------------------- | -------------------------------------------------------------------- |
| “Registered email”      | What if the customer enters an unregistered email?                   |
| “Reset password”        | Does this mean creating a new password or receiving a temporary one? |
| Email                   | What content should the email contain?                               |
| Reset mechanism         | Link, OTP, or temporary password?                                    |
| Security                | How is the reset request authenticated?                              |
| Expiration              | How long is the link/code valid?                                     |
| Password                | What are the password complexity requirements?                       |
| Multiple requests       | What happens if the customer requests several resets?                |

These should be discussed before development begins.

---

### 4. Missing Acceptance Criteria

The story needs acceptance criteria covering at least the **happy path and important failure scenarios**.

For example, the team should establish expected behavior for:

**Happy path**

- Customer requests a password reset.
- Customer receives the reset mechanism at the registered email.
- Customer successfully verifies the request.
- Customer creates a valid new password.
- Password is updated.
- Customer can log in using the new password.

**Failure/security scenarios**

- Email address isn't registered.
- Reset link/code has expired.
- Reset link/code has already been used.
- Invalid or weak new password.
- Reset request is made repeatedly.
- Reset link is tampered with or invalid.
- Customer doesn't have access to the registered email.
- Old password/session behavior after reset.

The exact acceptance criteria should be agreed upon by the **PO, Developers, and relevant stakeholders**, rather than assumed by the Scrum Master.

---

### 5. Possible Edge Cases

The team should consider:

- Customer enters an unregistered email.
- Customer enters an incorrectly formatted email.
- Reset email is delayed/not delivered.
- Customer requests multiple reset emails.
- Customer uses an old reset link after requesting a newer one.
- Reset link expires.
- Reset link is already consumed.
- Customer opens the link on another device/browser.
- Customer enters mismatched passwords.
- Password doesn't meet security rules.
- Customer is already logged in when requesting a reset.
- Customer changes the password and then tries using the old password.
- Account is locked/suspended.
- Potential security issue where the system reveals whether an email address is registered.

That last point is particularly important: the team should consider whether the application should say **“Email not registered”** or provide a generic response such as **“If an account exists for this email, instructions have been sent.”**

---

### 6. Is It Small Enough for a Sprint?

**Probably yes, but this depends on the team's context.**

The story itself sounds like a **reasonable Sprint-sized feature**, assuming the team already has:

- User authentication infrastructure
- Email service
- Password management functionality
- Account/user database
- Existing security mechanisms

However, if the team needs to build the entire email service, authentication mechanism, security infrastructure, UI, backend workflow, etc. from scratch, this could become too large.

The key Scrum question isn't simply:

> “Can this be completed within the Sprint?”

It is:

> **“Can the team produce a usable, Done Increment of this capability within the Sprint?”**

If not, the team may need to **split the work vertically** rather than simply breaking it into technical tasks.

---

### 7. Questions for Refinement

I'd bring these questions to the refinement session:

**User experience**

1. What should the customer see when they select “Forgot Password”?
2. Should the customer enter their email address?
3. What should happen after submitting the request?
4. What should the reset email contain?

**Security**
5\. How is the reset request verified?
6\. How long should the reset link/OTP remain valid?
7\. Can a reset link be used more than once?
8\. Should previous reset links become invalid when a new one is generated?
9\. Should we reveal whether an email address exists in the system?

**Password rules**
10\. What are the password complexity requirements?
11\. Can the new password be the same as the old password?
12\. Should the customer enter the new password twice for confirmation?

**Failure scenarios**
13\. What happens if the email isn't registered?
14\. What happens if the email isn't delivered?
15\. What happens with an expired or invalid reset link?
16\. What happens if multiple reset requests are made?

**Completion**
17\. What should happen after a successful reset?
18\. Should existing sessions/devices be logged out?
19\. What constitutes “Done” for this story?
20\. Are there security, compliance, or audit requirements?

---

## Overall Refinement Assessment

| AreaAssessment      |                                  |
| ------------------- | -------------------------------- |
| Clarity             | 🟢 Good basic intent             |
| Completeness        | 🟡 Needs more behavioral detail  |
| Ambiguity           | 🟡 Several important ambiguities |
| Acceptance Criteria | 🔴 Insufficient                  |
| Edge Cases          | 🔴 Need discussion               |
| Sprint Size         | 🟢 Potentially Sprint-sized      |
| Ready for Planning? | 🟡 **Not yet**                   |

### Agile Coach takeaway

I **wouldn't immediately rewrite this story** in refinement.

Instead, I'd use the session to uncover the **business rules, security expectations, user behavior, and acceptance criteria**. Once those are understood, the PO can refine the story and the team can estimate it.

The most important distinction is:

> **A good user story doesn't need to contain every implementation detail—but the team needs enough shared understanding to know what behavior is expected and what “Done” means.**

This is also a **very good example for your AI-for-Scrum-Masters experiment**, because you can document the original story → AI analysis → team refinement questions → final refined story → acceptance criteria → lessons learned.

## ✅ 5. What AI Did Well?
- AI evaluated the story systematically instead of immediately rewriting it.
- It identified ambiguity around the password reset workflow.
- It highlighted missing acceptance criteria and important edge cases.
- It considered security-related scenarios that could easily be overlooked.
- It correctly recognized that Sprint size depends on the team's existing technical capabilities and context.
- It generated useful questions that could guide the Product Owner and Developers during refinement.
- It emphasized that the Scrum Team should agree on expected behavior rather than relying on assumptions.

## ⚠️ 6. What Needs Human Validation

- AI identified several ambiguities in the password-reset workflow, but the Product Owner and Developers need to determine which behaviors are actually required.
- Security expectations, password policies, reset-link behavior, session handling, and account-security rules need validation against the product's actual requirements.
- The suggested edge cases should be prioritized based on real business, security, and user-impact considerations.
- Whether the story is genuinely small enough for a Sprint depends on the team's existing architecture, capabilities, dependencies, and capacity.
- The team needs to decide which acceptance criteria are essential for the intended product behavior rather than automatically adopting every suggestion from AI.
- The final assessment of whether the story is sufficiently understood for Sprint Planning belongs to the Scrum Team, not AI.

## 🔴 7. Actual AI Weaknesses / Mistakes

No significant factual or Scrum-related errors were identified in the AI response.

The response appropriately distinguished between the user story's intent and the additional details that need clarification. It also correctly avoided simply rewriting the story and instead focused on questions the team should explore during refinement.

The main limitation is that the AI cannot determine the actual product requirements, security policies, technical constraints, or team capacity from the user story alone. These require human and product-context validation.

## 💡 8. Key Learning:
### 🌱 What I Learned From This Experiment?

1. AI can quickly identify gaps and ambiguities that may otherwise be missed during refinement.
2. AI-generated questions can help the Scrum Master prepare for a more productive refinement discussion.
3. More questions do not automatically mean better refinement; the team needs to focus on relevant business and user needs.
4. The Product Owner and Developers must validate and agree on the requirements.
5. AI can support refinement, but it should not replace collaborative conversation within the Scrum Team.
6. A Scrum Master can use AI as a preparation and thinking aid while remaining neutral and facilitative.

## 🚀 9. Final Scrum Master Approach:

I would use ChatGPT before refinement as a **preparation and thinking tool**, not as a replacement for the refinement conversation.

My approach would be:

1. Review the user story with the AI.
2. Use the AI output to identify potential gaps and questions.
3. Discuss the relevant points with the Product Owner and Developers.
4. Allow the team to determine the actual requirements and acceptance criteria.
5. Clarify ambiguities and identify important edge cases.
6. Discuss whether the story is appropriately sized.
7. Ensure there is sufficient shared understanding before the story is considered ready for future Sprint Planning.

### 🔑 Key Takeaway:

> **AI can help us ask better questions, but the Scrum Team must create the shared understanding.**
