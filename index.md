# The Auditory Recursive Experiment 

## Vision

What we are trying to do is make it so students can observe what a recursive function is doing by using audio. We will be making programs that play audio tones within recursive functions so students can tell what is happening while it is running. Recursion can be tough for certain people, so we are aiming to make it easier to understand, and to make it more interesting. 

## Team

Hayworth Anderson is the only one working on this experiment, a senior in Computer Science at Calvin University. He is being mentored by Professor Joel Adams of the Computer Science department.  

## Code

Types of recursion being used are as follows:

- binary search
- factorial
- linear search
- hanoi towers

Some example code so you can see generally how it works
```markdown
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

## Report

Right now, most of the code is written for the experiment, however some small adjustments need to be made. The experiment is scheduled to comence in the spring semester of 2022. We are hoping to gather a decent group of students to run a control group and a group using these auditory programs. 
