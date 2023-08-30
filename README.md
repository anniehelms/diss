# Dissertation Analysis
Data and analysis for the production and perception tasks in my dissertation entitled "Trilingual production and perception of lexical stress: Extending the cue-weighting transfer hypothesis to L3 acquisition."

## Abstract

This dissertation analyzes the production and perception of lexical stress in trilinguals’ first, second, and third languages (L1, L2, and L3) to evaluate how the cue-weighting transfer hypothesis applies to L3 acquisition. According to this hypothesis, acoustic cues to stress have different weights across languages, and results from both production and perception studies of bilingual speakers indicate that bilinguals transfer cue-weightings from the L1 to the L2 (Chrabaszcz et al., 2014; Ingvalson et al., 2012; Iverson et al., 2003; Tremblay et al., 2021; Zhang & Francis, 2010). Acoustic correlates of lexical stress were analyzed in English, Spanish, and Catalan, as produced and perceived by L1 English-L2 Spanish-L3 Catalan speakers. Productions of stress minimal pairs in the three languages were collected in three separate experimental sessions via a sentence elicitation task (analyzed in [`production`](https://github.com/anniehelms/diss/tree/main/production)), and perceptions of stress were gathered in three separate experimental sessions via a word identification task using nonword stress minimal pairs (analyzed in [`perception`](https://github.com/anniehelms/diss/tree/main/perception)).

This study focuses on acoustic cue-weightings to word-level prominence in English, Spanish, and Catalan, which all have lexical stress as indicated by the existence of stress minimal pairs and which are reported to belong to different rhythm classes (Prieto et al., 2012). Little, if any, research has been done to investigate how the cue-weighting transfer hypothesis may extend to the L3, which in turn allows for L2 transfer to be better understood (Flynn et al., 2004). Whereas vowel quality is the main correlate to lexical stress in English, duration is the most prominent cue in Spanish, and in Catalan, cue-weighting is vowel-dependent,
with duration and vowel quality being prominent cues. Since the majority of models of multilingual phonetic and phonological acquisition that posit some degree of interaction between acquired language systems have been theorized to extend to L3 aquisition in a similar manner (e.g., Amengual, 2021; Chan & Chang, 2019; de Leeuw & Chang, in press; Escudero et al., 2013; Wrembel et al., 2019), I hypothesize that cue-weightings from previously learned language(s) will transfer into the L3 in the same way that cue-weightings from the L1 transfer into the L2. That is, I hypothesize that cue-weightings in each language will be mediated by relative language dominance. I additionally predict that transfer will be bidirectional, where cue-weightings in the L2 and the L3 can influence cue-weightings in the L1.

The results of the production and perception tasks indicate that relative language dominance does affect cue-weighting to a different extent in each language in the trilinguals’ repertoires. There was additionally evidence for regressive transfer of cue-weighting in both production and perception, indicating that all languages in a trilingual’s repertoire are susceptible to
crosslinguistic influence. Principal component analysis (performed in [`blp`](https://github.com/anniehelms/diss/tree/main/blp)) is shown to be a viable way to extend the Bilingual Language Profile (Birdsong et al., 2012) and obtain relative dominance scores for trilinguals. Lastly, through a comparison of theoretical frameworks of L3 phonetics and phonology, the Attrition & Drift in Access, Production, and Perception Theory (ADAPPT; de Leeuw & Chang, in press) was determined to most closely align with the findings of this study.

## Repo structure

**PCA of Bilingual Language Profile**:

**Production**: Bayesian multilevel modeling of trilingual acoustic data obtained in sentence elicitation task.
- csvs with sentence orders are saved to `sentence_orders` from raw PyschoPy data files (in `psychopy_csvs` and `numbers_files`) using `1_psychopydata_to_txt.ipynb` (`1.1_psychopydata_to_text_keepTrials.ipynb` retains practice trial sentences in output)
- textgrids were aligned with these sentences, hand-corrected, and annotated for vowels of interest, stress, and syllable, then saved to `textgrids`
- acoustic measures were extracted with voicesauce and saved in `voicesauce_txt` 
- `2_acoustic_measures.ipynb` is used to combine acoustic measures from voicesauce with annotated info from textgrids. Vowel formants and normalized with DeltaF normalization and acoustic measures are submitted to PCA. A master df (`data/master_df.csv`) is saved with vowel productions from the target words, principal components of acoustic measures, and participants' PCA loadings from the BLP.
- Bayesian multilevel models predicting whether a vowel is stressed or unstressed are run in `3_cat_bayes.Rmd` (Catalan data), `4_spa_bayes.Rmd` (Spanish data), `5_eng_tri_bayes.Rmd` (Trilingual English data), and `6_eng_all_bayes.Rmd` (Trilingual and monolingual English data). Visualizations of significant predictors are saved in `figures`.


## References

Amengual, M. (2021). The acoustic realization of language-specific phonological categories despite dynamic cross-linguistic influence in bilingual and trilingual speech. The Journal of the Acoustical Society of America, 149 (2), 1271–1284.

Birdsong, D., Gertken, L. M., & Amengual, M. (2012). Bilingual language profile: An easy-to-use instrument to assess bilingualism. COERLL, University of Texas at Austin. https://sites.la.utexas.edu/bilingual

Chan, I. L., & Chang, C. B. (2019). Perception of nonnative tonal contrasts by Mandarin-English and English-Mandarin sequential bilinguals. The Journal of the Acoustical Society of America, 146 (2), 956–972.

Chrabaszcz, A., Winn, M., Lin, C. Y., & Idsardi, W. J. (2014). Acoustic cues to perception of word stress by English, Mandarin, and Russian speakers. Journal of Speech, Language, and Hearing Research, 57 (4), 1468–1479.

de Leeuw, E., & Chang, C. B. (in press). Phonetic and Phonological L1 Attrition and Drift in Bilingual Speech. In M. Amengual (Ed.), The Cambridge Handbook of Bilingual Phonetics and Phonology. Cambridge University Press.

Escudero, P., Broersma, M., & Simon, E. (2013). Learning words in a third language: Effects of vowel inventory and language proficiency. Language and Cognitive Processes, 28 (6), 746–761.

Flynn, S., Foley, C., & Vinnitskaya, I. (2004). The cumulative-enhancement model for language acquisition: Comparing adults’ and children’s patterns of development in first, second and third language acquisition of relative clauses. International Journal of Multilingualism, 1 (1), 3–16.

Ingvalson, E. M., Holt, L. L., & McClelland, J. L. (2012). Can native Japanese listeners learn to differentiate /r–l/ on the basis of F3 onset frequency? Bilingualism: Language and Cognition, 15 (2), 255–274.

Iverson, P., Kuhl, P. K., Akahane-Yamada, R., Diesch, E., Kettermann, A., Siebert, C., et al. (2003). A perceptual interference account of acquisition difficulties for non-native phonemes. Cognition, 87 (1), B47–B57. 

Prieto, P., del Mar Vanrell, M., Astruc, L., Payne, E., & Post, B. (2012). Phonotactic and phrasal properties of speech rhythm. Evidence from Catalan, English, and Spanish. Speech Communication, 54 (6), 681–702.

Tremblay, A., Broersma, M., Zeng, Y., Kim, H., Lee, J., & Shin, S. (2021). Dutch listeners’ perception of English lexical stress: A cue-weighting approach. The Journal of the Acoustical Society of America, 149 (6), 3703–3714.

Wrembel, M., Marecka, M., & Kopeˇckov ́a, R. (2019). Extending perceptual assimilation model to L3 phonological acquisition. International Journal of Multilingualism, 16 (4), 513–533.

Zhang, Y., & Francis, A. (2010). The weighting of vowel quality in native and non-native listeners’ perception of English lexical stress. Journal of Phonetics, 38 (2), 260–271.

