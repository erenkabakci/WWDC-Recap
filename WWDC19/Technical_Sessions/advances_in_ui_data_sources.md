WWDC19
# Table of Contents
=================

   * [Advances In UI Data Sources - Wednesday](#advances-in-ui-data-sources---wednesday)
      * [Current State-of-the-Art](#current-state-of-the-art)
      * [A New Approach](#a-new-approach)
         * [Diffable Data Source](#diffable-data-source)
      * [Considerations](#considerations)
         * [Constructing Snapshots](#constructing-snapshots)
         * [Configuring Snapshots](#configuring-snapshots)
         * [Identifiers](#identifiers)
         * [What About IndexPath based APIs?](#what-about-indexpath-based-apis)
         * [Performance](#performance)

# Advances In UI Data Sources - Wednesday
Session materials: https://developer.apple.com/videos/play/wwdc2019/220/

## Current State-of-the-Art
- Traditional `UICollectionViewDataSource`
  - Simple & flexible
- Generating UI Updates can be challenging
  - Current approach which relies on informing the UI and updating is error prone
  - There is no centralized truth

## A New Approach
### Diffable Data Source
- `performBatchUpdates()` is gone, `apply()` is the new cool kid in town!
- Applying a snapshot via `UICollectionViewDiffableDataSource` & `UITableViewDiffableDataSource`
- Call it anytime the UI requires a change
```
let snapshot = NSDiffableDataSourceSnapshot<Section, Item>()
snapshot.appendSections([.aSection])
snapshot.appendItems(items, toSection: aSection)
// delete, modify etc. is also available

======================

self.dataSource = UITableViewDiffableDataSource<Section, Item>(tableView: tableView) {
  // the code we usually execute at cellForRowAtIndexPath to reflect changes
}

======================

datasource.apply(snapshot)
```

## Considerations
- Always call `apply()`, never call `performBatchUpdates()` ,`insertItems()`

### Constructing Snapshots
- Empty
  - `let snapshot = NSDiffableDataSourceSnapshot<Section, Item>()`
- Current data source snapshot copy
  - `datasource.snapshot()`

### Configuring Snapshots
- `insertItems(_ identifiers: [ItemIdentifierType], beforeItem beforeIdentifier: ItemIdentifierType)`
- `moveItems`
- `appendItems`
- `appendSections`

### Identifiers
- Must be unique
- Conforms to `Hashable`
- Data model or identifier

### What About IndexPath based APIs?
- e.g: `didSelectItemAt indexpath` should be converted to the datasource snapshot selection

### Performance
- Safe to call `apply()` from a bg thread
  - But, always call from the main queue or a bg queue, don't mix and match

- The newly designed share sheet on iOS13 uses this new implementation
