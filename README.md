# Glish

**Goal: Make a version of English where every word is only one syllable**

Inputs:

- words by frequency (optimize monosyllabification for more common words)
  inputs/word_frequency.txt
- words with pronunciations and split by syllables (CMU Dict syllablized)
  Note: multiple valid pronunciations for any given word,
  but all American english

Stages:

- `syllablize.ts` &rarr; convert CMU dict to JSON mapping of word &rarr; IPA split by syllables
- `main.ts` &rarr; load IPA syllables and generate new monosyllabic version of all words
- `sonorityGraph.ts` &rarr; data structure that helps generate new syllables following sonority sequencing.
- `respellIPA.ts` &rarr; convert IPA back into "readable" latin alphabet.

To run code to generate Glish language mapping,
- `ts-node syllablize.ts` to generate outputs/syllablizedIPA.json + syllableGraph + big list of randomly generated syllables
- `ts-node main.ts` to generate outputs/monosyllabic.json & other monosyllabic results

To run UI,
- `cd ui`
- `npm run dev`
