# neoG Camp - Level 1 - CSS

## Positioning

- _Static positioning_ is the default. This means put the element into its normal position in the document flow.
- With _relative positioning_, once the positioned element has taken its place in the normal flow, we can modify its final position using `top`, `left`, `bottom`, `right`.
- An _absolute positioned_ element sits no longer in the normal document flow. Instead, it sits on its own layer separate from everything else. `top`, `bottom`, `left`, `right` behave dofferently with absolute positioning. Rather than positioning the element based on its relative position within the normal document flow, they specify the distance the element should be from each of the containing element's sides.
- Which element is the containing element of an _absolutely positioned_ element is very much the property depends on the position property of the ancestors of the positioned element. If no ancestors have a position property explicetely defined (i.e. they are statically positioned) then the initial containing block will be the block that contains the `html` element.
- We can change the _positioning context_ by setting the position of on of the ancestors to relative.
- When elements start to overlap, we can use `z-index` to specify which element appears over another.
- The positioned elements later in the source order win over positioned elements earlier in the source order.
- _Fixed positioning_ is similar to absolute positioning except that it usually fixes an element in place relative to the visible portion of the viewport.
- _Sticky positioning_ allows a positioned element to act like its relatively positioned until its scrolled to a certain threashold. It can be used, for example, to cause a navigation bar to scroll with the page until a certain point and then stick to the top of the page.

## References

- [Positioning - MDN Docs](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)