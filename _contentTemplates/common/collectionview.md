#collectionview-keyboard-notes
## Notes

Consider the following when using the keyboard navigation support:

* Navigating through groups is not supported.
* When entering the CollectionView with the keyboard, if there is already a `CurrentItem` set, this item becomes focused and is used as a starting point for navigation onwards. 
* When entering the CollectionView with the keyboard, if there is no `CurrentItem` set, the first rendered item becomes current. If there are no rendered items, then the first item from the data view becomes current. For example, when all groups in the `viewport` are collapsed, no items are rendered. In this case, when expanding the first group, the `CurrentItem` will become visible. 
* When changing the `CurrentItem` to an item that is not in the `viewport`, the CollectionView scrolls to this item. The CollectionView won't scroll to an item if the `CurrentItem` is inside a collapsed group and the item is not visible.
#end

#collectionview-keyboard-common-text
While applying part of the keyboard keys, you can also change the current item behavior of the CollectionView component. For more details, see the article on [setting the .NET MAUI CollectionView Current Item]({%slug collectionview-current-item%})

The following table lists the actions and keyboard combinations that are available in the CollectionView:
#end