# PhD Defence — Speaker Notes

## Slide 1 of 19: Title
Welcome to the doctoral defense presentation on "Chemical characterisation of essential oils and machine learning analysis of molecular substructures associated with antimicrobial activity against Salmonella Typhimurium for food industry applications."


This interdisciplinary research bridges experimental phytochemistry with computational approaches to understand and predict antimicrobial activity in essential oils. The work was conducted at the Faculty of Agriculture, University of Belgrade, under the supervision of Prof. Dr. Viktor Nedović and Prof. Dr. Mirjana Pesić.

## Slide 2 of 19: Acknowledgments
I would like to express my sincere gratitude to all collaborators who contributed to this research.


Mentors: Prof. Dr. Viktor Nedović and Prof. Dr. Mirjana Pešić for their guidance throughout this doctoral journey.


Faculty of Agriculture team: Dr. Ana Salević, Dr. Ana Kalušević, Dr. Steva Lević, Dr. Milena Pantić, and Prof. Dr. Miomir Nikšić for experimental support and expertise.


Other Serbian institutions: Dr. Miloš Jovanović and Dr. Marija Kuzmanović from Faculty of Organizational Sciences for computational collaboration; Dr. Dejan Pljevljakušić and Dr. Katarina Šavikin from the Institute for Medicinal Plants for botanical expertise; and Prof. Dr. Nataša Milosavljević from the Department of Mathematics and Physics, Faculty of Agriculture, for her support.


International collaborators: Prof. Dr. Ivan Mijaković, Prof. Dr. Jens Nielsen, Prof. Dr. Aleksej Zelezniak, Dr. Jan Zrimec, and Filip Buric from Chalmers University of Technology and partner institutions for machine learning and systems biology insights.

## Slide 3 of 19: The PhD Journey
I begin with some reflections: this phd was not a straightforward journey at all.


The first year went as expected but then life got in the way. I moved between different countries and even continents. Then Covid. Then marriage. At one point I actually started another PhD in Copenhagen but dropped out shortly after starting it. Then I thought I will become an artist instead. Then unsuccesfull pregnancies and I even joined a cult in Spain. 
I finaly went back to school to study data science and got a job as a consultant in AI and data analytics in Sweden. There were long stretches where this thesis was sitting in a drawer and I genuinely didn't know if I'd ever come back to it.


But I did come back. I picked py PhD up again, finished the project, publish the paper and here we are today — bringing it to a logical resolution. But resolution is not the end of the journey. The journey continues to a postdoc positon in Chalmers, Sweden where I will continue working with AI to develop novel drugs to treat bacterial infections.



And what's interesting is that through all of that, two things kept moving in opposite directions. My skills — the research, the writing, the analytical thinking — kept growing. But my certainty about how much I know kept shrinking. The more I learn, the more I realise how much I don't know. I think that's actually the most unexpected outcome of this PhD journey.

## Slide 4 of 19: Research Roadmap


## Slide 5 of 19: Experimental Foundation


## Slide 6 of 19: Machine Learning
Phase I: Experimental Results & Discussion



1. GC-MS Chemotyping:

- Tea Tree (M. alternifolia): Dominated by terpinen-4-ol (44.7%), γ-terpinene (19.5%), and α-terpinene (7.8%). Together, these C10 monoterpenes account for >70% of the peak area, confirming ISO4730 compliance. Terpinen-4-ol drives antibacterial effects, while hydrocarbons provide antioxidant power.

- Lavender & Bergamot: Both exhibit oxygenated monoterpenoid chemotypes. Lavender (35.7% linalool, 42.3% linalyl acetate); Bergamot (22.9% linalool, 57.5% linalyl acetate). The high ester content in Bergamot distinguishes it from Lavender.

- Peppermint (M. piperita): Classic "high-menthol" chemotype with iso-menthol at 49.3%.



2. Bioactivity Profile:

- Antimicrobial Potency: Lavender and Bergamot were most potent (MIC 5 µg/mL), while Tea Tree and Peppermint required 10 µg/mL. These values are modest compared to phenolic-rich oils (Origanum/Thymus), likely due to the Gram-negative outer membrane barrier of S. Typhimurium.

- Antioxidant Efficacy: Peppermint emerged as the top performer (23.3 mmol TE/L), whereas Tea Tree was the weakest (7.6 mmol TE/L), reflecting its lower phenolic/menthol load.



3. Formulation Strategy (Outcome 1):

- We addressed the industrial barriers of toxicity and sensory impact using Electrostatic Extrusion.

- Bead Integrity: 2% calcium-alginate matrices effectively encapsulated the oils. Beads averaged 2.0mm (wet) and shrank to ~1.4mm (dried).

- Versatility: Physicochemical data confirms this as a food-grade, versatile method for preserving terpene-rich volatiles and maintaining redox stability throughout shelf life.



Research Gap: This stage confirmed bioactivity but highlighted a 10-fold potency difference between these oils and literature-reported oregano/thyme oils. This led to our "Pivot Point": using computational tools to decode the specific molecular drivers behind these differences.

## Slide 7 of 19: Why?
This slide introduces the three main research questions driving this doctoral work:


1. Why Salmonella? It's a major global foodborne pathogen with rising antimicrobial resistance, designated as a WHO priority pathogen.


2. Why essential oils? Unlike single-target antibiotics, EOs contain complex mixtures of secondary metabolites that attack bacteria through multiple mechanisms simultaneously, potentially reducing resistance development.


3. Why ML & Morgan Fingerprints? Machine learning allows us to identify which molecular substructures in EO compounds are responsible for antimicrobial activity, enabling rational design of new antimicrobial formulations.


Click on any section to explore the detailed rationale.

## Slide 8 of 19: Why studying Salmonella?
Antibiotics are routinely added to animal feed and water on farms, both to promote growth and prevent disease in livestock. This agricultural use creates an environment where bacteria including Salmonella Typhimurium are exposed to low antibiotic levels, encouraging resistance to develop. Resistant strains then enter the food chain and cause hard-to-treat infections in people.
While many Salmonella infections are treated without antibiotics, multidrug resistance is a clinical crisis — effective antibiotics are the only thing standing between life and death for invasive cases.
As we can see from the graph, diarrheal diseases are a major cause of death in children under 5 globally. But the overall trend is positive — as research advances, so do our tools to fight these diseases.

## Slide 9 of 19: Why essential oils?
Why essential oils as antimicrobials?


The resistance problem: Most antibiotics act on single, well-defined targets (cell wall synthesis, DNA replication, protein synthesis), making it relatively easy for bacteria to develop resistance through a single mutation or enzyme modification.


Examples:

• β-lactams (Penicillin, Ampicillin) - inhibit cell wall synthesis via PBPs

• Fluoroquinolones (Ciprofloxacin) - inhibit DNA gyrase

• Aminoglycosides (Gentamicin) - cause ribosomal mistranslation

• Macrolides (Azithromycin) - block ribosomal exit tunnel


The EO advantage: Essential oils evolved over millions of years as plant defense mechanisms. Rather than single toxins, they produce complex mixtures of terpenes and phenolics that attack bacteria through multiple simultaneous mechanisms: membrane disruption, altered permeability, enzyme interference, and signaling disruption. This multi-target approach makes resistance development much harder.

## Slide 10 of 19: Why ML & Morgan Fingerprints?
Essential oils are not just single compounds but complex biological mixtures. 
Our key insight was that antimicrobial activity correlates with specific molecular substructures, not just the major components.
This became the starting point for our computational study.
By using Machine Learning, we can extract these Structure–Activity Relationships (SAR) and reveal biological patterns that are completely inaccessible to traditional reductionist screening methods.

## Slide 11 of 19: Why ML & Morgan Fingerprints?
Why machine learning was needed:
Essential oils are chemically complex mixtures, often containing dozens to hundreds of compounds. Traditional experimental approaches struggle to isolate and test each individual component. ML enables the integration of heterogeneous literature data and allows patterns to be extracted across 171 samples comprising 682 molecular substructures, identifying recurring structural motifs rather than focusing on single compounds. (2025_49_1_929).

Why Morgan fingerprints were chosen:
Morgan fingerprints encode molescules as binary vectors (ECFP) allowing decomposition into interpretable substructures. A radius of two captures chemically meaningful features like hydroxyl-substituted benzene rings while distinguishing them from inactive bicyclic hydrocarbon structures like α-pinene. They handle EOs as mixtures, capture local structural motifs without assuming a mechanism, and work reliably in small, high-dimensional datasets. Importantly, this allows overlapping substructures within the same molecule to be analysed.

Why a simple, interpretable ML model was used:
L1-regularised logistic regression was selected because it enforces sparsity and performs embedded feature selection, yielding a compact and stable model in a regime with far more features than samples. This choice allowed direct inspection of feature coefficients, permutation importance, and bootstrapped confidence intervals, making it possible to biologically rationalise why certain substructures were predictive. Combined with Morgan fingerprints, it allows direct mapping from model features to chemically meaningful substructures, central to the thesis aim of interpretation rather than pure prediction.

Alternative methods:
• Single-compound testing: impractical due to cost/scale and ignores synergistic effects.
• MACCS keys & physicochemical descriptors: too coarse to resolve terpene and phenolic diversity.
• Molecular docking: requires predefined protein targets (multi-target mechanism of EOs).
• Deep learning/Random Forest/GBM: data-hungry; risk of black-box behavior and overfitting.
• L2 regularisation: retained too many correlated features;
• 3D descriptors: computationally expensive and poorly defined for mixtures.

## Slide 12 of 19: Feature Selection and Model Evaluation
1. The "Funnel" (Left):

We started with messy data. 682 variables, most of which were zeros (sparse).

We filtered them down to 10 using the "Sabotage Test" and Correlation rules we just discussed.



2. The "Report Card" (Middle - Box 3):

Now, look at the orange box. We have to ask: "Is this model actually any good?"

We used 5-fold cross-validation, and here are the results.



EXPLAINING AUC (The 0.88 Score):

You see that score AUC = 0.88?

Think of AUC like a grade for the model:

- 0.50 is a Coin Toss (Pure guessing).

- 1.00 is Perfection.

- 0.80 - 0.90 is considered "Excellent."

So, at 0.88, our model is an "A-student." It is very good at distinguishing between active and inactive oils.



EXPLAINING THE GRAPHS (Figure 3):

If you click that small graph, you'll see the curves.

- The Blue Curve (ROC) shows the trade-off: How many active oils do we catch (Sensitivity) vs. how many false alarms we raise (Specificity). The fact that the curve hugs the top-left corner is what gives us that high 0.88 score.



EXPLAINING THE TABLE (Generalisation):

Finally, look at the Table. Compare "Train" (0.84) vs "Test" (0.81).

The gap is tiny (3. The Outcome (Right):

Because the math is solid, we can trust the results on the right: Phenolics (Bit_1607) are the heroes, and plain terpenes (Bit_549) are just bystanders.

## Slide 13 of 19: Molecular Substructures Linked to Activity
Figure 4.8 shows that limonene is the most recurrent molecule at 21.1%, followed by carvacrol at 14.9%, eugenol at 12.3%, β-caryophyllene at 9.7%, linalyl acetate at 8.8%, thymol at 7.9%, and α-terpineol at 6.1%. The remaining 19.3% is a diverse "Others" category.

The dominance of phenolic aromatics is consistent with extensive evidence. Carvacrol and thymol, which differ only in hydroxyl orientation, show MICs as low as 0.5 µg/mL against S. Typhimurium. Eugenol's free phenolic hydroxyl group enables membrane proton leakage and ROS production.

Synergy between phenolics and terpenic hydrocarbons has been quantified in thyme + clove + cinnamon + garlic nano-emulsions, which reduced the MIC from 0.625 to 0.312 mg/mL.

On the inactive side, Figure 4.9 shows that α-pinene accounts for 15.3%, followed by linalool at 14.8%, limonene at 11.5%, geranial at 10.5%, and δ-3-carene at 7.2%. The logistic regression model ranked bicyclic hydrocarbons and long aliphatic chains as the strongest negative predictors.

Helander et al. showed that carvacrol and thymol permeabilized the outer membrane of S. Typhimurium at 1-3 mM, while (+)-carvone exhibited only minor effects even at 10 mM. Dorman and Deans found that thymol and carvacrol produced inhibition zones of 26-53 mm and suppressed every test strain, whereas non-phenolic alcohols like linalool generated zones one order of magnitude smaller.

This validates our logistic regression analysis where bits encoding an aromatic hydroxyl group receive the strongest positive weights, while bits representing tertiary alcohol or acetate moieties are negatively weighted.

## Slide 14 of 19: Conclusions
This conclusions section summarizes the key outcomes of the doctoral research, which bridged experimental essential oil characterization with machine learning-based structure-activity analysis. The work validated that four commercial EOs meet ISO specifications, demonstrated alginate encapsulation as a viable delivery method, and identified hydroxyl-substituted benzene rings as the strongest predictors of anti-Salmonella activity.

## Slide 15 of 19: Experimental Outcomes
GC-MS Chemotyping: All four oils matched expected chemotypes with >98% identified volatiles. Tea tree showed classic terpinen-4-ol dominance (44.7%), lavender and bergamot shared linalool/linalyl-acetate profiles but differed quantitatively, and peppermint displayed high iso-menthol (49.3%).


Encapsulation: Electrostatic extrusion into calcium-alginate matrices preserved bead integrity post-freeze-drying. Blank beads averaged 2.0mm wet, shrinking ~30% to 1.4mm dry. Oil-loaded beads showed k=0.33-0.40 shrinkage while maintaining sphericity.


Antioxidant: Peppermint was the top performer (23.3 mmol TE/L DPPH), followed by lavender/bergamot, with tea tree lowest (7.6 mmol TE/L). Activity remained stable after 12 months storage.


Antimicrobial: Lavender and bergamot inhibited S. Typhimurium at 5 µg/mL; tea tree and peppermint required 10 µg/mL. The linalool/linalyl-acetate chemotype showed superior Gram-negative penetration.

## Slide 16 of 19: Machine Learning Insights
Model Details: L1-regularised logistic regression (C=1.75) trained on 171 EO profiles encoded as 2048-bit Morgan fingerprints, reduced to 682 significant bits. Achieved 81% cross-validated accuracy and 0.88 ROC AUC.


Key Finding: Only 10 fingerprint bits passed the permutation-importance threshold. The hydroxylated aromatic fragment alone elevated predicted anti-Salmonella activity probability from ~45% to ~95%.


Positive predictors: Phenolic -OH on aromatic rings, acetate esters, furan heterocycles, cycloalkene motifs.

Negative predictors: Branched bicyclic hydrocarbons, tertiary alcohols, long aliphatic chains.


This explains the order-of-magnitude potency gap between phenolic-rich oregano/thyme oils and the linalyl-acetate-dominated lavender/bergamot examined here.

## Slide 17 of 19: Scope & Constraints
Experimental Limitations: • Only 4 commercial EOs • Encapsulation: no release kinetics • Antioxidant: missing FRAP, ORAC • Antimicrobial: single strain.
Computational Limitations: • MIC heterogeneity • Trace compounds ignored • No stereochemistry • No external validation.

## Slide 18 of 19: The Research Horizon


## Slide 19 of 19: Key Takeaways
Final Summary: Lightweight ML pipelines bridge compositional analytics and biological performance. Key finding: phenolic -OH is the strongest predictor of anti-Salmonella activity.
