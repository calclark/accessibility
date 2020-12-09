--- 
title:
---

### This is an accessible website.

HTML tags are properly annotated according to [ARIA
standards](https://www.w3.org/TR/html-aria/).

Text fonts are sans-serif by default but still render properly when overwritten
by user settings.

All text and widgets automatically resize to fit any screen configuration,
desktop or mobile.

The entirety of the page consists of no more than 25 kilobytes of data, meaning
it loads fast even on slow connections.

And, importantly, the page contains no CAPTCHA.

That last point is not trivial and addresses one of the most difficult points of
modern web design for visually-impaired users. Indeed, most widespread CAPTCHA
implementations have left behind the user experiences of the blind and
visually-impaired, and though some promising solutions are on the horizon, they
will require widespread adoption before the ideals of accessibility on the web
are met at large.


### Audio-Based CAPTCHA

Traditionally, CAPTCHA has sought to meet the needs of the visually impaired by
using an audio-only test. The common test presents itself as the following
series of events:

- The test vocalizes a series of distorted characters accompanied by background
  noise.
- The user writes down the characters that they perceived.
- If the user correctly transcribed the characters, then they have passed the
  CAPTCHA, otherwise they must try again until they succeed.

Already, it is apparent how these tests can create issues for those with
disabilities. In the name of security, these tests introduce background noise
and distortion, but these effects can make it difficult to distinguish unique
characters even for those fluent in English. Take for instance the ..e sound. In
a distorted tone, this sound could be associated with any one of a host of
characters including (but certainly not limited to): b, c, d, e, g, 3. Where
this task is difficult for a native speaker, it may be near-impossible for a
non-native one.

Yet there are even more issues. A more subtle one regards the timing of the
audio track and the user’s screen reader. One of the common functions of a
screen reader is to vocalize what key the user has typed when they press one.
This creates an issue as CAPTCHA audio tracks often do not allow adequate
spacing between letters for screen readers to interject. In practice, this means
that the vocalization of the typed key (by the screen reader) often interferes
with the next letter in the track, compounding the difficulty in understanding
what the next key is. The only alternative method that the user has is to
attempt to memorize the entire string of characters before typing them, a feat
that becomes exponentially more difficult as the number of characters increases
\- remember that these are random characters, not recognizable words or acronyms.

These issues come together to form some troubling statistics. On average, these
standard audio CAPTCHA tests take an entire 28 seconds to complete and have a
success rate of only 50%. Contrast these statistics with the most common visual
CAPTCHA, image matching, wherein tests take only 10 seconds and have a 95%
success rate. Given that the principle goal of accessibility is to create a
common user experience between those with disabilities as those without, it is
apparent that something here is amiss.

So what is the path forward for accessible CAPTCHA?

### Improvements and Alternatives

Some plausible improvements stem directly from the issues declared above.
Non-native speakers have trouble distinguishing the characters in the audio
track? Simply allow for tracks to be read in different languages. While many
websites have CAPTCHAs that are not in english, it is best for every CAPTCHA to
offer multiple languages that can be chosen by the user at runtime, regardless
of what language the website actually offers content in. This way, any user is
able to access the website without having to be entirely fluent in the language.

The spacing of vocalized characters is interfering with screen readers? Add more
space between consecutive characters for screen readers to operate in. This
change alone saw the average success rate increase to 76.2% and average time to
completion decrease by 33%.

Yet there are other solutions that do not only account for these common errors,
but attempt to redesign the audio-based tests as a whole. The current
implementation is considered a content-based test, which means that the user is
tasked merely with transcribing the characters that they hear in the recording.
Other, alternative tests are considered rule-based, which means that instead of
merely having the user transcribe what is heard, they must instead extrapolate
information from it as in a game of sorts.

For instance, one such rule-based test has the user count the number of times
that a specific character appears in the spoken text. This specific type of test
has a success rate of 86.9% and a completion time 39% faster than control.
Another example has the user solve a very simple math problem that is spoken
aloud. This test has an 89.2% success rate and completion time 41% faster than
control. 

These tests benefit from reducing the cognitive load placed on the user
throughout the duration of the test. Instead of the user having to memorize the
entire string of characters or be constantly typing, they instead only have to
keep a running total in their head that they respond with at the end of the
test.

Of course these improvements and alternatives are not without their own
flaws. In order to afford these improvements to user-experience, at least some
tradeoff is made with the security of the CAPTCHAs. Because these alternative
CAPTCHAs are easier for humans to solve, they are also easier for computerized
algorithms to solve. Consequently, they are not appropriate for an all around
replacement of the existing implementation. However, in the most common
situations where CAPTCHA acts merely as spam prevention, the minor tradeoff
between security and user experience can be afforded.

### Closing
So while the current situation for audio-based blind-accessible CAPTCHA
is grim, particularly in comparison to visual CAPTCHA, there does still exist a
path forward for improving the user experience of the visually-impaired.
However, any improvements to the system will require a case-by-case study of the
security implications of such a decision.

### Works Cited

S. Faulkner, S. O'Hara, and P. Lauke, "ARIA in HTML," Nov 25, 2020.

E. Bursztein, S. Bethard, C. Fabry, J. C. Mitchell, and D. Jurafsky, “How Good
Are Humans at Solving CAPTCHAs? A Large Scale Evaluation,” 2010.

V. Fanelle, S. Karamini, A. Shah, B. Subramanian, and S. Das, “Blind and Human:
Exploring More Usable Audio CAPTCHA Designs,” presented at 16th Symposium on
Usable Privacy and Security, Aug 9-11, 2020.
