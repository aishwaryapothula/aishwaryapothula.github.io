# A summary of Winograd Schema Challenge

[https://www.tryinteract.com/share/quiz/602587482dfe0800179da2de](https://www.tryinteract.com/share/quiz/602587482dfe0800179da2de)

---

I am sure many of you have answered correctly within a few seconds. I assume your thinking would have been along the lines of " It has to be the trophy that is too big. If the suitcase was too big, the trophy would fit, rendering the statement meaningless".

The existence of that thinking process is what AI tests are trying to identify in machines. In one school of approaches, the behavior of a machine is analyzed to ascertain the presence or lack of thinking/[intelligence](http://aishwarya.io/universal-intelligence-a-measure-of%20machine-intell) in a machine. Some tests that fall into this class, such as the Turing test and the Winograd Challenge Schema, classify, with high probability, that a machine is intelligent if its behavior imitates human behavior in their tests. 

Last week, we reviewed the Turing test and identified concerns such as practicability. Winograd Schema Challenge is one of the alternatives to Turing test offering certain practical advantages.

**Winograd Schemas**

Each Winograd schema is a pair of sentences that differ by a word or two and contain an element of ambiguity. The ambiguity is resolved in opposite ways when one word is switched. For example,

**Paul tried to call George on the phone, but he wasn't successful. Who isn't successful?
Paul tried to call George on the phone, but he wasn't available. Who isn't available?
Answers:** Paul/George

The answer to the question changes from Paul to George when "successful" is changed to "available".

**Properties of Schemas**

The winograd schema corpus consists of many such schema pairs which adhere to the following properties.

1. Two parties are mentioned in a sentence by noun phrases.They can be two males, two females, two inanimate ob-jects or two groups of people or objects.
2. A pronoun or possessive adjective is used in the sentence in reference to one of the parties, but is alsoof the right sort for the second party. In the case of males, it is “he/him/his”; for females, it is “she/her/her”for inanimate object it is “it/it/its,” and for groups it is“they/them/their.”
3. The question involves determining the referent of the pronoun or possessive adjective. Answer 0 is always the first party mentioned in the sentence (but repeated from the sentence for clarity), and Answer 1 is the second party.
4. There is a word (called the special word) that appears in the sentence and possibly the question. When it is replaced by another word (called the alternate word), every-thing still makes perfect sense, but the answer changes

**More examples of Winograd Schemas**

- The firemen arrived [after/before] the police because they were coming from so far away. Who came from far away?
**Answers:** The firemen/the police.

- Jim [yelled at/comforted] Kevin because he was so upset.Who was upset?
**Answers:** Jim/Kevin.

While the answers to these questions may seem "obvious" to a human, it is not so for a machine. The schemas are designed such that they cannot be resolved by machines through selectional restrictions or statistical techniques trained on large corpuses of data through. Common sense and a general understanding of the world are requisites to solving these schemas.  

**Winograd** **Challenge**

For the Winograd challenge, the contestants are presented with a set of questions, one from each of the schema pairs. Those who achieve human level accuracy in resolving the ambiguities are  claimed, with very high probability, to be engaging in behavior that is generally said to be indicative of thinking in humans. While this sounds like a weak claim, it is to be noted that no test of intelligence, till now, has made a very strong claim that passing that test indicates the presence of human thinking in a machine. 

**My thoughts**

The main advantage of Winograd schema challenge over Turing test is that it is simple and clear cut. The answers being a binary choice mostly eliminates the need for lengthy conversations for behavioral analysis. Moreover, the answers can be easily evaluated by non-experts to determine the presence or lack of understanding the machine. Models most likely will not be able to pass the test with just statistical techniques and selectional restrictions alone.

My main point of contention with the Winograd schema challenge could not have been better articulated than the below excerpt from an [article](https://cs.nyu.edu/faculty/davise/papers/WSProblems.pdf) highlighting the limitations of the challenge.

Excerpt

![A%20summary%20of%20Winograd%20Schema%20Challenge%20f34c851039fe40b7887a684c6f63a515/Untitled.png](A%20summary%20of%20Winograd%20Schema%20Challenge%20f34c851039fe40b7887a684c6f63a515/Untitled.png)