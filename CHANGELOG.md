# Changelog

All notable changes to Macro Icon Search are documented here.

## 2.10.3 - Stable

### Fixed
- Search bar no longer overlaps the **All Icons** dropdown.

## 2.10.2

### Fixed
- Profession filter layout tightened so **Jewelcrafting** stays fully inside the filter panel.

## 2.10.1

### Added
- Mouse-wheel page navigation for filtered results.
- Mouse wheel works over the result grid, individual icons, and the page-navigation bar.
- Wheel down goes to the next page; wheel up goes to the previous page.

## 2.10.0

### Added
- Pre-generated 2-/3-character text-search index.
- Dynamic result-grid sizing based on the actual Forever icon-selector area.
- Page controls moved inside the result window.
- Centered page and result-count display.

### Performance
- Common text searches now narrow to a much smaller candidate list before matching.
- Very short or special searches retain the chunked fallback scanner.

## 2.9.3

### Added
- Precomputed direct quick-filter lists.
- Static intersection path for combined quick filters.

### Performance
- Single quick filters can return results without scanning all 27,714 icons.

## 2.9.x

### Changed
- Replaced filtered Blizzard data-provider updates with a lightweight custom results grid.
- Added performance diagnostics through `/mis perf`.
- Improved cold-search behavior and Forever exact-set handling.

## 2.6.x

### Added
- Clickable filter panel.
- Color filters with broad / strong / dominant modes.
- Class filters.
- Profession filters.
- Right-click reset for individual filters.
- Custom readable search field.
- Layout fixes for the filter panel and result counter.

## Earlier versions

Earlier development versions established the exact Forever icon set, resolved icon filenames, and embedded real pixel-color analysis used by the current addon.
