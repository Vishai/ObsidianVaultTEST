# Prompt Engineering

## Overview

Prompt engineering is the practice of designing effective inputs for large language models to achieve desired outputs. It's both art and science - requiring understanding of model capabilities, task structure, and iterative refinement.

## Key Principles

### 1. Clarity and Specificity
Vague prompts yield vague results. Be explicit about:
- What you want
- Format of desired output
- Constraints and requirements
- Context needed

### 2. Examples Are Powerful
Few-shot learning works remarkably well. Provide 2-3 examples of desired behavior.

### 3. Think Step-by-Step
Breaking complex tasks into steps improves accuracy dramatically. Use phrases like "Let's approach this systematically" or "Think through this step by step."

### 4. Role Assignment
Assigning an expert role can improve quality: "As an experienced software architect..." or "As a constitutional scholar..."

### 5. Iterative Refinement
First prompt rarely optimal. Test, analyze, adjust.

## Advanced Techniques

### Chain-of-Thought Prompting
Encourage reasoning process visibility:
```
Solve this problem and show your reasoning at each step.
```

### Constitutional AI
Embed principles and constraints:
```
Provide analysis while adhering to: [principles]
```

### Tree of Thoughts
Explore multiple reasoning paths:
```
Generate three different approaches, then evaluate each.
```
### Meta-Prompting
Use LLM to help design better prompts for specific tasks.

## Common Patterns

**Information Extraction**
```
Extract [specific information] from the following text and format as [structure].
```

**Content Generation**
```
Write [content type] about [topic] for [audience] with [tone/style].
```

**Analysis and Reasoning**
```
Analyze [subject] considering [factors]. Provide insights on [aspects].
```

**Translation and Transformation**
```
Convert [input format] to [output format] while maintaining [properties].
```

## Pitfalls to Avoid

1. **Over-specification**: Too many constraints can box in creativity
2. **Assumption of Knowledge**: Model doesn't know what it doesn't know
3. **Prompt Injection**: If using user input, sanitize carefully
4. **Ignoring Context Window**: Manage information density

## Personal Discoveries

- Temperature settings matter more than expected
- System prompts set crucial behavioral patterns
- Negative examples ("don't do this") surprisingly effective
- JSON mode useful for structured outputs

## Tools & Resources

- Anthropic's Prompt Library
- OpenAI's Prompt Engineering Guide
- Personal prompt template collection

---
*Related: [[llm_agents|LLM Agents]] | [[model_comparison|Model Comparison]]*
