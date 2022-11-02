# financial_nlp_small

"Financial NLP Small" started with sentences from company initial public
offering documents (IPO SEC Form S-1) that were converted to relational facts
with [`rnlp`](https://github.com/hayesall/rnlp/).

## Task

**Binary Classification**: Is the sentence a primary share?

```prolog
wordstringinsentence(+sentenceid,+wordid,#wordstring).
lemmaofwordinsentence(+sentenceid,+wordid,#wordlemma).
beginningwordinsentence(+sentenceid,-wordid).
midwordinsentence(+sentenceid,-wordid).
endingwordinsentence(+sentenceid,-wordid).
nextwordinsentence(+sentenceid,+wordid,-wordid).
nextwordinsentence(+sentenceid,-wordid,+wordid).
sentencecontainstarget(+sentenceid,+wordid).
```

## Publications

- Dhami, D.S., & Kunapuli, G., & Natarajan, S., Efficient Learning of Relational Gaifman Models using Probabilistic Logic, Workshop on Probabilistic Logic Programming (PLP) 2019.
