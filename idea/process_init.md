# Process Init

## Process Flow

```text
*********************************************************************
  ***********************          ***********************
  * General Trend Analy *  -TRUE-> * Instant Trend Analy *
  ***********************          ***********************
                                              |
                                              | TRUE
                                              V
  ***********************          ***********************
  *   Stochastic Analy  *  <-TRUE- *      RSI Analy      *
  ***********************          ***********************
            |
            | TRUE
            V
  ***********************
  *   Position Entry    *
  ***********************
*********************************************************************
```

## Exponential Moving Average (EMA)

The Exponential Moving Average –EMA from now onwards– consists of an indicator that
charts a softened –average– curve of the the prices the value has been leading.
We will use the EMA to answer to the following question:
“Is the trend clearly defined? If so, does it go up or down?”
This indicator will be used to see the trend of the value. Let’s see what it is:

- We all know what an average is. Take the n numbers, add them up and divide the
result by n. We will do the same procedure, but with the close data of the candles of
the asset of which we want to calculate the EMA.
  - How many values, you will be wondering. The fact is that an EMA calculation is
always accompanied by a number. This number indicates the window size, which
contains the values of which we will calculate the average. Thus, a window of 1 value
will be a lot more susceptible to changes than a window of 50 values.
  - Now that we have our window, we start rolling it over all the close values of the day,
as if it was a wagon in a roller coaster, moving, calculating averages.
  - The word exponential is there to indicate that the averages are somehow weighted,
meaning that the values closer to the current moment are given more importance
than the others. Which is clever, because we care about what is happening now, to
decide our entry.
- We will be working with three different window sizes: 9 for the fast, 26 for the medium and 50
for the slow. Obviously, the 50-value EMA will reveal a much longer-term trend than the
9-value EMA. Keep in mind that these are all prices. An EMA is an average of the price
osculations inside a defined window.
The code will calculate the three EMAs and answer this question, which is pretty
straight-forward:
  - If the fast EMA is over the medium, and the medium is over the slow, the trend goes
up.
  - If the fast EMA is below the medium, and the medium is below the slow, the trend
goes down.

## Relative Strength Index (RSI)

The Relative Strength Index –RSI from now onwards– consists of an oscillator that charts
the directional price movements. When the price of a stock has an increasing trend, it has a
high RSI. The more accentuated and constant the positive changes, the higher the RSI
value. And vice versa.
We will use the RSI to answer to the following question:
“How hard is people buying –or selling– this value?”

- This indicator will be used to see the buying or selling momentum of the value. Let’s see
what it is:
  - It is an oscillator, which means that it is always oscillating within two values, being
these 0 and 100.
  - The resting point of its oscillation would be 50, where the trend is neither buying
neither selling.
  - It is thought to have a ceil at 70 and a low end at 30. When surpassing these
barriers, it is demonstrated that a rebound is likely to happen. In other words, if the
RSI is 75, it has been overbought, and will probably start to switch its trend to be
more sold than bought, soon. If the RSI is 10 –far below 30–, it has been oversold,
and people may start to buy mode than sell.

The situations we will be looking for are these in which we catch the correct momentum to
our trend. As if we were waiting for a wave with a body board at the shore. Sooner or later,
the operating trend will play in our favour, because it keeps on oscillating.
On the other hand, if the RSI stays too flat, always too close to the middle point, it will mean
that the volatility of that value may be too low to operate.

## The Stochastic

The Stochastic is also an oscillator indicating the momentum of the current price in relation
to its price range over a period of time. It intends to predict price turning points, working with
the close, high and low price, believing the price tends to close near the extremes of the
recent candles.
It charts two curves, the fast and the slow. The last one is a simple moving average of the
fast, that can be configured. The fast curve responds to a simple formula that aims to place
the value higher if it comes closer to the past highest values, and vice versa.
The importance of this indicator relies in seeing the price turning points. The fast curve is
representing the current momentum of the price, and it is leading the slow curve, which has
less inertia. If the fast curve changes its trend, given that the slow curve has slower
reactions, a crossing is produced, being a clear signal of a change of trend.
We will use the stochastic oscillator to answer to the following question:
“How is the asset price currently, compared to its recent historical range?”

- This indicator will be used to check how much room for carrying on with the current trend
does the value have. Let’s see what it is:
  - Again, it is an oscillator, within 0 and 100.
  - As said, it is composed of two curves. The fast one, which will react quicker to the
price, and the slow one, which will be used as a reference.
  - This index provides us with the specific instant where the price has reached its upper
or lower limit –in comparison to the last values, remember–, thus it indicates a
change of trend.
  - This index also provides us with the proximity to this limit, which means that, even
though the curves still haven’t crossed, it is not likely to go much upper –or lower–.
  - This indicator admits three configuration parameters, being them the length of the
number of samples taken, the softening factor and the average factor for the slow
curve.

### General Trend Analysis

> Idea

- In this stage we use EMA.

> Target

- Seek for a defined trend today.

> Frame

- Using 30 mins (default) time frame candiates.

### Instant Trend Analysis

> Idea

- In this stage we use EMA.

> Target

- Seek for a defined trend now.

> Frame

- Using 5 mins (default) time frame candiates.

### RSI Analysis

> Idea

- In this stage we use RSI.

> Target

- Evaluate operation momentum.

> Frame

- Using 5 mins (default) time frame candiates.

### Stochastic Crossing Analysis

> Idea

- In this stage we use Stochastic.

> Target

- Relativize the current price against its recent histor.

> Frame

- Using 5 mins (default) time frame candiates.
