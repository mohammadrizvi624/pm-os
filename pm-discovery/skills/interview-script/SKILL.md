---
name: interview-script
description: "Create a structured customer interview guide with JTBD probing, following The Mom Test — no leading questions, no pitching, focus on past behavior. Use when planning user/customer interviews, writing an interview or discovery-call script, or preparing to talk to users. Produces a runnable guide plus a note-taking template."
---
# Customer interview script

A runnable guide that surfaces real behavior, not opinions. Follows The Mom Test (Rob Fitzpatrick) — ask about their life, not your idea. Interviews are one source in the Explore stage of continuous discovery; the Product Trio (PM+Designer+Engineer) should run discovery together, with direct access to users — no proxies.

## Inputs
- The research objective and the assumptions/questions this interview must resolve. If personas, hypothesis lists, briefs, or prior notes are attached, read them first.

## Load company context
Read `./company-context/03-users-personas.md` (who you're talking to, their JTBD) and `00-company.md`.

## Method
1. State the objective: the questions to answer, the decision it informs, the assumptions to validate.
2. Build the script in timed sections:
   - Opening (2-3 min) — introduce yourself + purpose (learning, not selling); "no right or wrong answers"; ask to record; confirm time available.
   - Warm-up (5 min) — their role, a typical day/week, how long they've done the activity. Build rapport and context.
   - Core — Jobs to Be Done (15-20 min):
     - Current behavior (past tense, specific): "Walk me through the last time you <did the thing>. What happened? What tools? How long? Who else was involved?"
     - Pains (observe, don't lead): "What was hardest? What have you tried? What happened?"
     - Desired outcomes (their words): "What does 'good' look like? How would you know it's working?"
     - Willingness to pay / priority (skin in the game): "How much time/money do you spend on this today? Have you looked for a better solution? What would you give up to solve it?"
   - Wrap-up (3-5 min) — "Anything I didn't ask that matters? Who else should I talk to?" Thank them; share next steps.
3. Probing techniques: "Tell me more about that," a gentle "Why?" (2-3×), "Can you give a specific example?", "What happened next?", "How did that make you feel?"
4. The Mom Test rules: ask about their life not your idea; the past not the future ("Would you use X?" is useless); talk less, listen more (~80/20); never pitch; chase strong emotions; treat compliments as noise.

## Output
Save to `./outputs/<YYYY-MM-DD>_interview-script_<slug>.md`. Include the full timed script AND a note-taking template:
```
Participant: <name/ID>   Date: <…>
Key jobs: <what they're accomplishing>
Current solution: <what they use today>
Biggest pain: <#1 frustration>
Desired outcome: <what success looks like>
Willingness to pay: <time/money invested or would invest>
Surprise finding: <unexpected>
Follow-up: <next steps>
```

## Avoid
- Leading or yes/no questions; asking users to predict future behavior.
- Pitching the solution; mistaking compliments for validation.
