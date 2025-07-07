## Chapter 6 - Time series decomposition

### STL decomposition

- STL: Seasonal and Trend decomposition using Loess
- It can be robust to outliers (i.e., the user can specify a robust decomposition), so that occasional unusual observations will not affect the estimates of the trend-cycle and seasonal components
- The two main parameters to be chosen when using STL are the trend-cycle window (`t.window`) and the seasonal window (`s.window`). These control how rapidly the trend-cycle and seasonal components can change. Smaller values allow for more rapid changes. Both `t.window` and `s.window` should be odd numbers; `t.window` is the **number of consecutive observations to be used when estimating the trend-cycle**; `s.window` is the **number of consecutive years to be used in estimating each value in the seasonal component**. The user must specify `s.window` as there is no default. Setting it to be infinite is equivalent to forcing the seasonal component to be periodic (i.e., identical across years)
