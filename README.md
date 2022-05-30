# PRIMATE 2022 Dataset

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

This repository accompanies our **CLPsych 2022** paper which can be cited as follows:

```
@misc{https://doi.org/10.48550/arxiv.2205.13884,
  doi = {10.48550/ARXIV.2205.13884},
  
  url = {https://arxiv.org/abs/2205.13884},
  
  author = {Gupta, Shrey* and Agarwal, Anmol* and Gaur, Manas and Roy, Kaushik and Narayanan, Vignesh and Kumaraguru, Ponnurangam and Sheth, Amit},
  
  keywords = {Artificial Intelligence (cs.AI), Computation and Language (cs.CL), FOS: Computer and information sciences, FOS: Computer and information sciences},
  
  title = {Learning to Automate Follow-up Question Generation using Process Knowledge for Depression Triage on Reddit Posts},
  
  publisher = {arXiv},
  
  year = {2022},
  
  copyright = {Creative Commons Attribution Share Alike 4.0 International}
}
```


This [PRIMATE agreement document](https://github.com/primate-mh/Primate2022/blob/main/Primate2022_agreement.pdf) provides all details needed to have access to the PRIMATE 2022 dataset.
The dataset is available for research purposes under proper user agreements.

# Downloading the dataset
## User agreement
This dataset can only be used for research purposes. If you are interested in having access to this data, please sign the PRIMATE dataset agreement and upload the filled PDF at the end of the form (https://forms.gle/4yinUi829kUpfZPZ7). The link to the dataset will then be shared with you immediately. 
If you face any issues, you can contact the authors at anmol.agarwal@students.iiit.ac.in, shrey.gupta@students.iiit.ac.in, mgaur@email.sc.edu or kaushikr@email.sc.edu.

# Dataset
### Question-like labels from PHQ-9 used in the dataset
1) "Feeling-bad-about-yourself-or-that-you-are-a-failure-or-have-let-yourself-or-your-family-down"
2) "Feeling-down-depressed-or-hopeless"
3) "Feeling-tired-or-having-little-energy"
4) "Little-interest-or-pleasure-in-doing-things"
5) "Moving-or-speaking-so-slowly-that-other-people-could-have-noticed-Or-the-opposite-being-so-fidgety-or-restless-that-you-have-been-moving-around-a-lot-more-than-usual"
6) "Poor-appetite-or-overeating" 
7) "Thoughts-that-you-would-be-better-off-dead-or-of-hurting-yourself-in-some-way"
8) "Trouble-concentrating-on-things-such-as-reading-the-newspaper-or-watching-television"  
9) "Trouble-falling-or-staying-asleep-or-sleeping-too-much"


### Format
`primate_dataset.json`: Contains 2003 posts with each post having the following attributes:
* `post_title`: title of the post
* `post_text`: the entire text of the post (this is same as the selftext attribute of Reddit posts)
* `annotations`: this is a list containing 9 elements. The ith element has 2 items:
    1. A particular question in PHQ-9
    2. **Yes/No** label depending on whether "the answer to the question can be deduced/known using the content present in the post text & title"

### Sample post 1:

```json
{
    "post_title": "Should I use the psychological help service that my university provides for free?",
    "post_text": "Lately I've been feeling really low. \nI can't make myself leave the bed, I start crying out of the blue and everything is just so heavy. \nI think I've always suffered from some kind of depression but I've never been to therapy because I couldn't afford it on my own and my family didn't ever suspect anything. \nNow I live on my own in another city. Yesterday I discovered that my university provides psychological help for students for free. Do you think I should give it a go? \nI'm a bit afraid because I don't know what to expect and I don't really know what to tell them when I'll be there. I know they don't provide help for very serious issues (you'll need a psychiatrist for that) and I hope they don't take care for only \"university related problems\".\nOn the other hand, I have nothing to lose because it's free.\nDid you ever try anything like that? \n",
    "annotations": [
      [
        "Feeling-bad-about-yourself-or-that-you-are-a-failure-or-have-let-yourself-or-your-family-down",
        "yes"
      ],
      [
        "Feeling-down-depressed-or-hopeless",
        "yes"
      ],
      [
        "Feeling-tired-or-having-little-energy",
        "yes"
      ],
      [
        "Little-interest-or-pleasure-in-doing ",
        "yes"
      ],
      [
        "Moving-or-speaking-so-slowly-that-other-people-could-have-noticed-Or-the-opposite-being-so-fidgety-or-restless-that-you-have-been-moving-around-a-lot-more-than-usual",
        "no"
      ],
      [
        "Poor-appetite-or-overeating",
        "no"
      ],
      [
        "Thoughts-that-you-would-be-better-off-dead-or-of-hurting-yourself-in-some-way",
        "no"
      ],
      [
        "Trouble-concentrating-on-things-such-as-reading-the-newspaper-or-watching-television",
        "no"
      ],
      [
        "Trouble-falling-or-staying-asleep-or-sleeping-too-much",
        "yes"
      ]
    ]
  }
```

#### Embedded Explanation for the labels for sample post 1
> "Lately I've been [feeling really low **(Q2, Q3)**].
[I can't make myself leave the bed **(Q3,Q9)**], [I start crying out of the blue and everything is just so heavy **(Q1,Q4)**].
I think I've [always suffered from some kind of depression **(Q2)**] but I've never been to therapy because [I couldn't afford it **(Q1)**] on my own and [my family didn't ever suspect anything **(Q1)**].
Now I live on my own in another city. Yesterday I discovered that my university provides psychological help for students for free. Do you think I should give it a go?
I'm a bit afraid because I don't know what to expect and I don't really know what to tell them when I'll be there. I know they don't provide help for very serious issues (you'll need a psychiatrist for that) and I hope they don't take care for only \"university related problems\".
On the other hand, I have nothing to lose because it's free.
Did you ever try anything like that?"


### Sample post 2:

```json
{
    "post_title": "I haven\u2019t been happy in so long",
    "post_text": "I look up how to get out of bed all the time. I see \u201csit up\u201d as the first step but when I wake up in the mornings I dont want to feel better. I just want to go back to sleep. I sleep all day. I don\u2019t have a job and I know my boyfriend is being affected. I feel like a parasite on everyone\u2019s life. No one benefits from being my friend or being with me. I\u2019m literally just a burden. Some of my best friends have even blocked me on social media and honestly I\u2019m not even mad. I understand. I take my anti depressants, I\u2019ve been to inpatient hospitals. I literally have no motivation to keep going. I don\u2019t want to die but I don\u2019t want to wake up anymore. I just want to lay in bed. I have a son. Even though I have no job, he goes to a babysitter. I only watch him twice a week. I love him and I miss him when he\u2019s gone but I can barely even take care of him when he\u2019s home. I know he\u2019s going to grow up to resent me. I wish I was the same person that gave birth to him but I am completely different. He\u2019s such a good kid. He\u2019s so happy I wish I could be a good mom for him. I wish I could be who my family needs me to be. I hate myself. I am terrible for my family. Most of the time I think that staying around is going to be worse for my family than if I just left. I don\u2019t know what to do. I want to be happy but I\u2019ve tried so many times to heal and the attempts have never gained any happiness.",
    "annotations": [
      [
        "Feeling-bad-about-yourself-or-that-you-are-a-failure-or-have-let-yourself-or-your-family-down",
        "yes"
      ],
      [
        "Feeling-down-depressed-or-hopeless",
        "yes"
      ],
      [
        "Feeling-tired-or-having-little-energy",
        "yes"
      ],
      [
        "Little-interest-or-pleasure-in-doing ",
        "yes"
      ],
      [
        "Moving-or-speaking-so-slowly-that-other-people-could-have-noticed-Or-the-opposite-being-so-fidgety-or-restless-that-you-have-been-moving-around-a-lot-more-than-usual",
        "no"
      ],
      [
        "Poor-appetite-or-overeating",
        "no"
      ],
      [
        "Thoughts-that-you-would-be-better-off-dead-or-of-hurting-yourself-in-some-way",
        "yes"
      ],
      [
        "Trouble-concentrating-on-things-such-as-reading-the-newspaper-or-watching-television",
        "no"
      ],
      [
        "Trouble-falling-or-staying-asleep-or-sleeping-too-much",
        "yes"
      ]
    ]
  }
```

#### Embedded explanation for the labels for sample post 2
> "I look up how to get out of bed all the time. I see sit up as the first step but when I wake up in the mornings I dont want to feel better. [I just want to go back to sleep. I sleep all day **(Q9)**]. I don't have a job and I know my boyfriend is being affected. I feel like a parasite on everyone's life. No one benefits from being my friend or being with me. I'm literally just a burden. Some of my best friends have even blocked me on social media and honestly I'm not even mad. I understand. I take my anti depressants, I've been to inpatient hospitals. [I literally have no motivation to keep going **(Q2,Q4)**]. [I don't want to die but I don't want to wake up anymore **(Q7)**]. [I just want to lay in bed **(Q3)**]. I have a son. Even though I have no job, he goes to a babysitter. I only watch him twice a week. I love him and I miss him when he's gone but I can barely even take care of him when he's home. [I know he's going to grow up to resent me. I wish I was the same person that gave birth to him but I am completely different. **(Q1)**] He's such a good kid. He's so happy I wish I could be a good mom for him. I wish I could be who my family needs me to be. I hate myself. I am terrible for my family. [Most of the time I think that staying around is going to be worse for my family than if I just left. **(Q1)**]. I don't know what to do. [I want to be happy but I've tried so many times to heal and the attempts have never gained any happiness. **(Q2)**]"
