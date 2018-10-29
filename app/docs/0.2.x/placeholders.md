---
title: Placeholders
---

# Placeholders

Resource files often use placeholders in strings to allow dynamic information to be inserted into a string. For example: *"Welcome %{username}, you have $%{balance} in your account".* Qordoba will recognize these placeholders and protect them from being translated, while still allowing the translator to position them as needed in the translated string. Placeholders are also known as “formatting strings”, “format specifiers” or just “specifiers”.

We recognize standard placeholders by default. Exactly what is captured as a placeholder depends on the file format. 


|Placeholders|Exmples|
|---|---|
| %{xxxxx} | Hi %{username} |
| %{{xxxxx}} | Hi %{{username}} |
| {{xxxx}} | Hi {{username}} |
| {xxxx} | Hi {username} |
| %x (x here will be A-Z and a-z only) | Number of %d |
| $x (x here will be A-Z and a-z only) | Number of $x |
