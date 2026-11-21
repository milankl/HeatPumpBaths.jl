# Caveats: booklet's spring basis and electric back-up heaters

> Status: **completed**. Two caveats added to the notebook; no model change.

Date of initial draft: 2026-11-21

Base revision: e5c3bc9

## Originating prompt

> We got several comments, can you respond to them here
> - [...] The booklet says its heat delivery times are based on a Vaillant aroTHERM plus in spring,
>   and that winter will be quicker. [...] it might be worth a line in your caveats.
> - We're also looking at Vaillant's electric back-up heater, which adds 2 to 6kW alongside the heat
>   pump [...] I've been approximating it by setting the heat pump to 7kW or 11kW. Do you think
>   that's a reasonable way to use the model?
>
> Yes open a PR

## Revision log

> (none)

## Problem description

Readers asked (1) how the booklet's "spring, aroTHERM plus" basis affects the winter results and
(2) whether an electric back-up heater can be modelled by raising the heat pump size.

## Background

The booklet's run times are indexed by nominal heat pump size. In cold weather a heat pump on hot
water at high flow temperatures usually delivers less than nominal, so the winter results on the page
(10 °C inlet) may be optimistic despite the booklet's statement that winter is quicker.

## Summary of changes

Two bullets in the notebook's Caveats cell (`index.jl`):
- the spring/aroTHERM plus basis and why winter results may be optimistic;
- adding a back-up heater's kW to the heat pump size is an upper-bound approximation (heat still
  passes through the store coil, odd kW sizes are interpolated, electric heat costs ~3× more).

## Testing and verification

Markdown-only change; the Julia/JavaScript model is untouched, the consistency test is unaffected.

## Documentation changes

The notebook caveats themselves.

## Known limitations

The booklet's newer v1.4 has not been checked yet.

## Future work

Compare against booklet v1.4; add a reader's measured bath test to the graph.
