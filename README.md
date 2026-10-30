# Email Triage Agent

A small, heavily commented Python agent that reads a batch of emails and decides for each one whether it is **important** or **not important**, with a one-line reason, in Arabic.

Built for a hands-on workshop, *"How to build an agent"*, so the code is split into four clearly labelled parts that map to the building blocks of any LLM agent:

1. **Connection** to the model (Anthropic API)
2. **Instructions**: the system prompt that defines the agent's behaviour and forces a strict JSON output
3. **Data**: sample emails (in a real app these would come from Gmail)
4. **Agent loop**: goes through each email, calls the model, parses the JSON decision and prints a summary

## Example output (illustrative — the reasons are written by the model and vary between runs)

```
🔴 [مهم] اجتماع غداً الساعة ٩
    └─ السبب: اجتماع عمل يتطلب الحضور وتجهيز التقرير
⚪️ [غير مهم] 🔥 خصم ٥٠٪ على كل شي!
    └─ السبب: إعلان تسويقي لا يحتاج أي إجراء
```

## Run it

```bash
pip install -r requirements.txt
export ANTHROPIC_API_KEY=your-key
python agent.py
```

Change the text in the `SYSTEM` prompt and the whole agent changes behaviour, which is the main lesson of the workshop.

**Author:** Ritaj Albogami
