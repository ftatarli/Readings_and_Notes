# The Expected Goals Philosophy

(2020)
by James Tippett

## Football, randomness and why analytics matters

- Football is a sport with a lot of randomness. A team can play well, create many situations and still lose because of randomness.
- Goals are the most important outcome, but they are also rare. 
- A game can have 3,000 events, while the average match only has around 2.7 goals. This makes goals alone a noisy way of measuring performance. 
- The core question is basically:
    - How well can a team create danger against the opponent?
    - How well can it prevent danger against its own goal?
- Every tactical idea is ultimately trying to improve one or both of these things: creating chances and preventing chances.

## What Expected Goals (xG) measures

- xG tries to measure the quantity and quality of chances created by a team.
- Each shot receives a probability representing how likely it was to become a goal.
- The main idea behind xG is that **shot quantity alone is not enough, shot quality matters too**. 
	- A shot taken close to goal and one from long range should not be treated as the same type of chance.
- xG is based on the mathematical concept of **Expected Value (EV)**: estimating the expected value of an event based on its probability of success.

## How xG models calculate probability

- Shot location is one of the main factors determining the probability of scoring, but xG models also consider other variables, such as:
    - Whether the shot came from a cross
    - Header vs shot with the foot
    - Volley vs ball on the ground
    - Strong foot vs weak foot
    - Whether the ball was moving or stationary
    - Type of assist leading to the shot
- Providers such as Opta use very large historical datasets of previous shots to estimate these probabilities.
  - The basic logic is: if historically 10% of similar shots resulted in goals, a new similar shot could receive an xG value of around 0.10.

## xG as a measure of team performance

- xG gives insight into how well a team actually performed, rather than relying only on the final score.
- Looking only at the result can hide what really happened during the match.
- This is why xG can be useful for evaluating whether a team's performance is sustainable over time.

## Visualizing xG

- Collecting xG data is useful, but presenting it in a way that tells the story of the match is equally important.
- xG maps show:
    - The quantity of shots
    - The quality of each shot
    - The location of each shot
- A team may have many shots, but an xG map can reveal that most of them were low-quality attempts.

## Limitations of xG

- Accuracy of shot location
	- There can be limitations in how precisely analysts record the exact location of a shot.
- Defenders and goalkeeper positioning
	- Traditional shot-based models may not fully account for the exact position of defenders and the goalkeeper.
	- Two shots from the same location may have very different difficulty depending on who is blocking the angle or where the goalkeeper is positioned.
- Dangerous attacks without a shot
	- Traditional xG models only evaluate shots, but some very dangerous attacks never result in a shot.

## The difficulty of analysing individual players

- Player analysis in football is much harder than team analysis because football is extremely dynamic.
- The actions of one player constantly affect the actions and performance of others.
	- Attacking actions are easier to assign to an individual player.
	- Defending is much more of a collective responsibility.
	- For example:
	    - A player scores a goal → easy to give credit to that player.
	    - A team concedes a goal → responsibility may be shared between several defenders and the goalkeeper.
- A classic example is tackles: it might seem logical that defenders who make the most tackles are the best defenders, but this ignores context.
	- A defender may make many tackles because their team is constantly under pressure.

## Expected Assists (xA)

- xG gives useful information about strikers, but it doesn't work as well for creative players who rarely take shots.
- xA measures the probability that a player's pass will eventually lead to a goal.
	- It provides a way to measure player creativity.
- Every pass can theoretically receive an xA value, although most passes will have a very low value.
- xA is based on the probability that an **average player** would score from the opportunity created by the pass.
- This is important because actual assists depend heavily on the quality of teammates. Example:
    - A midfielder playing with poor finishers may create many good chances but receive few actual assists.
    - The same midfielder playing with elite finishers could have many more assists.
	- xA helps normalize this by measuring the quality of the chances created rather than whether teammates actually converted them.
