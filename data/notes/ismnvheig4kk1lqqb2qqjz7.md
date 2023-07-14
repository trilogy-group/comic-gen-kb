## Parameters
### Dependent
- Story
### Independent
- Teaching Scope
### Control
- GPT-4
- Prompt
- Incident


## The prompt
- "incident-narration.0.0.0" for the script

- And the following prompt for extracting teaching scope from concept:
```python
"""
{{#system~}}
Given a concept, type out it's teaching scope like:

if the concept was allergies:
allergies, antihistamines, and our body's natural immunity would include the following concepts: Immune System Function, Allergen Recognition, Allergic Reactions, Histamine Role, Antihistamine Mechanism of Action, Immune Response, Innate Immunity, Adaptive Immunity, Immune Cells, Antibodies, Mast Cells, Immunoglobulin E (IgE), Allergy Symptoms, Allergy Types (Food Allergies, Skin Allergies, Respiratory Allergies), Allergy Diagnosis, Allergy Treatments, Antihistamine Types, Antihistamine Side Effects, Immune System Disorders, Autoimmunity, Hypersensitivity, Immunodeficiency, Tolerance, Vaccination, Immunotherapy, and Allergy Prevention.

{{~/system}}
{{#user~}}
{{concept}}
{{~/user}}
{{#assistant~}}
{{gen 'teaching_scope' temperature=0 max_tokens=1500}}
{{~/assistant}}
"""
```

## The Incident
- Syed was walking down the roads of pune when he found an cat abandoned on the side of the road. He decided to adopt the cat and take it home. Soon he realised that he was developing rashes around his skin because of the cat and fell sick. He was stubborn to keep the cat home and fight the allergy. Soon he became immune to it.



## Teaching Scopes
- allergies
- photosynthesis
- mitosis
- osmosis


## Output 1
```json
Concept : allergies

teaching_scope : allergies, antihistamines, and our body's natural immunity would include the following concepts: Immune System Function, Allergen Recognition, Allergic Reactions, Histamine Role, Antihistamine Mechanism of Action, Immune Response, Innate Immunity, Adaptive Immunity, Immune Cells, Antibodies, Mast Cells, Immunoglobulin E (IgE), Allergy Symptoms, Allergy Types (Food Allergies, Skin Allergies, Respiratory Allergies), Allergy Diagnosis, Allergy Treatments, Antihistamine Types, Antihistamine Side Effects, Immune System Disorders, Autoimmunity, Hypersensitivity, Immunodeficiency, Tolerance, Vaccination, Immunotherapy, and Allergy Prevention.

Narration : {
"Chain of Thought":"The story revolves around Syed, who develops an allergy after adopting a stray cat. The comic will visually depict the internal workings of the immune system, the allergic reaction, and the process of developing immunity. The incident of Syed adopting the cat and developing an allergy is the crux of the story. The comic will use this incident to explain the concepts of allergies, antihistamines, and immunity. The climax is when Syed's symptoms start to lessen, and the resolution is when he becomes immune to his cat allergy.",

"Narration" : [
"Panel 1: In the bustling city of Pune, we meet Syed, a kind-hearted man with a love for animals.",
"Panel 2: One day, Syed stumbles upon a stray cat and decides to adopt it.",
"Panel 3: Soon after bringing the cat home, Syed starts to develop rashes on his skin and falls sick.",
"Panel 4: This is Syed's immune system reacting to the cat's dander as if it were a harmful substance.",
"Panel 5: We delve into the immune system's function, explaining how it recognizes allergens and triggers an allergic reaction.",
"Panel 6: Despite his discomfort, Syed is determined to keep the cat. He visits a doctor who diagnoses him with a cat allergy.",
"Panel 7: The doctor prescribes antihistamines, and we explore how these drugs block the effects of histamine.",
"Panel 8: Syed struggles with his symptoms but remains steadfast in his decision to keep the cat.",
"Panel 9: Over time, his symptoms start to lessen. This is Syed's body learning to recognize the cat dander as harmless.",
"Panel 10: We explain the concepts of innate and adaptive immunity, showing how Syed's immune response is reducing his allergic reaction.",
"Panel 11: Finally, Syed has become immune to his cat allergy. This transformation is a result of his immune system's adaptive response.",
"Panel 12: We touch upon the concepts of immune system disorders, autoimmunity, hypersensitivity, and immunodeficiency.",
"Panel 13: We conclude by discussing allergy prevention, vaccination, and immunotherapy, providing a comprehensive understanding of allergies and our body's natural immunity."
]
}
```


### Insights
- The prompt is weak but we can see GPT's efforts trying to teach:
    - That allergies are caused due to histamines
    - immune system
    - hypersensitivity, etc


## Output 2
```json
Concept : photosynthesis

teaching_scope : Photosynthesis, chloroplasts, and plant energy conversion would include the following concepts: Photosynthesis Process, Light-Dependent Reactions, Light-Independent Reactions (Calvin Cycle), Chloroplast Structure, Chlorophyll, Photosynthetic Pigments, Energy Conversion, ATP (Adenosine Triphosphate), NADPH, Carbon Dioxide Fixation, Oxygen Evolution, Stomata, Photosystems I and II, Electron Transport Chain, Photophosphorylation, Carbon Cycle, Photorespiration, C3, C4, and CAM Plants, Factors Affecting Photosynthesis (Light Intensity, Carbon Dioxide Concentration, Temperature), Cellular Respiration, and the Role of Photosynthesis in the Ecosystem.

Narration : {
"Chain of Thought":"The story revolves around Syed, a young man who adopts a stray cat despite being allergic to it. The comic uses this incident to explain the concept of photosynthesis and how plants adapt to their environment. The plot points include Syed's decision to adopt the cat, his allergic reaction, his research into allergies and immunity, his efforts to build up his immunity, and finally, his success in overcoming the allergy. The comic also delves deep into the process of photosynthesis, explaining various aspects such as light-dependent and light-independent reactions, ATP and NADPH creation, carbon dioxide fixation, oxygen evolution, stomata, photosystems I and II, electron transport chain, photophosphorylation, carbon cycle, photorespiration, C3, C4, and CAM plants, factors affecting photosynthesis, cellular respiration, and the role of photosynthesis in the ecosystem.",

"Narration" : ["In the bustling city of Pune, we meet Syed, a compassionate young man with a love for nature and animals. One day, he stumbles upon a stray cat and decides to adopt it.", "Despite developing rashes, a sign of an allergic reaction, Syed is determined to keep the cat. Meanwhile, we delve into the concept of photosynthesis, the process by which plants synthesize food using sunlight.", "As Syed's condition worsens, he begins to understand his allergy. He learns about the immune system and how it reacts to foreign substances, much like how plants react to changes in their environment.", "We delve deeper into photosynthesis, explaining the light-dependent and light-independent reactions, the creation of ATP and NADPH, and the fixation of carbon dioxide.", "Syed starts taking small doses of cat dander, gradually building up his immunity. Similarly, we explain how plants adapt to different conditions, introducing C3, C4, and CAM plants.", "Finally, Syed's efforts pay off, and he becomes immune to the cat dander. He learns that challenges can be overcome with patience and perseverance.", "We wrap up the concept of photosynthesis, discussing the role of photosystems I and II, the electron transport chain, and photophosphorylation.", "We explain the carbon cycle and the role of photosynthesis in the ecosystem, emphasizing the importance of plants in maintaining the balance of life on Earth.", "Lastly, we touch upon cellular respiration, the process by which organisms convert biochemical energy from nutrients into ATP, and then release waste products."]
}
```


### Insights
- GPT is forcing the two concepts to be merged together and is trying random analogies
- The value of the story is lost as in the end it proceeds to independently explain photosynthesis


## Output 3
```json
Concept : mitosis

teaching_scope : The teaching scope for mitosis would include the following concepts: Cell Cycle, Interphase, Prophase, Prometaphase, Metaphase, Anaphase, Telophase, Cytokinesis, Chromosomes, Chromatids, Centromeres, Spindle Fibers, Centrioles, Nuclear Membrane, Cell Division, DNA Replication, Genetic Material, Cell Growth, Cell Differentiation, Cell Regeneration, Cell Death (Apoptosis), Mitotic Errors, Cancer and Tumors, Cell Cycle Regulation, Checkpoints in Cell Cycle, Role of Enzymes in Cell Division, Mitosis in Plants vs Animals, and Laboratory Techniques for Studying Mitosis.

Narration : {
"Chain of Thought":"The story revolves around Syed, who adopts a stray cat and develops an allergic reaction. This incident is used to explain the concept of cell division and growth. The plot points include Syed's decision to keep the cat despite the allergy, his worsening condition, and his eventual recovery. The characters are Syed and his immune cells, which undergo a transformation to become allergy-resistant. The emotions are shown through Syed's determination to keep the cat and his struggle with the allergy. The comic has a smooth continuity, with each panel leading to the next. The narration is engaging and explains the concept in detail.",

"Narration" : ["In the bustling city of Pune, we meet Syed, a compassionate man who stumbles upon a stray cat.", "Despite developing an allergic reaction, Syed decides to keep the cat.", "We delve into Syed's body, witnessing the rapid division and growth of his cells.", "Through the stages of mitosis, we see Syed's cells preparing to fight the allergen.", "Despite the cell division, Syed's condition worsens, and he falls severely ill.", "In a turn of events, Syed's body begins to adapt. His immune cells learn to recognize the allergen.", "Syed's immune cells differentiate, becoming specialized and resistant to the allergy.", "Syed's skin heals, a result of cell regeneration.", "The overactive immune cells die off, a process known as apoptosis.", "Finally, Syed recovers, living happily with his cat, immune to the allergy."]
}
```


### Insights
- It actually managed to incorporate mitosis into the story quite well..


## Output 4
```json
Concept : osmosis

teaching_scope : osmosis, diffusion, and cell membrane permeability would include the following concepts: Cell Membrane Structure, Passive Transport, Active Transport, Concentration Gradients, Hypertonic Solutions, Hypotonic Solutions, Isotonic Solutions, Water Potential, Solvent and Solute, Semi-permeable Membranes, Diffusion, Facilitated Diffusion, Ion Channels, Carrier Proteins, Osmotic Pressure, Osmoregulation, Turgor Pressure, Plasmolysis, Cytolysis, Endocytosis, Exocytosis, Phagocytosis, Pinocytosis, Aquaporins, Role of Osmosis in Kidney Function, Role of Osmosis in Plant Cells, and Osmosis in Everyday Life.

Narration : {
"Chain of Thought":"The story revolves around Syed and his adopted cat. The incident of Syed developing an allergy to the cat and then overcoming it serves as a perfect backdrop to explain the concepts of osmosis, diffusion, and cell membrane permeability. The allergens from the cat serve as the trigger for the immune response, which allows us to delve into the workings of the cell membrane and the transport of substances across it. The climax is Syed's body adapting to the allergens, which is a testament to the body's ability to learn and adapt. The resolution is Syed living peacefully with his cat, having overcome his allergy. This story allows us to explain the concepts in a relatable and engaging manner.",

"Narration" : ["Our story begins in the bustling city of Pune, where we meet Syed, a kind-hearted man with a love for animals.", "One day, Syed stumbles upon a stray cat, abandoned and alone. He decides to adopt the cat and bring it home.", "However, things take a turn when Syed starts developing rashes on his skin, a clear sign of an allergic reaction to the cat.", "Despite this, Syed is determined to keep the cat and fight off the allergy.", "As Syed's body reacts to the cat's allergens, we zoom into his body at a cellular level.", "We see the allergens coming into contact with Syed's cells, introducing the concept of the cell membrane and its semi-permeability.", "The allergens diffuse across the cell membrane, moving from an area of high concentration to an area of low concentration.", "This triggers an immune response, causing the rashes on Syed's skin.", "However, Syed's body starts to adapt. His cells begin to produce antibodies, which are transported out of the cells through active transport.", "These antibodies bind to the allergens, neutralizing them.", "Over time, Syed's body becomes more efficient at this process, and he becomes immune to the cat's allergens.", "Syed's body has now adapted to the cat's allergens. He no longer develops rashes and can live peacefully with his new pet.", "This transformation is a result of his body's ability to regulate the movement of substances across the cell membrane, a process known as osmoregulation.", "We end the comic with a broader look at how these concepts apply in everyday life, such as the role of osmosis in kidney function and plant cells, and how our bodies constantly adapt to our environment."]
}
```


### Insight
- This actually ended up being a pretty good comic and it found a neat way to show osmosis through the incident.


## Conclusion
- Prompt was weak but the attempt from GPT to merge the concept into the incident could be graded
- In photosynthesis, it failed and wasn't able to generate any value and tried baseless analogies between them
- In osmosis, mitosis it was surprisingly able to use the incident as reference and teach the concept

## Note
- The concepts chosen can be considered bias so will be retrying it with bit more diverse concepts as all previous ones were from life sciences


## Teaching Scopes
- newton's laws of motion
- random variables
- French Revolution


## Output 5
```json
Concept : newton's laws of motion

teaching_scope : Newton's Laws of Motion, forces, and their effects on motion would include the following concepts: Newton's First Law (Law of Inertia), Newton's Second Law (F=ma), Newton's Third Law (Action-Reaction), Force, Mass, Acceleration, Inertia, Momentum, Friction, Gravity, Centripetal Force, Equilibrium, Net Force, Balanced and Unbalanced Forces, Free Body Diagrams, Kinematics, Dynamics, Impulse, Conservation of Momentum, Elastic and Inelastic Collisions, Weight, Normal Force, Tension, Drag, Terminal Velocity, Projectile Motion, Circular Motion, Work, Energy, Power, Potential Energy, Kinetic Energy, Mechanical Energy, Conservation of Energy, Simple Machines, and Applications of Newton's Laws in Everyday Life.

Narration : {
"Chain of Thought":"The story revolves around Syed, a physics teacher, and his adopted cat, Newton. The incidents in their life together serve as practical examples of Newton's Laws of Motion. Syed's struggle with his cat allergy and his eventual adaptation to it mirrors the concept of forces and equilibrium in physics. The comic will visually depict these incidents and their corresponding physics concepts, making the subject more relatable and engaging for students. The climax is Syed falling seriously ill due to his allergy, and the resolution is his recovery and continued use of his experiences with Newton as teaching tools.",
"Narration" : [
"Panel 1: In the bustling city of Pune, we meet Syed, a physics teacher with a heart of gold.",
"Panel 2: One day, Syed finds an abandoned cat on the side of the road.",
"Panel 3: Despite his allergies, Syed adopts the cat, naming it Newton.",
"Panel 4: Syed's life with Newton becomes a series of challenges, each mirroring a concept from Newton's Laws of Motion.",
"Panel 5: Newton jumps off a high shelf, demonstrating Gravity.",
"Panel 6: Newton lands without injury, illustrating the Law of Inertia.",
"Panel 7: Newton pushes a vase off the table, exemplifying the Action-Reaction principle.",
"Panel 8: Syed's allergy worsens, but he persists, demonstrating Newton's First Law.",
"Panel 9: Syed falls seriously ill, marking the climax of our story.",
"Panel 10: Syed's immune system finally adapts, illustrating the concept of equilibrium in physics.",
"Panel 11: Syed recovers, having learned that every action in life has an equal and opposite reaction.",
"Panel 12: Syed continues to use his experiences with Newton to teach his students about physics, transforming his ordeal into a powerful teaching tool."
]
}
```



### Insights
- I liked the idea of using the cat and naming it newton to show some laws of motion
- Overall I did feel it was engaging

## Output 6
```json
Concept : random variables

teaching_scope : The teaching scope for the concept of random variables would include the following concepts: Definition of Random Variables, Discrete Random Variables, Continuous Random Variables, Probability Distribution, Probability Mass Function, Probability Density Function, Cumulative Distribution Function, Expected Value, Variance, Standard Deviation, Covariance, Correlation, Joint Distribution, Marginal Distribution, Conditional Distribution, Independence of Random Variables, Transformations of Random Variables, Moment Generating Functions, Common Distributions (Binomial, Poisson, Uniform, Normal, Exponential, etc.), Central Limit Theorem, Law of Large Numbers, Chebyshev's Inequality, and Applications of Random Variables in Statistics and Probability.

Narration : {
"Chain of Thought":"The story revolves around Syed, a statistician who adopts a cat despite being allergic to it. The allergy becomes a real-life example of a random variable, which Syed uses to explain the concept of random variables, probability distribution, expected value, variance, and standard deviation. The story is visually rich, with scenes of Syed's allergic reactions, his calculations, and his interactions with the cat. The climax is when Syed becomes immune to his allergy, symbolizing his mastery over the concept of random variables. The resolution is Syed's realization of the practical applications of statistics and probability, and his decision to teach these concepts to others.",

"Narration" : ["In the bustling city of Pune, we meet Syed, a young statistician with a heart of gold. He stumbles upon a stray cat and decides to adopt it, despite his allergies.", "Syed names the cat 'Variable' and starts developing rashes and falling sick due to his allergy.", "Syed decides to approach his allergy statistically. He starts recording the frequency and intensity of his allergic reactions, treating them as 'random variables'.", "Syed explains to Variable that a random variable is a variable whose possible values are numerical outcomes of a random phenomenon.", "He further explains that there are two types of random variables: discrete and continuous. His allergic reactions are a discrete random variable, as they can only take on a finite number of values.", "Syed introduces the concept of a probability distribution, which describes the likelihood of each outcome. He calculates the probability of having a severe allergic reaction on any given day, using the probability mass function.", "He also calculates the expected value, variance, and standard deviation of his allergic reactions. As his understanding improves, he starts taking preventive measures, reducing the frequency and intensity of his allergic reactions.", "The climax occurs when Syed realizes that he has become immune to his allergy. He reflects on his journey, realizing that his allergy was a blessing in disguise.", "Syed shares his insights with his colleagues, explaining how he used the concepts of probability distribution, expected value, variance, and standard deviation to manage his allergy.", "Syed's transformation is complete when he realizes that he can use his knowledge of statistics and probability to solve real-world problems. He decides to dedicate his life to teaching these concepts to others, starting with Variable, who has been his faithful companion throughout his ordeal."]
}
```



### Insights
- It had a great way of incorporating random variables through tracking the stage of allergies, and with improvements in prompts it can teach the concept by diving deep into each of these panels as well!

## Output 7
```json
Concept : French Revolution

teaching_scope : The teaching scope for the French Revolution would include the following concepts: Causes of the French Revolution, Enlightenment Ideas, Economic Crisis, Social Inequality, Estates-General, National Assembly, Storming of the Bastille, Declaration of the Rights of Man and of the Citizen, Women's March on Versailles, French Revolutionary Wars, Reign of Terror, Guillotine, Maximilien Robespierre, Committee of Public Safety, Thermidorian Reaction, The Directory, Napoleon Bonaparte, Coup of 18 Brumaire, Napoleonic Wars, The Consulate, The French Empire, The Concordat, The Napoleonic Code, Battle of Waterloo, The Congress of Vienna, and Legacy of the French Revolution.

Narration : {
"Chain of Thought":"The story revolves around Syed, a history teacher, who adopts a cat despite being allergic to it. His struggle with the allergy and eventual immunity is used as a metaphor to explain the French Revolution. The comic will visually depict Syed's journey and parallel it with the events of the French Revolution. The climax is Syed's immunity to the cat's allergens, which is likened to the fall of Robespierre and the establishment of The Directory. The resolution is Syed's peaceful coexistence with the cat, reflecting the legacy of the French Revolution.",

"Narration" : [
"Panel 1: In the bustling city of Pune, Syed, a history teacher, finds an abandoned cat.",
"Panel 2: Despite his allergies, Syed decides to adopt the cat, setting the stage for a struggle.",
"Panel 3: Syed starts developing rashes, mirroring the social inequality and economic crisis that led to the French Revolution.",
"Panel 4: As Syed fights his body's reaction to the cat, we delve into the causes of the French Revolution.",
"Panel 5: Syed's determination to keep the cat parallels the French people's fight for their rights.",
"Panel 6: Syed's health deteriorates, reaching the climax of the French Revolution with the Reign of Terror.",
"Panel 7: Syed becomes immune to the cat's allergens, symbolizing the fall of Robespierre and the establishment of The Directory.",
"Panel 8: Syed undergoes a transformation, becoming immune to the cat's allergens.",
"Panel 9: This mirrors the rise of Napoleon Bonaparte and the establishment of the French Empire.",
"Panel 10: Syed's newfound peace with the cat is likened to the Concordat.",
"Panel 11: Syed adapts to living with the cat, reflecting the Napoleonic Code.",
"Panel 12: The comic ends with Syed living harmoniously with the cat, symbolizing the legacy of the French Revolution."
]
}
```



### Insights
- French Revolution being a big topic but it was able to summarise it through incidents without making it feel too unnatural


## Conclusion
- Almost all cases, GPT does manage to relate seemingly opposite topics to the incident

- Also another observation is that the deviation from original story is minimal in case of allergies hence would be preferred by the customer the most
