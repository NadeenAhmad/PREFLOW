# PREFLOW: Open Delegation of Long-Horizon Web Tasks for Blind and Low-Vision Users

This repository accompanies an anonymous submission to The Web Conference 2027 (research track). It contains the **supplementary material**, a **video demonstration**, and the **code** for PREFLOW, a Web agent that blind and low-vision (BLV) users can delegate long-horizon Web tasks, such as online shopping, to.

The repository is anonymized for double-blind review.

## Contents

| What | Where | Size |
|---|---|---|
| Supplementary material | [`supplementary_material.pdf`](supplementary_material.pdf) | 13 pages |
| Code of PREFLOW | [`code/`](code/) (start with [`code/README.md`](code/README.md)) | |
| Figures shown below | [`figures/`](figures/) | |
| Terms of use | [`LICENSE`](LICENSE) | |

**If you have ten minutes:** watch the video, look at the architecture below, then read Section S1 of the supplementary material, which follows one task through every part of PREFLOW.

## The architecture (Figure 1 of the paper)

![Architecture of PREFLOW. A User band at the top, a PREFLOW band in the middle, and a Web band at the bottom. The user sends instructions and messages to the Dialogue Agent and receives the Dialogue Agent's questions, purchase preview, and report. The Dialogue Agent passes the instruction and messages to the Task Router, which assigns a task schema; the Schema-Guided Planning Agent fills the schema's slots and yields the preference beliefs. The preference beliefs and the Evidence Ledger form the explicit memory. The Executive Controller Agent reads the memory, sends Web actions to the Web environment, receives observations, records them in the memory, and passes a proposed product to the Commit Verifier Agent. The Commit Verifier Agent reads the memory, passes the checked product to the Dialogue Agent, receives the user's approval, and performs the final action. Every arrow points in one direction.](figures/architecture.png)

*The PREFLOW architecture for online shopping, shown for a blind user and a driver. Explicit memory stores how observations relate to each preference (Evidence Ledger) and what the agent believes the user prefers (preference beliefs). The Commit Verifier Agent checks the proposed product before the final action. The Dialogue Agent decides when to ask, what to ask, and what to report.*

## Video demonstration

[Watch the demo](https://github.com/user-attachments/assets/5c77f921-16ce-4494-9c83-95021fbd23e8.)

**[Play the video (about 8 minutes)](https://github.com/user-attachments/assets/5c77f921-16ce-4494-9c83-95021fbd23e8)**

The video shows PREFLOW in the BLV study interface: the shop on the left and PREFLOW's panel on the right. The user's messages are scripted (written in advance); the user is neither a study participant nor an AI model. The video was recorded in real time and is not sped up or edited. The shop is WebShop, a research shop; nothing is really bought.

The steps below follow the video in order, so it can also be followed without watching it.

1. The user asks for a black women's coat, classic in style, for a trip to a cold city.
2. PREFLOW answers a general question as advice, asks about missing details such as size and budget, and summarizes the request.
3. PREFLOW searches the shop and reports its progress in a status region. Products whose photos show a different product are not offered.
4. PREFLOW presents the options: what they share, then what sets each apart. The options form a radio group that can be browsed with the arrow keys.
5. PREFLOW reports details that only the photo shows, and says so ("the photo shows …").
6. PREFLOW recommends an option and gives its reasons.
7. PREFLOW describes a product photo for someone who cannot see it.
8. PREFLOW compares products in a table that screen readers can navigate.
9. PREFLOW finds more options that the user has not heard yet.
10. The user's budget drops. PREFLOW rechecks the previously heard options against the new budget.
11. PREFLOW lists the colors of the chosen option and answers several questions asked in one message.
12. The user chooses a size and color. PREFLOW previews the purchase, including the preference that the product page does not confirm, and buys only after the user approves. The purchase is simulated.

### The same kind of task as a still image

![A screenshot of the BLV study's interface. On the left, a WebShop results page shows four folding desks with their prices, colors, and whether they come assembled, and below them is a simulated purchase confirmation for the black folding office desk at $349.99. On the right, PREFLOW's panel shows the conversation: PREFLOW asks for the user's budget and whether the desk should come fully assembled, offers three options with what each meets and misses, describes a desk's photo, rechecks the desks after the user lowers the budget to under 350 dollars, asks whether black or fully assembled matters more, previews the purchase with the unmet preference, and confirms the simulated purchase.](figures/nora_conversation.jpg)

*Nora's (blind persona) task from the paper's introduction in the study's interface (Figure S2 of the supplementary material). Section S1 follows the same task through every part of PREFLOW.*

## Supplementary material

[`supplementary_material.pdf`](supplementary_material.pdf) opens with a reader's guide (Table S1) that answers likely reviewer questions in one line each and points to the section with the details.

| Question | Section |
|---|---|
| What does the explicit memory hold, and how does it change during a task? | S1, Figure S1, Table S2 |
| What does the task look like in the BLV study's interface? | Figure S2 |
| How is each component implemented in WebShop, EComAgentBench, and the BLV study? | S2 |
| Does PREFLOW see the benchmarks' goals, rewards, or scripted answers? | S2.3 |
| Why WebShop and EComAgentBench? What does a recorded run look like? | S3 |
| Where do the gains come from, and do they survive a weaker LLM and long tasks? | S4.1 to S4.3 |
| How large is the uncertainty? | S4.4 |
| Is the EComAgentBench gain due to the LLM? | S4.5 |
| Can a user who cannot see the page trust PREFLOW's report? | S5 |
| BLV study: participants, procedure, interfaces, questionnaires, and further results | S6 |
| What changes for other tasks, and what are the threats to validity? | S7 |

## Code

[`code/`](code/) contains PREFLOW and the scripts that run it on WebShop and EComAgentBench, with the settings used in the paper. The key settings are also listed in Table S5 of the supplementary material.

## Results and data

The paper and the supplementary material report all results. The per-task outputs of the benchmark runs (WebShop and EComAgentBench) will be released with the code upon acceptance. From the BLV study, the paper and the supplementary material report averages and each participant's differences; session logs and questionnaire answers are not shared to protect the participants' privacy.

## Terms of use

This repository is provided for peer review only. All rights are reserved until publication; the code and materials will be released under an open license upon acceptance. Please see [`LICENSE`](LICENSE).
