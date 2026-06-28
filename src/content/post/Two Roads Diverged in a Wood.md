---
title: "Two Roads Diverged in a Wood"
description: "How Bayes' theorem, HIV testing, and medicine taught me to think differently about probability."
publishDate: 2020-07-09
tags:
  - medicine
  - mathematics
  - probability
  - bayes-theorem
  - HIV
---

Diving deeper into Probability, after Bernoulli Trial, another heading that caught my sight was Bayes’ Theorem which incorporates the concept of Conditional Probability that we discussed in previous blog post 0.5. Now you must be wondering why do I have to study Math, when I am already into Medicine which in itself is enormous and no less than a sisyphean task to do.

Am I lacking clarity? Well, two roads diverged in a wood and I don’t know which one has it all. So, as I study Medicine I often find that many concepts and topics find their roots in basic Mathematics which is essential to truly grasp the idea, and that’s how I ultimately end up exploring it from the scratch. Keep reading and you’ll have some impression about this journey from Medicine to Mathematics.

Many of us know about the HIV testing done in ICTCs (Integrated Counselling and Testing Centres) in a government hospitals. Although, the gold standard for confirmation is Western Blot technique, but its high cost is a limitation. Another such technique is ELISA. Instead, we perform three consecutive rapid immunochromatographic tests, each with different sensitivities and specificities, to establish the diagnosis. Sensitivity is the ability of a test to correctly identify those who have the disease in an infected population, i.e. true-positives while the remaining are false-negatives. Conversely, Specificity is the ability of a test to correctly identify those who do not have the disease in a healthy population, i.e. true-negatives while the remaining are false-positives. The hospital I serve in, uses the following kits for confirmation of HIV.

Test 1- CombAids (Sensitivity : 99.8 and Specificity : 99.8)

Test 2- SD Card (Sensitivity : 99.5 and Specificity : 99.0)

Test 3- Signal Tridot (Sensitivity : 99.3 and Specificity : 99.9)

With such high sensitivity of Test 1, which implies that 99.8% of the diseased people screened by the test will give a “true-positive” result and the remaining 0.2% a “false-negative” result, why are we conducting the other two? If someone tests positive for HIV and the Test 1 is 99.8% sensitive, then the chances that they are HIV positive is 99.8%, right? Well, actually wrong! This is where Math comes to play, and clears the confusion by using Bayes’ Theorem.

According to Bayes’ Theorem –

$$
P(H \mid E)=
\frac{P(H)\,P(E \mid H)}
{P(H)\,P(E \mid H)+P(\sim H)\,P(E \mid \sim H)}
$$

Boring! I am sure some of you must have lost all the interest and enthusiasm in reading further and most of you must have not even bothered to read the theorem. I myself belong to the latter group and closed the textbook the day I saw it for the first time. But trust me, it just appears to be complicated. We start with what H and E stand for because P, you already know, stands for Probability. H is the Hypothesis, E is the Evidence. ‘~‘ is ‘not‘ or ‘in absence‘, and P(H|E) here, depicts the Conditional Probability that is Probability of Hypothesis to be true in the presence of Evidence. Let me simplify this for you.

Let the Hypothesis or H be presence of HIV as D (Disease) and ~H be absence of HIV as ~D. Evidence would be the test being positive.

| Test Result | Disease (D) | No Disease (~D) |
|-------------|-------------|-----------------|
| Positive (+) | True Positive (+\|D) | False Positive (+\|~D) |
| Negative (-) | False Negative (-\|D) | True Negative (-\|~D) |

Applying Bayes’ Theorem to know the probability that I have the disease given that I tested positive (Conditional Probability- P(D|+)):

$$
P(D \mid +)=
\frac{P(D)\,P(+ \mid D)}
{P(D)\,P(+ \mid D)+P(\sim D)\,P(+ \mid \sim D)}
$$

i.e.
$$
P(D \mid +)=
\frac{P(D)\,P(\text{True }+)}
{P(D)\,P(\text{True }+)+P(\sim D)\,P(\text{False }+)}
$$

i.e. 
$$
P(D \mid +)=
\frac{P(D)\,P(\text{True }+)}
{P(\text{Total }+)}
$$

P(D) is actually the frequency of the disease in a population also called the Disease Prevalence. It varies for different age groups and also varies among different sections of the society. In nut shell,

$$
P(D \mid +)=
\frac{\text{Disease Prevalence}\times P(\text{True-positive})}
{P(\text{Total positive})}
$$

It was this simple.

I belong to India, where prevalence of HIV, in general, is 0.2% or 0.002. So, P(~D) = 1-P(D) = 0.998. We know that Test 1 is 99.8% sensitive, implying that, P(+|D) = 0.998. We also know the specificity of the test which is also 99.8%, hereby implying that 99.8% are true-negatives and remaining 0.2% don’t have the disease but are tested positive (false +). So, P(+|~D) = 0.002.

| Test | P(D) = 0.002 | P(~D) = 0.998 |
|------|---------------|---------------|
| **+** | P(+\|D) = 0.998<br><sub>Sensitivity = 99.8%</sub> | P(+\|~D) = 0.002 |
| **−** | P(−\|D) = 0.002 | P(−\|~D) = 0.998<br><sub>Specificity = 99.8%</sub> |

$$
P(D \mid +)=
\frac{0.002 \times 0.998}
{(0.002 \times 0.998) + (0.998 \times 0.002)}
$$

$$
P(D \mid +)=0.5
$$

or, 50%.

With such high sensitivity and specificity, chances that I actually have the disease are still 50%. Amazing, right? This percentage is known as the Positive Predictive Value (PPV) of that test and it depends upon sensitivity, specificity and the disease prevalence.

Coming back to 50% chances, we do the test again (Test 2) but this time Bayes’ Theorem helps us to update our previous belief about disease prevalence P(D), which now becomes 0.5. Let us now calculate the probability for Test 2 keeping its sensitivity and specificity in mind.

<table>
  <thead>
    <tr>
      <th>Test</th>
      <th>P(D) = 0.5</th>
      <th>P(~D) = 0.5</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>+</strong></td>
      <td>
        P(+|D) = 0.995<br>
        <em>(Sensitivity = 99.5%)</em>
      </td>
      <td>
        P(+|~D) = 0.01<br>
        <em>(1 − Specificity)</em>
      </td>
    </tr>
    <tr>
      <td><strong>−</strong></td>
      <td>
        P(−|D) = 0.005<br>
        <em>(1 − Sensitivity)</em>
      </td>
      <td>
        P(−|~D) = 0.99<br>
        <em>(Specificity = 99%)</em>
      </td>
    </tr>
  </tbody>
</table>

$$
P(D \mid +)=0.99004975124
$$

0r approximately 99%.

Now you are 99% sure about your status. Updating the prevalence for Test 3 from 0.5 to 0.99 and after considering their sensitivity and specificity, the probability rise to 0.99998982788 or, 99.99898%. So, do you now realise why it is necessary to conduct three tests?

One thing is definite that positive predictive value rises with rise in disease prevalence, which we updated in these series of tests. Here Bayes’ Theorem teaches you what question you need to ask yourself. If the prevalence of a disease is very low, just like HIV, the question we asked ourselves was – ” What are the chances that someone has the disease in presence of a positive result?”, but in case of very high disease prevalence as in the case of CoViD-19, it is more likely that we might have the disease. So the question to be asked here is -“What are the chances that I don’t have the disease given that I tested negative for it?”, which will be:

$$
P(\sim D \mid -)=
\frac{P(\sim D)\,P(\text{True }-)}
{P(\sim D)\,P(\text{True }-)+P(D)\,P(\text{False }-)}
$$

$$
P(\sim D \mid -)=
\frac{P(\sim D)\,P(\text{True-negative})}
{P(\text{Total negative})}
$$

This is called the Negative Predictive Value (NPV) and this value will decrease appreciably even with minute decrease in sensitivity. This is because of increase in number of false-negatives and hence, the denominator. So, it is very important to have high sensitivity along with specificity of the testing kit. Now that you know the importance of serial testing, you are all set to advise your dear ones three consecutive CoViD-19 negative tests.

Having said that, now you see that Medicine teaches you what to do, Math on the other side, teaches you with what intensity you should do it. So, even if it was a needle prick injury, get yourself tested completely and follow the ICTC guidelines. It does not matter if the HIV status of the person whose needle prick you had, was negative. What if he was in a window period (3-6 months) at the time of his testing (false-negative) and he did not follow up for another negative test? Or his testing wasn’t complete like you now know how it should be?

