react-dropdown-w-react13
========================

I found myself in need of neat react dropdown component that works with react v13 and can be
styled based on baseClassName. I simply copy&paste render method from later versions
of [react-dropdown](https://github.com/fraserxu/react-dropdown) and it seemed to work.
Use at your own risk.

Simple Dropdown component for React, inspired by [react-select](https://github.com/JedWatson/react-select)


### Why

* The default HTML select element is hard to style
* And sometime we also want grouped menus
* if you want more advanced select, check [react-select](https://github.com/JedWatson/react-select)

### Installation

```
$ npm install react-dropdown  --save
```

### Usage

```JavaScript
'use strict';

import React from 'react';
import Dropdown from '../';

class App extends React.Component {

  constructor() {
    this.state = {
      selected: { value: 'two', label: 'Two'}
    }
  }

  _onSelect(option) {
    console.log('You selected ', option.label)
    this.setState({selected: option})
  }

  render() {

    const options = [
      { value: 'one', label: 'One' },
      { value: 'two', label: 'Two' },
      {
        type: 'group', name: 'group1', items: [
          { value: 'three', label: 'Three' },
          { value: 'four', label: 'Four' }
        ]
      },
      {
        type: 'group', name: 'group2', items: [
          { value: 'five', label: 'Five' },
          { value: 'six', label: 'Six' }
        ]
      }
    ]

    let defaultOption = this.state.selected

    return (
      <Dropdown options={options} onChange={this._onSelect.bind(this)} value={defaultOption} />
    )
  }

}
React.render(<App />, document.body)

```

### License

MIT
