```hbs
{{frost-object-browser-lts
  items=sortedItems
  header=(component 'frost-info-bar'
    icon=(component 'frost-icon'
      icon='list-medium'
      pack='frost'
    )
    title=(component 'text-box'
      isVisible=isTitleVisible
      text='&lt;placeholder: title&gt;'
    )
    summary=(component 'text-box'
      isVisible=isSummaryVisible
      text='&lt;placeholder: summary&gt;'
    )
    scope=(component 'text-box'
      isVisible=isScopeVisible
      text='&lt;placeholder: controls&gt;'
    )
    controls=(component 'frost-button'
      design='info-bar'
      icon='infobar-create'
      text='Click me!'
      onClick=(action 'triggerAction')
    )
  )
  content=(component 'frost-list'
    onSelect=(action 'selectItem')
    item=(component 'lts/user-list-item'
      onCollapse=(action 'collapseItem')
      onExpand=(action 'expandItem')
    )
    expansion=(component 'frost-list-expansion'
      onCollapseAll=(action 'collapseItems')
      onExpandAll=(action 'expandItems')
    )
    sorting=(component 'frost-sort'
      sortOrder=activeSorting
      properties=sortableProperties
      onChange=(action 'sortItems')
    )
  )
  controls=(array
    (component 'frost-button'
      disabled=(eq selectedItemsNumber 0)
      priority="secondary"
      size='medium'
      text='Delete'
      onClick=(action 'triggerDelete')
    )
    (component 'frost-button'
      disabled=(not-eq selectedItemsNumber 1)
      priority="secondary"
      size='medium'
      text='Edit'
      onClick=(action 'triggerEdit')
    )
    (component 'frost-button'
      disabled=(not-eq selectedItemsNumber 1)
      priority="secondary"
      size='medium'
      text='Detail'
      onClick=(action 'triggerDetail')
    )
  )
}}
```