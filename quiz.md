# StencilJS Quiz

The following questions should take you no longer than 2 hours to answer.  

1. What versions of IE does StencilJS support?
 
2. Build a `my-round-image` component which shows an image in a round border. The consumer of the component should be able to supply the path to the image as well as the rendered height and width

3. If a component changes some state in the `componentDidLoad` lifecycle method, how many times will it render before a user interacts with it?

4. Build a `my-button` component that has a `kind` prop with possible values `primary` and `standard`. The style for the primary button should be:
```
  color: #737373;
  background-color: #fff;
  border-color: #d9d9d9;
```
The style for the standard button should be:
```
  color: #fff;
  background-color: #1890ff;
  border-color: #1890ff;
```
Both kinds of button should have the following styles:
```
  border-radius: 4px;
  border: 1px solid transparent;
  line-height: 25px;
```
The content of the button should be supplied by the consumer

5. Is it possible to change a component prop internally within a component after it has been rendered initially?

6. We need to build a `my-counter` component that internally contains a button. When the button is clicked, it increments the counter by an amount defined by the consumer of the component. The counter will always start from `0`. Should the increment amount be defined as a prop or state within the component? What about the current count - should this be a prop or state?

7. Within the component JavaScript, how can you get a DOM reference to the host element?

8. Within the component JavaScript, how can you add an event listener to the host element?

9. Build a `my-listbox` compound component that has the following consuming markup:
```
<my-listbox>
    <my-listbox-item name="item1">...</my-listbox-item>
    <my-listbox-item name="item2">...</my-listbox-item>
    ...
</my-listbox>
```
The component should render an unorder list. The component should allow the consumer to render the content of each list item. When a list item is clicked it should raise a `itemClick` event that contains the item `name` its argument. 

10. Build a component called `my-count-down` that counts down from a configurable number of seconds. The current number of seconds in the countdown should be rendered by the component. 

🏆🏆🏆   

Send your answers to Carl to get your score and feedback. 


