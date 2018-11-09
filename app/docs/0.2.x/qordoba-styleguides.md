---
title: Introducing Qordoba Styleguides
---

# Introducing  Styleguides

Define you brand's writing style. Qordoba's Artificial Intelligence will analyze content from all your writers to help you achieve a consistent voice across all your content.


###Brand
If your brand was a person, how would you want them to be described? With the sliders below, you'll define a full personality profile for your brand based on the Big Five personality traits used by psychologists: openness, conscientiousness, extraversion, agreeableness, and emotional range. Qordoba’s AI will analyze all of your copy and give you insight into how your brand is likely to be perceived vs. how you want it to be perceived.


- `Openness`:   Inventive/Curious => Consistent/Cautious

- `Conscientiousness`: Efficient/Organized => Easy-going/Careless


- `Extraversion`: Outgoing/Energetic => Solitary/Reserved


- `Agreeableness`: Friendly/Compassionate =>  Challenging/Detached


- `Emotional range`:  Sensitive/Nervous =>  Secure/Confident




###Voice
Voice is the underlying character of how your brand speaks to its customers. Keep in mind that voice is different from tone. While your tone might change with context (depending on the emotional state of your user), your underlying voice doesn’t change much. Define the voice of your brand using the sliders below.

`Confident`
`Tentative`
`Analytical`
`Emotional`
`Formal`
`Informal`


###Gender bias
Built based on: Bolukbasi Tolga, Kai-Wei Chang, James Y. Zou, Venkatesh Saligrama, and Adam T. Kalai. Man is to computer programmer as woman is to homemaker? debiasing word embeddings. NIPS 2016.*

****Types of Bias****

- **Direct Bias**
	- 1. Associations: Words that are closer to one end (e.g., he) than to the other end (she). For example, occupational stereotypes.
	- 2. Analogies: Analogies of he:x::she:y. For example analogies exhibiting stereotypes.
	
- **Indirect Bias**
Projection of a neutral words into a two neutral words direction is explained in a great portion by a shared bias direction projection.




###Reading level
Qordoba use Flesch reading ease. In the Flesch reading-ease test, higher scores indicate material that is easier to read; lower numbers mark passages that are more difficult to read. The formula for the Flesch reading-ease score (FRES) test is

<img src="/assets/images/docs/reading-level.svg" />

Scores can be interpreted as shown in the table below


|Score	|School level	|Notes|
| ------------- | ------------- | ------------- | 
|100.00-90.00	|5th grade	|Very easy to read. Easily understood by an average 11-year-old student.|
|90.0–80.0|	6th grade	|Easy to read. Conversational English for consumers.|
|80.0–70.0	|7th grade	|Fairly easy to read.|
|70.0–60.0	|8th & 9th grade	|Plain English. Easily understood by 13- to 15-year-old students.|
|60.0–50.0	|10th to 12th grade	|Fairly difficult to read.|
|50.0–30.0	|College	|Difficult to read.|
|30.0–0.0	|College graduate	|Very difficult to read. Best understood by university graduates.|


Example

```
Speak to users in a single, unified voice.
Product content is typically written by different authors, on different teams, using different technologies — resulting in inconsistent product voices. Qordoba’s Content AI benchmarks application content according to a single Styleguide you establish.
``` 

- Number of characters (without spaces) :	247.00
- Number of words :	42.00
- Number of sentences :	3.00
- Average number of characters per word :	5.88
- Average number of syllables per word :	2.02
- Average number of words per sentence:	14.00

Flesch Reading Ease :	21.41 =>  `College graduate`


###Brevity
In Brevity you can set a word limit for sentences.


###Passive voice
A verb in a sentence is considered to be in the passive voice when the subject of the sentence is acted on by the verb. This happens a lot in technical writing when the process is more important than who is doing the activity. Conversely in the active voice the Subject acts on an object. 
The passive voice consists of an auxiliary form of "to be" + the participle verb:

| Voice| Example| Verbs| Definition|
|------------- |------------- |------------- |------------- |
|Passive |	Joan’s travel plans have to be arranged by December.|	be arranged :: the subject "travel plans" is acted on	|subject is acted on by verb|
|Active|	Joan arranged her travel plans before December. |	arranged:: the subject "Joan" acts on object "travel plans" 	|subject acts on object |

A customer may choose to remove passive voice from UX for a more informal experience. 

Sentences and clauses where the subject is the receiver of the main action. Often, sentences in passive voice sound weak and can be confusing. If so, rephrase the sentence in active voice.

Units of measurement: cases per sentence.

Examples: is made, is being carried, will be started.


###Named Entities detection

Categories selected below will be excluded from Qordoba's speelcheck.

- Person
- Organization
- Event
- Work of art
- Consumer goods
- Other types


###Emoji
Select what is Allowed 👍  and `Not Allowed` 

###Capitalization
Group of content rules defined by Qordoba and you can enable it or desible it

###Punctuation
Group of content rules defined by Qordoba and you can enable it or desible it



