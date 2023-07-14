

# Experiment to check if GPT can aptly sense std.ids that a particular incident can teach

## DoD
- [x] Get a conclusion whether GPT's sense of what concepts fit best is accurate
- [x] Get a conclusion whether GPT is able to map concepts to valid NGSS standard ids.


## Parameters
### Independent
- incidents
### Dependent
- script
- standard ids
- concept
### Control
- Prompts
- GPT-4

## Incidents
- Syed was walking down the roads of pune when he found an cat abandoned on the side of the road. He decided to adopt the cat and take it home. Soon he realised that he was developing rashes around his skin because of the cat and fell sick. He was stubborn to keep the cat home and fight the allergy. Soon he became immune to it.
 
- I, Anirudh was determined to learn to solve the Rubik's cube. I realised that it required me to learn the notations for each move like "R" was to move the right face up, and "U" was to move the top face left etc. After which I learn't that the cube is solved in stages and memorised the algorithms and though process for each, After which I was able to solve the cube!
 
- I ate an apple today
 
- I scored a goal today while playing football.


## Prompts
- story : "incident-narration.0.0.0"
- for getting the NGSS standard :
```python
"""
{{#system~}}
Based on the short incident provided, please identify and list the relevant school concept that align with the Next Generation Science Standards (NGSS) curriculum that can be learned from this incident.

In your Chain of thought, think about what concept can be naturally taught through the story and can provide the highest educational value. If there are multiple concepts, choose one that is most natural to the story and highlight why in the chain of thought. Also Validate why the chosen standard id is a valid NGSS standard id

Have all the topics to be taught in the standard id be part of the Description. 

Have the output as valid JSON enclosed in double quotes and nothing else!

{
"Chain of Thought" : "....",
"Concept": "....",
"NGSS Standard id" : "....",
"Assessment Boundary": "...",
"Clarification Statement":"...",
}


{{~/system}}
{{#user~}}
{{incident}}
{{~/user}}
{{#assistant~}}
{{gen 'teaching_scope' temperature=0 max_tokens=1500}}
{{~/assistant}}
"""
```
- for extracting topics from the NGSS standard:

```python
"""
{{#system~}}
Given a concept, type out it's teaching scope like:
if the concept was allergies:
allergies, antihistamines, and our body's natural immunity would include the following concepts: Immune System Function, Allergen Recognition, Allergic Reactions, Histamine Role, Antihistamine Mechanism of Action, Immune Response, Innate Immunity, Adaptive Immunity, Immune Cells, Antibodies, Mast Cells, Immunoglobulin E (IgE), Allergy Symptoms, Allergy Types (Food Allergies, Skin Allergies, Respiratory Allergies), Allergy Diagnosis, Allergy Treatments, Antihistamine Types, Antihistamine Side Effects, Immune System Disorders, Autoimmunity, Hypersensitivity, Immunodeficiency, Tolerance, Vaccination, Immunotherapy, and Allergy Prevention.
And if it's part of a curriculum , make sure the topics are under scope
{{~/system}}
{{#user~}}
{{concept}}
{{~/user}}
{{#assistant~}}
{{gen 'teaching_scope' temperature=0 max_tokens=1500}}
{{~/assistant}}
"""
```
## Output 1
```python
{'Chain of Thought': "The incident involves Syed developing an allergic reaction to a cat, which he then becomes immune to. This can be used to teach about the immune system and how it responds to allergens. The most relevant concept here is the immune system's ability to adapt and develop immunity over time. This aligns with the NGSS standard on the role of the immune system in human health.", 'Concept': 'Immune System and Allergies', 'NGSS Standard id': 'HS-LS1-2', 'Assessment Boundary': 'Assessment does not include the molecular mechanisms of the immune response.', 'Clarification Statement': 'Develop and use a model to illustrate the hierarchical organization of interacting systems that provide specific functions within multicellular organisms.'}
Incident : Syed was walking down the roads of pune when he found an cat abandoned on the side of the road. He decided to adopt the cat and take it home. Soon he realised that he was developing rashes around his skin because of the cat and fell sick. He was stubborn to keep the cat home and fight the allergy. Soon he became immune to it.

Teaching Scope : Immune System and Allergies would include the following concepts: Immune System Structure, Immune System Function, Innate Immunity, Adaptive Immunity, Immune Cells (T Cells, B Cells, Macrophages, Neutrophils, Dendritic Cells), Antibodies, Antigen Presentation, Immune Response, Allergen Recognition, Allergic Reactions, Histamine Role, Mast Cells, Immunoglobulin E (IgE), Allergy Symptoms, Allergy Types (Food Allergies, Skin Allergies, Respiratory Allergies), Allergy Diagnosis, Allergy Treatments, Antihistamines, Corticosteroids, Immune System Disorders, Autoimmunity, Hypersensitivity, Immunodeficiency, Tolerance, Vaccination, Immunotherapy, and Allergy Prevention.

Narration : {
"Chain of Thought":"The story revolves around Syed, who develops an allergy after adopting a stray cat. The comic will visually depict the immune system's response to the cat's dander, explaining the roles of different immune cells and how they work together to protect the body. The comic will also delve into the concept of allergies, their symptoms, diagnosis, and treatment. The climax will be when Syed's body starts to tolerate the cat dander, and his allergic reactions lessen. The resolution will be when Syed becomes immune to the cat dander and no longer experiences allergic reactions. The comic will also explain the concept of immunotherapy and vaccination.",

"Narration" : ["In the bustling city of Pune, we meet Syed, a kind-hearted man with a love for animals. One day, he stumbles upon a stray cat and decides to adopt it.", "Soon after bringing the cat home, Syed starts developing rashes on his skin and falls sick. This is his immune system reacting to the cat's dander as if it were a harmful substance.", "Despite his discomfort, Syed is determined to keep the cat. He visits a doctor, who explains that his immune system is overreacting to the cat dander, causing an allergic reaction.", "Syed learns about different types of allergies and their symptoms, as well as how they are diagnosed and treated. He starts taking antihistamines and corticosteroids to manage his symptoms.", "Over time, Syed's body starts to tolerate the cat dander, and his allergic reactions lessen. This is an opportunity to explain the concept of tolerance and how the immune system can adapt to recognize certain substances as non-threatening.", "Eventually, Syed becomes immune to the cat dander and no longer experiences allergic reactions. This is a chance to explain the concept of immunotherapy, where the immune system is trained to stop reacting to certain allergens.", "We also discuss the concept of vaccination, which works on a similar principle. In the end, Syed is able to live happily with his cat, having learned a lot about the immune system and allergies.", "He also takes steps to prevent future allergies, such as regular cleaning and grooming of his cat."]
}
```

### Insights
- HS-LS1-2 is a valid standard id
- it is a valid concept fit and feels natural

## Output 2
```python
{'Chain of Thought': "The incident involves Anirudh learning to solve a Rubik's cube. This involves understanding the notations for each move, learning the stages of solving the cube, and memorizing the algorithms. This can be related to the NGSS standard of developing and using models, as solving a Rubik's cube involves developing a mental model of the cube and its movements. It also involves using mathematical thinking, which is another NGSS standard.", 'Concept': 'Developing and Using Models, Mathematical and Computational Thinking', 'NGSS Standard id': 'MS-ETS1-4', 'Assessment Boundary': 'Assessment is limited to algebraic expressions and comparisons of algebraic expressions.', 'Clarification Statement': "Students can understand that solving a Rubik's cube involves developing a mental model of the cube and its movements, and using mathematical thinking to solve it. This aligns with the NGSS standard of developing and using models, and mathematical and computational thinking."}
Incident : I, Anirudh was determined to learn to solve the Rubik's cube. I realised that it required me to learn the notations for each move like was to move the right face up, and was to move the top face left etc. After which I learn't that the cube is solved in stages and memorised the algorithms and though process for each, After which I was able to solve the cube!

Teaching Scope : Developing and Using Models, Mathematical and Computational Thinking would include the following concepts: Understanding of Models, Types of Models (Physical, Conceptual, Mathematical, Computational), Model Development, Model Analysis, Model Application, Model Limitations, Mathematical Thinking, Computational Thinking, Algebraic Expressions, Comparison of Algebraic Expressions, Problem Solving, Logical Reasoning, Abstract Thinking, Pattern Recognition, Algorithm Development, Data Analysis, Data Interpretation, Computational Tools, Mathematical Concepts (Variables, Equations, Functions, Graphs), Mathematical Operations, Mathematical Relationships, Mathematical Models, Computational Models, and Real-world Application of Models and Mathematical/Computational Thinking.

Narration : {
"Chain of Thought":"The comic will visually depict Anirudh's journey of solving the Rubik's cube, using it as a metaphor for complex problem-solving. The cube's structure, the notations, the stages of solving, and the algorithms will be visually represented. Anirudh's thought process, his struggles, his learning, and his success will be shown through his expressions and actions. The comic will also visually represent the mathematical and computational concepts involved in solving the cube. The climax will be Anirudh solving the cube, and the resolution will be his reflection on his journey and the lessons learned.",

"Narration" : ["In the bustling city of Bangalore, we meet Anirudh, a curious teenager with a knack for problem-solving.", "One day, Anirudh stumbles upon a Rubik's cube, a complex 3D puzzle that piques his interest.", "Anirudh decides to solve the cube, embarking on a journey of mathematical and computational exploration.", "He begins by understanding the cube's structure and the notations for each move.", "Anirudh learns that the cube is solved in stages, each requiring a different algorithm.", "He uses algebraic expressions to represent the moves, comparing them to find the most efficient solution.", "Anirudh develops a computational model, using logical reasoning and abstract thinking to recognize patterns and develop algorithms.", "He faces setbacks as some algorithms don't work as expected, but he learns from these failures and refines his model.", "The climax occurs when Anirudh finally solves the cube, applying his mathematical and computational thinking skills.", "In the aftermath of his success, Anirudh reflects on his journey.", "He realizes the importance of developing and using models, understanding their limitations, and the need for constant refinement.", "Anirudh appreciates the power of mathematical and computational thinking in problem-solving.", "His transformation is evident in his newfound confidence and his ability to apply these concepts to real-world problems."]
}
```

### Insights
- MS-ETS1-4 is a valid standard id
- The concept chosen fits very naturally to the story, as I assumed that my journey in Rubik's cube would have to educational relevance, but it was able to find an actual part of the curriculum that It could teach through it
- Although the concerning part is how it was able to guess that Anirudh lives in Bangalore XD the data available in the net is indeed scary

## Output 3
```python
{'Chain of Thought': 'The incident involves the consumption of an apple, which can lead to a discussion about the life cycle of plants, including fruit-bearing trees like apple trees. This can be linked to the concept of life cycles and reproduction in organisms, which is a part of the NGSS curriculum.', 'Concept': 'Life Cycles and Reproduction in Organisms', 'NGSS Standard id': '3-LS1-1', 'Assessment Boundary': 'Assessment of plant life cycles is limited to those of flowering plants. Assessment does not include details of human reproduction.', 'Clarification Statement': 'Students who demonstrate understanding can develop models to describe that organisms have unique and diverse life cycles but all have in common birth, growth, reproduction, and death.'}
Incident : I ate an apple today

Teaching Scope : Life Cycles and Reproduction in Organisms would include the following concepts: Life Cycle Stages, Reproduction Methods, Sexual Reproduction, Asexual Reproduction, Flowering Plant Life Cycle, Animal Life Cycles, Insect Life Cycles, Bird Life Cycles, Mammal Life Cycles, Amphibian Life Cycles, Reptile Life Cycles, Fish Life Cycles, Birth, Growth, Death, Fertilization, Embryonic Development, Larval Stage, Pupal Stage, Adult Stage, Metamorphosis, Germination, Pollination, Seed Dispersal, Fruit Formation, Flower Parts, Egg, Sperm, Zygote, Embryo, Fetus, Juvenile, Adult, Aging, and Life Span.

Narration : {
"Chain of Thought":"The story revolves around the life cycles and reproduction in organisms. The central characters are a group of friends: Alex the Apple Tree, Benny the Bee, Cathy the Caterpillar, and Danny the Dog. The incident of Alex losing his apples prematurely sets the stage for the exploration of life cycles and reproduction. The friends embark on a journey through Bioville, learning about different life cycles and reproduction methods. They face challenges and setbacks, but they overcome them together. The climax occurs when they discover that Alex's premature apple loss is due to a lack of pollination. In the resolution, the friends work together to solve Alex's problem, understanding the importance of each organism in the ecosystem and the interconnectedness of life cycles.",

"Narration" : ["Our story begins in the bustling city of Bioville, where Alex the Apple Tree stands tall, his branches heavy with apples.", "Suddenly, an apple falls prematurely, causing concern among Alex's friends: Benny the Bee, Cathy the Caterpillar, and Danny the Dog.", "They decide to investigate, leading us on a journey through the life cycles and reproduction in organisms.", "First stop, Benny's hive. We see bees buzzing, collecting nectar, and learn about their life cycle and the crucial role they play in pollination.", "Next, we visit Cathy, snug in her cocoon, ready to transform. We learn about the fascinating process of metamorphosis in insects.", "Then, we meet Danny, a proud new father, teaching us about the life cycle of mammals, from birth to aging.", "Our friends face challenges, like a sudden storm and a predator attack, but they overcome them together, showing the strength of their bond.", "The climax hits when they realize Alex's problem: a lack of pollination.", "In the resolution, Benny brings more bees for pollination, Cathy helps in seed dispersal, and Danny guards the tree.", "They all understand the interconnectedness of life cycles and the importance of each organism in the ecosystem.", "Finally, Alex blooms again, signifying the continuity of life cycles, and the friends celebrate their victory."]
}
```

### Insights
- The point of this and the next example is to test whether our system works well with a single sentence and the result is indeed promising
- The prompt can be fine tuned to go deeper into each concept but with the short text, but the choice of concept works well with trees although personally I feel since the action was eating a better choice would be digestion but that's subjective
- 3-LS1-1 is a valid standard id

## Output 4
```python
{'Chain of Thought': 'The incident involves the student playing football and scoring a goal. This can be related to the concept of motion and forces. The student had to apply a certain amount of force to the ball to make it move and score a goal. This can be used to teach the concept of forces and motion in physics.', 'Concept': 'Forces and Motion', 'NGSS Standard id': 'MS-PS2-2', 'Assessment Boundary': 'Assessment does not include quantitative force size, only qualitative and relative. Assessment is limited to gravity being addressed as a force that pulls objects down.', 'Clarification Statement': 'Plan an investigation to provide evidence that the change in an object’s motion depends on the sum of the forces on the object and the mass of the object.'}
Incident : I scored a goal today while playing football.

Teaching Scope : Forces and Motion, as per the NGSS Standard MS-PS2-2, would include the following concepts: Force Definition, Types of Forces (Gravity, Friction, Applied Force, Normal Force, Air Resistance Force, Tension Force, Spring Force), Newton's Laws of Motion, Mass and Weight, Effects of Force on Motion, Balanced and Unbalanced Forces, Net Force, Direction of Forces, Motion (Speed, Velocity, Acceleration), Inertia, Momentum, Gravitational Force, Frictional Force, Investigating Forces, Planning and Conducting Investigations, Data Collection and Analysis, Drawing Conclusions from Investigations, and Application of Forces in Real-world Contexts. The teaching scope is limited to qualitative and relative force size, with gravity being addressed as a force that pulls objects down.

Narration : {
"Chain of Thought":"The story revolves around a friendly football game in a city park. The central characters are Max, a science enthusiast, and Leo, a sports fanatic. The incident that sparks the story is Leo scoring a goal, which leads Max to explain the science behind it. The comic will visually depict the forces at play during the game, using diagrams, slow-motion replays, and simple experiments to illustrate the concepts. The climax is Leo's understanding and appreciation of the science behind his goal. The resolution sees Leo applying his newfound knowledge to improve his game, while Max learns the importance of patience and effective communication in teaching.",

"Narration" : ["Our story begins in a bustling city park, where a group of kids are engrossed in a friendly game of football.", "Among them are Max, a science enthusiast, and his best friend, Leo, a sports fanatic.", "The game takes an interesting turn when Leo scores a goal, sparking Max's curiosity.", "Max, always eager to explain the science behind everyday activities, begins to explain the concept of force.", "He uses the football as an example, explaining how Leo's kick, an applied force, set the ball in motion.", "Max introduces the types of forces, using the football game as an example.", "He explains gravity as the force that pulls the ball down, friction as the force that slows the ball down, and air resistance as the force that opposes the ball's motion in the air.", "Max then introduces Newton's Laws of Motion, explaining how they apply to the football game.", "He uses the first law to explain why the ball stays in motion until another force acts on it (inertia), the second law to explain how the force of Leo's kick affected the ball's acceleration, and the third law to explain how the ball exerted an equal and opposite force on Leo's foot.", "Leo struggles to understand these concepts, but Max uses diagrams, slow-motion replays of the goal, and simple experiments to help Leo understand.", "The climax occurs when Leo finally understands and appreciates the science behind his goal.", "In the post-climax resolution, Leo begins to see the science in his everyday activities and develops a newfound appreciation for physics.", "He even starts using his understanding of forces and motion to improve his football skills.", "Max, on the other hand, learns the importance of patience and effective communication in teaching complex concepts.", "The comic ends with the two friends continuing their game, now with a deeper understanding and appreciation of the science behind it."]
}
```

#### Insights
- Once again, the choice of concepts fit perfectly to the comic
- And MS-PS2-2 is a valid standard id

## Conclusion
- The experiment was a success and we were able to answer our questions that
- Yes, GPT's concepts matched the incident perfectly
- Yes, Standard ids generated were valid NGSS standards