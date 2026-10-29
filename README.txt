PeptideScouter Peptide Price Index - published aggregates
=========================================================

One pair of files per monthly issue, published alongside the report at
https://peptidescouter.com/blog/peptide-price-index-<month>-<year>.
Method, normalization and known limits: https://peptidescouter.com/methodology

Files
-----
<YYYY-MM>-summary.csv    Headline figures for the issue (long format).
<YYYY-MM>-compounds.csv  One row per compound in the closing window.

These are aggregates only. No file here carries vendor names, vendor prices
or per-listing rows. Per-milligram figures cover vial and liquid products
sold by mass; capsules, sprays and volume-dosed products are excluded.
Prices are raw listed prices before any coupon or site-wide discount.

Windows
-------
Each issue compares the first seven calendar days of the month (opening
window) with the last seven (closing window). A listing's value in a window
is the median of its in-stock, priced observations in that window. Change
figures use matched pairs only: listings in stock and priced in BOTH windows.
Level figures are snapshots of the closing window.

summary.csv columns
-------------------
metric   Name of the statistic (see list below).
scope    What it was computed over.
value    The figure. Prices are USD per milligram; pct fields are percent.
n        Denominator: listings, compounds or vendors, depending on metric.
as_of    Window (YYYY-MM-DD..YYYY-MM-DD) or window pair the value describes.

Metrics:
  panel_compounds / panel_vendors           distinct compounds / vendors in the matched panel
  unchanged_listings / listings_fell / listings_rose
                                            matched listings by direction of change
  mean_pct_change / median_pct_change       across all matched listings
  median_pct_change_among_movers            across matched listings that changed
  median_price_per_mg_listing_weighted      median across listings, blends excluded
  median_price_per_mg_compound_weighted     median of per-compound medians, blends excluded;
                                            also given per category (scope = category name)
  price_per_mg_p25 / price_per_mg_p75       interquartile bounds across listings
  median_listing_spread                     median cheapest-to-dearest ratio among compounds
                                            on five or more vendors, closing window
  fixed_basket_median_price_per_mg_compound_weighted
                                            previous vs current close on the compounds
                                            present in both (n = compounds in the basket)
  matched_vendor_median_listing_spread      previous vs current close on vendors pricing the
                                            compound in both windows (n = compounds)
  coverage_priced_listings                  priced non-blend listings in each close (n = vendors)

compounds.csv columns
---------------------
peptide_slug                    Stable identifier; page at https://peptidescouter.com/peptides/<slug>
peptide_name                    Display name.
category                        PeptideScouter category.
is_blend                        true when the row is a multi-component blend. A blend's
                                per-milligram figure is over the vial total across components
                                and is not comparable to a single-compound vial.
median_price_per_mg             Median across the compound's indexed listings, closing window.
listings                        Indexed listings priced and in stock in the closing window.
vendors                         Distinct vendors among those listings.
min_price_per_mg / max_price_per_mg
                                Cheapest and dearest listing in the closing window.
spread_ratio                    max / min, only when vendors >= 5; blank otherwise.
matched_vendor_spread_previous / matched_vendor_spread_current
                                Spread at the previous issue's close and this close, restricted
                                to vendors pricing the compound in both. Blank when fewer than
                                five shared vendors or no comparison issue. This is the only
                                spread figure safe to compare across issues.
window                          Closing window the row describes.

Reading across issues
---------------------
Level figures are snapshots; the set of compounds and listings changes month
to month, so do not difference two issues' raw levels or raw spreads. Use
the fixed_basket and matched_vendor lines, or the change figures within an
issue.

Citation
--------
PeptideScouter Peptide Price Index, <Month YYYY> issue, peptidescouter.com,
figures as of the last day of the covered month.

License: CC BY 4.0. Attribution: PeptideScouter (https://peptidescouter.com).
