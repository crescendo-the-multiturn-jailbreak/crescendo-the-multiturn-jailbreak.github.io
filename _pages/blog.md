---
layout: default
permalink: /
title: blog
nav: true
nav_order: 1
pagination:
  enabled: false
  collection: posts
  permalink: /
  per_page: 5
  sort_field: date
  sort_reverse: true
  trail:
    before: 1 # The number of links before the current page
    after: 3 # The number of links after the current page
---

<div class="post">

{% assign blog_name_size = site.blog_name | size %}
{% assign blog_description_size = site.blog_description | size %}

{% if blog_name_size > 0 or blog_description_size > 0 %}

  <div class="header-bar">
    <h1>{{ site.blog_name }}</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>
  {% endif %}

  One of the challenges of developing ethical LLMs is to define and enforce a clear boundary between acceptable and unacceptable topics of conversation. For example, an LLM might be trained to avoid engaging in discussions about violence, hate speech, or illegal activities. However, this does not mean that the LLM is incapable of generating such content, as it might have learned relevant words and phrases from its large-scale training data. Rather, the LLM is expected to refuse or deflect any attempts by the user to steer the conversation towards the prohibited topics. This creates a discrepancy between the LLM's potential and actual behavior, which can be exploited by malicious users who want to elicit unethical responses from the LLM through what are known as jailbreak attacks. These attacks aim to bypass the ethical boundaries set by these models. In other words, they aim to narrow the gap between what the model can do and what it is willing to do. 
  
{% include figure.liquid loading="eager" path="assets/img/bothComp.gif" title="chatGPT (GPT-4) output with and without Crescendo" class="img-fluid rounded z-depth-1" %}
{% include figure.liquid loading="eager" path="assets/img/cresFin.gif" title="Crescendo chatGPT (GPT-4) output" class="img-fluid rounded z-depth-1" %}

We introduce Crescendo, a novel jailbreak attack method. Unlike previous techniques, Crescendo is a multi-turn attack that starts with harmless dialogue and progressively steers the conversation toward the intended, prohibited objective. Crescendo exploits the LLM’s tendency to follow patterns and to focus on recent text, particularly text it has generated itself. The figure above illustrates an example of Crescendo in action against state-of-the-art models like ChatGPT and Gemini Ultra. It demonstrates that while the model refuses to engage when directly asked about the prohibited objective, it provides a detailed response when approached with the Crescendo technique. We have evaluated Crescendo across various state-of-the-art LLMs and have achieved strong performance in a range of tasks across different categories such as illegal activities, hate speech, and misinformation, among others. For more details, please refer to our paper “Great, Now Write an Article About That: The Crescendo Multi-Turn LLM Jailbreak Attack”. 
</div>
