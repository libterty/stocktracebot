# Process Exit

## Process Flow

```text
*********************************************************************
      ***********************           ***********************
      *     Gain Check      *           * Stochasitc Analysis *
      ***********************           ***********************
                                  |
                                  |
                                  V
                        ***********************
                        *   Position Close    *
                        ***********************
*********************************************************************
```

### Gain Check

> Input

- Current gain value.

> Eviction Policy

- First touch point of slow EMA.

> Frame

- Real time, time of delay control in at least 50us is importatant

### Stochasitc Analysis

> Input

- Candles data value.

> Eviction Policy

- If the oscillator crosses itself in the other direction, the system will read that signal and it will close the position.

> Frame

- Using 5 mins (default) time frame candiates.
