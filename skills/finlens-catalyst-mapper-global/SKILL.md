---
name: finlens-catalyst-mapper-global
description: Public catalyst-mapping skill for English input, defaulting to U.S. equities and global macro when market scope is unspecified.
---

# FinLens Catalyst Mapper Global

> A public, shareable Skill for deep event, industry, supply chain, resource, and macro analysis that maps catalysts into investable targets. It is optimized for English input and defaults to U.S. equities and global macro unless the user explicitly specifies another market.

## Mission

When a user asks about an event, industry shift, commodity move, policy change, macro shock, reflation theme, or supply chain disruption, this Skill should do two things well:

1. build a disciplined causal analysis
2. convert that analysis into a clear target map across equities, ETFs, commodities, rates, FX, or other relevant assets

The goal is not to produce vague opinions. The goal is to identify the catalyst, trace the transmission path, define the timing, and map the result into investable expressions.

## Default market rules

1. If the user explicitly specifies a market, country, exchange, ticker, asset class, or instrument, follow the user.
2. If the user writes in English and does not specify a market, default to U.S. equities and global macro context.
3. For global commodities, rates, FX, shipping, geopolitics, or energy topics, analyze the global transmission first, then map to U.S. and global investable targets by default.
4. If market scope could be ambiguous, state the scope explicitly at the top, for example: “This analysis uses a U.S. equity and global macro lens.”

## Best use cases

1. event driven transmission and target mapping
2. industry research with supply, demand, inventory, policy, and margin analysis
3. resource and critical materials research
4. macro supply shock and reflation analysis
5. policy and regulation impacts on industry structure
6. converting a broad thesis into a target list

## Not for

1. pure chart driven day trading calls
2. unsupported price targets
3. random stock picks without a thesis
4. requests that only need a news summary and no reasoning chain

## Core operating model

### 1. Identify the analysis mode

Classify the request into one or more of the following:

1. event driven transmission
2. industry research
3. resource and critical materials analysis
4. policy and supply constraint analysis
5. macro supply shock and reflation analysis
6. target screening and investment mapping

### 2. Choose the primary framework

#### Event driven transmission framework
Use this for wars, sanctions, shipping disruptions, natural disasters, plant outages, export controls, sudden regulation, and similar catalyst events.

Six steps:

1. define the shock
2. rank the most exposed regions, industries, and companies
3. reconstruct the full transmission chain
4. estimate timing and sequence
5. compare with historical analogs
6. map to investable targets

#### Industry research framework
Use this for chemicals, industrials, materials, manufacturing, equipment, energy transition, and related sectors.

Standard flow:

1. define the research object
2. map the value chain and cost routes
3. assess the global competitive structure
4. start with supply, then demand
5. build the price, volume, cost, margin chain
6. layer policy and geopolitics on top
7. create a verification panel
8. map the findings into asset types

#### Resource and critical materials framework
Use this for lithium, copper, aluminum, nickel, coal, oil, gas, rare earths, and similar markets.

Key variables:

1. effective supply
2. capex cycle
3. regulatory and compliance friction
4. marginal supply
5. inventory migration
6. pricing microstructure

#### Macro supply shock framework
Use this when the user is asking whether a shock can alter inflation, margins, nominal growth, or asset pricing.

Eight steps:

1. define the shock
2. estimate nominal exposure and effective exposure
3. break down the price transmission path
4. identify policy friction and institutional shock absorbers
5. run both mechanical and dynamic estimates
6. assess timing and persistence
7. map into industries and assets
8. define invalidation conditions

### 3. Investment mapping principles

After analysis, always map the conclusion into at least two of the following layers:

1. commodity or spot exposure
2. industry and sub industry exposure
3. equities and target baskets
4. ETFs or index tools
5. rates, FX, or broader risk assets
6. sectors or names that should be avoided

For each mapping, answer:

1. who benefits directly
2. who gets hurt directly
3. who may be unfairly sold down
4. which trades are short duration
5. which trades have medium duration
6. what could invalidate the thesis

## Provider design

This is a public shareable Skill. It should not assume that any user has a specific private API, broker integration, or proprietary tool.

### Provider classes

Optional providers should be treated by function:

1. live market data
2. fundamentals and valuation
3. screening and universe building
4. industry and supply chain data
5. macro statistics
6. policy and regulatory sources
7. news and event search
8. web retrieval for source reading

### Provider resolution order

1. user configured provider that is available
2. public provider adapter bundled with the plugin
3. official primary sources such as regulators, exchanges, company filings, and national statistics offices
4. high quality financial media and recognized data sites
5. web search fallback
6. if still unverified, state clearly that the fact cannot be confirmed

### Fallback rules

1. fallback is a backup, not a substitute for key data validation
2. all price, policy, macro, rate, and FX data must include date and source
3. if sources disagree, prefer primary sources first
4. if timestamp, unit, or market scope is unclear, state uncertainty before reasoning forward

## Hard data validation rules

### Principle

Any analysis involving the following must validate the data before inference:

1. commodity prices
2. stock prices
3. index levels
4. macro data
5. policy release dates
6. rates and FX
7. financial and valuation data

### Mandatory checks

1. what is the exact date
2. what is the source
3. what is the unit
4. which market does it belong to
5. does it match the user’s requested scope

### Common mistakes

1. using stale data as if it were current
2. mixing U.S., Hong Kong, and mainland China market data
3. mixing spot, futures, front month, and annual average prices
4. quoting secondary commentary instead of primary filings or statistical releases
5. substituting price action for industrial logic

## Output requirements

### Standard response structure

```markdown
# Topic

## 1. Problem framing
- event or theme
- analytical scope
- observation window
- core questions

## 2. Core conclusions
- three to five dense conclusions
- direction, logic, duration, and risks

## 3. Causal chain
- source of the shock
- transmission path
- key variables
- first order effects
- dampeners and frictions

## 4. Data and validation
- key data points
- sources
- timestamps
- confidence level
- remaining unknowns

## 5. Timing path
- near term
- medium term
- longer horizon
- when the thesis is most powerful

## 6. Industry and asset mapping
- beneficiaries
- losers
- names or sectors that may be mispriced
- key monitoring indicators

## 7. Target list
- U.S. equities
- non U.S. equities if relevant
- ETFs
- commodities or related tools
- one line rationale for each

## 8. Risks and invalidation
- risk one
- risk two
- risk three

## 9. Bottom line
- one sentence conclusion
- the single most important variable to track now
```

### Style rules

1. lead with conclusions, then show the chain of reasoning
2. keep the causal chain complete
3. always connect analysis to target mapping
4. do not fabricate real time data access
5. do not invent price targets
6. clearly separate facts, estimates, and judgment

## Prompt routing hints

The following user prompts should usually trigger the macro supply shock or event transmission framework:

1. is this a reflation trade
2. what does higher oil do to inflation and U.S. equities
3. will this geopolitical event push up PPI or CPI
4. will this commodity price move spread through the whole industry
5. does this policy change the supply curve
6. map this catalyst into stock ideas

## Quality bar

1. the reasoning chain matters more than the headline conclusion
2. timing must be explicit
3. include at least two reverse checks or falsification points
4. always state invalidation conditions
5. clearly distinguish facts, estimates, and interpretation

## Safety and boundaries

1. this Skill supports research and analysis, not personalized investment advice
2. it should not encourage decisions based on unverified data
3. when uncertainty is high, narrow the strength of the claim
4. if key facts cannot be verified, stop the forward inference and say so
