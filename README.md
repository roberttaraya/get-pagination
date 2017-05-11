[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/roberttaraya/get-pagination)

# \<get-pagination\>

A bootstrap-like pagination component

## Install

Install the component using [Bower](http://bower.io/):

```sh
$ bower install --save roberttaraya/get-pagination
```

## Usage

This component requires 4 properties, and 1 event listener, to work:

```html
<em-pagination
  current-page="[[currentPage]]"
  page-size="[[pageSize]]"
  total-count="[[totalCount]]"
  total-pages="[[totalPages]]"></em-pagination>
```

`current-page`: current page of the list of pages of records<br/>
`page-size`: number of records listed per page<br/>
`total-count`: total number of records<br/>
`total-pages`: the total number of pages of records<br/>

`<em-pagination>` fires an event when a page number is clicked on the pagination component. The event notifies the parent component which page number was clicked. You will also need to implement an event handler in the parent component that listens for the event fired by `<em-pagination>`. The parent component will then use that page number to fetch the corresponding page data. An example is shown below:

```js
listeners: {
   'paginator-select-page': "handlePaginatorSelectPage",
},

handlePaginatorSelectPage: function(e, currentPage) {
  e.preventDefault();
  this.handleFetchPageData(currentPage)
},
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## License

[MIT License](http://opensource.org/licenses/MIT)
