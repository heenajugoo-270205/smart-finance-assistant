# 📓 Developer's Diary – AI Collaboration Guide

This file shows sample entries for your **Developer's Diary**. You must document your AI collaboration throughout the project development. Each entry should have:
- **Artifact**: a screenshot, GIF, or snippet of your AI interaction
- **Context**: one-sentence description of your goal
- **Reflection**: analysis of what happened, what you learned, and how you improved the solution

**Key Principle**: You're directing AI like a junior developer - always review, critique, and improve their suggestions.

---

Entry 1 – Choosing Student Budget Theme (Week 8)


**Artifact:** <img width="1909" height="840" alt="image" src="https://github.com/user-attachments/assets/c293b8dc-73c2-4ba5-b23f-c0f27ccd5305" />


**Context:** Selecting the right finance problem to solve.


**My First Prompt:** "What's a good theme for a finance assistant that's unique?"


**AI Response:**


<img width="1067" height="697" alt="image" src="https://github.com/user-attachments/assets/dfa77091-ff30-44cd-aaed-94af345707d1" />
<img width="932" height="624" alt="image" src="https://github.com/user-attachments/assets/587430b6-a141-4268-8e1f-965f0c6447d3" />


**My Second Prompt:** "I'm building a Smart Finance Assistant for my university programming assignment. The project requires: a chatbot personality, RAG retrieval from CSV/documents, one custom tool (calculator/converter), and a Gradio UI.
The suggested themes are: Budget Buddy, Investment Insight, Currency Converter Agent, or Savings Coach.
Can you suggest me which theme i could choose for my programming assignment. I would like to focus on the budget buddy."


**AI Response:**

<img width="945" height="601" alt="image" src="https://github.com/user-attachments/assets/d982c7d1-2941-4424-afa4-31461b8e04ee" />

**Reflection:** My first prompt was too vague and it was not meeting my preference. The options provided by ChatGPT at first did not help me to decide at all. I felt lost and had to reformulate my prompt.

I realised that the AI needed more context. My second prompt included my constraints based on my assignment requirement, the suggested themes from the assignment requirement, my preference which is budget buddy and what i needed.

The AI second response was much better where it recommended the " Student Budget Buddy" with specific features like a relatable chatbot personality, budgeting tips for RAG and a custom budget calculator.

Entry 2 – AI Server Connection Error (Week 8)

**Artifact:** 
<img width="1782" height="592" alt="image" src="https://github.com/user-attachments/assets/795a6096-5b9b-4e1f-955e-19a4407777dd" />


**Context:** Testing the hands-on-ai connection after completing the setup cells.

**The Problem:** When I ran the Connection Test cell, I got a Connection Error. The package was installed correctly and the API key was entered, but the server at `https://ollama.serveur.au` would not respond.

**What I Tried:** 
1. Re-ran the cell multiple times but i got the same error each time.
2. Checked that my API key was correct.

**AI Assistance:** I asked ChatGPT what causes connection errors. It explained that the issue could be: server is down or unreachable, network or internet issues, wrong or missing API,firewall or network restrcitions, wrong server configuration.
<img width="909" height="712" alt="image" src="https://github.com/user-attachments/assets/061abc4b-e3be-4638-a46f-85aae371307b" />
<img width="925" height="557" alt="image" src="https://github.com/user-attachments/assets/14fec166-deda-4a35-9f15-f3aa459d77e9" />
<img width="877" height="380" alt="image" src="https://github.com/user-attachments/assets/b0f89bef-0630-42f8-a349-71be1f250650" />

**My Decision:** Instead of wasting time troubleshooting a server I cannot control, I decided to build a mock chatbot that works without the AI connection. This allows me to continue developing my Student Budget Assistant.



## Foundation Skills Examples

### Entry 1 – Effective AI Prompting for Business Data
**Artifact:** Screenshot of ChatGPT conversation about analyzing spending data.

**My Initial Prompt:** "Help me analyze CSV data with pandas"

**My Improved Prompt:** "I'm building a Smart Finance Assistant. I have a CSV with Date, Amount, Category, Description columns. The Amount has dollar signs that need cleaning. I want to calculate total spending by category and format results for a business presentation. Please write pandas code with clear comments."

**Context:** Learning to write specific, business-focused AI prompts.

**Reflection:** The first prompt gave me generic pandas code. The improved prompt with business context got me professional, commented code that handled data cleaning. I learned that AI needs clear business context and output requirements to give useful results. Now I always include: data structure, business purpose, and desired output format.

---

### Entry 2 – Critiquing and Improving AI Code
**Artifact:** Before/after screenshots of AI-generated spending analysis code.

**Context:** AI gave me complex code that was hard to understand for my transaction analysis.

**AI's First Response:**
```python
df.groupby('Category')['Amount'].agg({'sum','mean','count'}).round(2)
```

**My Critique:** "This code is unclear and doesn't handle dollar signs. Can you make it more readable with business-friendly variable names and add data cleaning?"

**AI's Improved Response:**
```python
# Clean amount data by removing dollar signs
df['Amount_Clean'] = pd.to_numeric(df['Amount'].str.replace('$', ''), errors='coerce')

# Calculate spending metrics by category
spending_summary = df.groupby('Category')['Amount_Clean'].agg({
    'Total_Spent': 'sum',
    'Average_Amount': 'mean', 
    'Transaction_Count': 'count'
}).round(2)
```

**Reflection:** I learned that AI's first response isn't always the best. By asking for clearer variable names and business context, I got much better code. This taught me to always review AI code and ask for improvements rather than accepting the first solution.

---

### Entry 3 – Business Context in AI Interactions
**Artifact:** Screenshot of Gemini generating financial insights from data.

**Context:** I wanted AI to help generate business recommendations from spending analysis.

**My Prompt:** "Based on this spending analysis showing Groceries: $450, Dining: $380, Coffee: $120, Transport: $95, create business insights and savings recommendations that sound professional for a personal finance app."

**AI Response:** Generated specific recommendations like "Consider meal planning to reduce dining expenses" and "Coffee purchases represent 8% of total spending - consider brewing at home."

**Reflection:** When I include business context and specify the audience (personal finance app users), AI generates much more relevant and professional output. I learned that framing requests in business terms gets business-quality responses. Now I always think about who will read the output and what decisions they need to make.

---

### Entry 4 – Data Quality and Edge Cases
**Artifact:** Screenshot of debugging session with Claude about handling messy CSV data.

**Context:** My CSV had negative amounts (refunds) and missing values that broke my calculations.

**My Problem:** "My spending analysis is giving wrong totals because some amounts are negative (refunds) and some cells are empty."

**AI Solution:** Helped me add data validation:
```python
# Handle refunds and missing data appropriately
df_clean = df.dropna(subset=['Amount_Clean'])
positive_spending = df_clean[df_clean['Amount_Clean'] > 0]
refunds = df_clean[df_clean['Amount_Clean'] < 0]
```

**Reflection:** AI helped me think about real-world data issues I hadn't considered. I learned that business data is always messy and I need to ask AI specifically about edge cases like refunds, missing values, and invalid entries. This makes my finance assistant more robust for actual use.

---

## Advanced Integration Examples

### Entry 5 – Combining Multiple AI Tools
**Artifact:** Screenshot showing integration of hands-on-ai chat with pandas analysis.

**Context:** I wanted to create a chatbot that could answer questions about spending data.

**My Approach:** Used AI to help me combine CSV analysis with hands-on-ai chat functionality.

**Key Learning:** AI helped me structure the integration, but I had to understand the business logic to make it useful. The chatbot needed to understand financial concepts, not just execute code.

**Reflection:** Integrating multiple technologies requires understanding how each piece serves the business purpose. AI can generate technical integration code, but I need to guide it toward business value.

---

### Entry 6 – Professional Error Handling
**Artifact:** Code snippet showing error handling for file uploads.

**Context:** I needed my Gradio interface to handle bad CSV files gracefully.

**AI Suggestion:** Generated try/catch blocks with business-appropriate error messages:
```python
try:
    df = pd.read_csv(file.name)
    # Analysis code...
except FileNotFoundError:
    return "Please upload a valid CSV file."
except pd.errors.EmptyDataError:
    return "The uploaded file appears to be empty. Please check your data."
```

**Reflection:** AI helped me think about user experience, not just technical functionality. Good error messages help users understand what went wrong and how to fix it. This is crucial for business applications.

---

## AI Collaboration Best Practices I've Learned

### 🎯 Effective Prompting Strategies
1. **Always provide business context**: "I'm building a finance assistant for..."
2. **Specify data structure**: "My CSV has columns X, Y, Z with these data types..."  
3. **Request professional formatting**: "Format output for business presentation"
4. **Ask for comments**: "Include clear comments explaining the business logic"

### 🤔 Critique Questions I Always Ask
- "Does this handle edge cases like negative amounts or missing data?"
- "Are the variable names clear for a business context?"
- "How would I explain this code to a non-technical manager?"
- "What assumptions is this code making about my data?"

### 🔄 Iterative Improvement Process
1. **Get basic working code** from AI
2. **Test with real data** and find issues  
3. **Ask AI to fix specific problems** with context
4. **Simplify complex solutions** for maintainability
5. **Add business-appropriate formatting** and error handling

### 📊 Business Value Focus
- Always connect code back to business decisions
- Format outputs for non-technical users
- Include actionable insights, not just data summaries
- Consider the end user's needs and context

---

## 📝 Documentation Template for Your Entries

Use this format for consistent diary entries:

```markdown
### Entry [Number] – [Descriptive Title]
**Artifact:** [Screenshot/code snippet/GIF of AI interaction]

**Context:** [One sentence: what you were trying to achieve]

**My Prompt:** "[Your exact prompt to AI]"

**AI Response Summary:** [Brief description of what AI provided]

**My Critique/Improvement:** [How you modified or improved the AI's suggestion]

**Result:** [What you ended up with and why it's better]

**Reflection:** [What you learned about AI collaboration, business programming, or problem-solving]
```

---

✅ **Remember**: Document your AI collaboration throughout your project development. Each entry should show learning and improvement, not just successful interactions. Show how you direct AI like a junior developer to create business-appropriate solutions.

