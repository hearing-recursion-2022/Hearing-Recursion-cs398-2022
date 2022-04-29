# The Auditory Recursive Experiment 

## Vision

In this project, we studied the question: Can adding sound to recursive functions improve students’ understanding of recursion? What we did is make it so students can observe what a recursive function is doing by using audio. We made programs that play audio tones within recursive functions so students can tell what is happening while it is running. Recursion can be tough for certain people, so we are making it easier to understand, and to make it more interesting. 

## Team

Hayworth Anderson is the only one working on this experiment, a senior in Computer Science at Calvin University. He is being mentored by Professor Joel Adams of the Computer Science department.  

## Code

Problems:

- linear search
- factorial
- binary search
- hanoi towers

Some example code so you can see generally how it works
```markdown
#include <tsal.hpp>

long long factorial(int n, ThreadSynth& synth) {
    const int DURATION = 1;
    long long answer = 0;

    MidiNote note = Util::scaleToNote(n, std::make_pair(0, 30), std::make_pair(C4, C7));

    if (n > 1) {
      synth.play(note, Timing::SECOND, DURATION);
      answer = n * factorial(n - 1, synth);
      synth.play(note, Timing::SECOND, DURATION);
      
    } else {
      synth.play(note, Timing::SECOND, DURATION);
      synth.stop(Timing::SECOND, DURATION*2);
      answer = 1;
    }

    return answer;
}
```
## Research Question

Can playing appropriate audio tones as a recursive function executes improve a student’s understanding of how recursion works?

## Experiment

For this experiment, CS 108/112 students were recruited for this project. Twenty-one students signed up for it and were randomly assigned into two groups. The first being a control group that would have no audio enhancement. The second group being the experimental group with audio enhancement. 

The participants were brought into the lab at differing times and give a set of slides and instruction for each program. 5-10 minutes were spent on each program, with the students running them however they see fit. 

About a week after this session, the students were sent a quiz. This students' scores on this quiz would be used to serve as our data for this experiment.

## Null Hypothesis

There will be no significant difference in the two groups’ performance on the quiz.

## Results 

For this experiment we used the p-value 0.05 as the value for statistical significance. In the context of this experiment, the p-value measures the likelihood that a difference in the means of the experimental and control group’s quiz scores can be attributed to anything more than random chance.

We took the two groups’ quiz scores for each question and compared them with a two-tailed t-test to test for significance. 

The results were as follows:
![lol](https://user-images.githubusercontent.com/71472546/165418058-864393e9-0c70-4bae-92a5-e0f782f3bd82.png)

Highlighted in yellow are the questions for which we found statistically significant differences.

Based on these results, we were able to reject the Null Hypothesis for our research question. Our experiment indicates that playing appropriate audio tones as a recursive function executes can indeed improve a student’s understanding of how recursion works!

## Report

can find the full report here:
You [CS PROJECT FINAL REPORT.pdf](https://github.com/hearing-recursion-2022/Hearing-Recursion-cs398-2022/files/8587584/CS.PROJECT.FINAL.REPORT.pdf)

## Resources

Calvin Computer Science: https://computing.calvin.edu

Final Presentation: [CS FINAL.pptx](https://github.com/haywortha/Hearing-Recursion/files/8568285/CS.FINAL.pptx)

