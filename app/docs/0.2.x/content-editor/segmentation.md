---
title: Segmentation Rules
---

# Segmentation 

Qordoba offers three different ways to segment content

 - **Cell-based** (default): our recommended parsing that pulls in content by key if it's a key-based file otherwise splits based on file type
 
 - **Punctuation-based** (for better SmartSuggest results): parses content by full stop markers (periods, question marks, exclamation marks) creating shorter segments of content 
 
 - **ICU**: allows for specifying arbitrary boundary rules based on a regex-like syntax

    For more information, go [here] (http://userguide.icu-project.org/intro)
