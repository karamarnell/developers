---
title: Automating Workflows
---

#Can I automate my workflows within Qordoba?

Yes. Qordoba’s Automations are a combination of rules and actions that are defined between two workflow steps.

Automations help to improve the speed, efficiency, and performance of your localization processes.

To create a new Automation, head to the “Workflow” tab on the left-hand sidebar of your project in Qordoba and click on “Automations.”

Click “Add New Automation” and name your Automation.

Then, specify between which workflow steps you would like your Automation to apply. Please note that our automations always move forwards, not backwards, to prevent an infinite loop of data.

Our automations are comprised of “if, then” statements, defined as **Rules** and **Actions**.

To customize your **Rules**, you first set the boundaries of your rules by specifying if “all” or “any” of your rules apply.

Then, select from the following dropdowns:

  - **SmartSuggest match rate** is [greater or equal to], [less or equal to], [greater than], [less than], or [is] a percentage you specify
  - **Target language** is [one of] one or more languages that you specify
  - Pushed by [one of] any number of members on your team
  - **CM match** is [greater or equal to], [less or equal to], [greater than], [less than], or [is] a percentage you specify
  - **CM key match** is [greater or equal to], [less or equal to], [greater than], [less than], or [is] a percentage you specify

You can combine any number of rules within the **Rules** section.

To customize your **Actions**, select from the following dropdown:

  - **Push SmartSuggest** through the workflow step you defined
  - **Save CM** at the workflow step you defined (note: the TM will be matched by source)
  - **Push CM** through the workflow step you defined (note: the TM will be matched by source)
  - **Push target segment** through the workflow step you defined
  - **Save target segment** at the workflow step you defined
  - **Save CM (key first)** at the workflow step you defined (note: the TM will be matched by key)
  - **Push CM (key first)** through the workflow step you defined (note: the TM will be matched by key)

You can compound both “move to” and “save at” actions.

**Example Automations:**

For the purposes of this article, we will assume a 5-step workflow consisting of Development, PM Review, Translation, Editing, and Final Review.

If I want to automatically push all 100% Translation Memory matches from Development to Final Review, bypassing the PM Review, Translation, and Editing steps, I would create the rule as follows below:

**insert image here**

If I want to further whittle this automation down to target only my Korean segments, I will add a second rule to my automation:

**insert image here**

If I want to push all segments that are 100% matches based on key, I would create the following automation:

**insert image here**

If I want to push all segments pushed by my PM in the PM Review step to Final Review, I can create this automation rule:

**insert image here**

If I want to save all Korean segments that are 100% Translation Memory matches at the PM Review step, I will create the following automation below:

**insert image here**

To view a list of all of your automations, head back to the Automations section within the Workflow tab.

You can edit, duplicate, make inactive (or active), or delete your Automations by clicking on the gear icon at the right of the Automation.

**insert image here**






