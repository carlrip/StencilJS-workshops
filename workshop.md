# Prerequisites

- Comfortable with HTML, CSS, JavaScript, JSX and TypeScript

# Key

👉 Instruction  
❔ Question  
🏃 Exercise  
🏆 Tough challenge  
📄 Information  
💡 Tip  
🔗 Link to useful information

# Getting started

👉 Follow the instructions at the following link to create a project for a collection of web components  
🔗 https://stenciljs.com/docs/getting-started 

🏃 Create a component called `my-alert` that simply renders *"This is an important alert"* in a paragraph tag. Consume the component in the `index.html` file.

🔗 Component decorator in stencil docs https://stenciljs.com/docs/component

# Making components configurable with props

📄 Props allow consumers to configure a component

🔗 Props decorator in stencil docs https://stenciljs.com/docs/properties

🏃 Make the `my-alert` alert text configurable with a `text` prop defaulting it to *"This is an important alert"*  

🏃 Change the consumer of `my-alert` in `index.html` to pass in *"This is a very important alert!"*  

❔ Does a component rerender when one of its props change?

🏃 Add a button beneath `my-alert` in `index.html` that when clicked sets the text of `my-alert` to *"This was a very important alert"*


# Styling components

📄 CSS can be defined for a component in a CSS file that is referenced from a component via the `styleUrl` field in the `Component` decorator.

🔗 Styling in stencil docs https://stenciljs.com/docs/styling

🏃 Add the following CSS style to `my-alert`: 
```
p {
  background-color: #e6f7ff;
  line-height: 1.5;
  padding: 8px 15px;
  border: 1px solid #91d5ff;
  font-size: 14px;
  font-family: sans-serif;
}
```

❔ Are styles encapsulated by default in a component?

🏃 Add a `p` tag containing some text in `index.html`  
❔ What do you notice about the style of the `p` tag?

🏃 Change the component to have its style in its shadow DOM   
❔ What do you notice about styles now on the HTML page? What about in IE? If the `my-alert` style is encapsulated in IE then how has this been achieved when there is no shadow DOM in IE?

❔ Can you think of any drawbacks of using the shadow DOM?

❔ What field on the `Component` decorator can be used as an alternative to the shadow DOM to provide a level of encapsulation without the drawbacks of the shadow DOM? Change the implementation of `my-alert` to use this approach.

🏃 Add a `kind` prop to `my-alert` that can have values `"Info"` (default), `"Success"` or `"Error"`. The colour styles should be the following when `kind` is `"Success"`:
```
  background-color: #f6ffed;
  border: 1px solid #b7eb8f;
}
```
The colour styles should be the following when `kind` is `"Error"`:
```
  background-color: #fff1f0;
  border: 1px solid #ffa39e;
}
```

🏃 Add success and error `my-alert` tags to `index.html`.

# State

📄 State is a local variable with a component that allows the components appearance change. State is changed when something internal within the component happens to change the components appearance

🔗 State in stencil docs https://stenciljs.com/docs/state

🏃 Add an *acknowledge* button to `my-alert` to the right of its text that hides the alert when clicked. The style for the button should be:
```
  margin-left: 10px;
  border: 0;
  background-color: transparent;
  cursor: pointer;
  font-size: 10px;
  font-family: sans-serif;
  opacity: 0.5;
```

❔ Does a component rerender when a state variable changes?

# Exposing and listening to Events

🔗 Events in stencil docs https://stenciljs.com/docs/events

🏃 Add an event called `acknowledge` to `my-alert` that is triggered when the *acknowledge* button is clicked

🏃 Consume the `acknowledge` event on all the `my-alert` tags in `index.html`. In the event listener, output the alert text to the console  

🏃 Add the current date and time to a `when` property in the `acknowledge` event argument

🏃 In the `acknowledge` event listener in `index.html`, output when the alert was acknowledged next to the text in the console  

🏃 Change the component so that a user can acknowledge the alert by clicking anywhere on it 

# Lifecycle methods

📄 Components invoke *lifecycle* methods when at various points within their lifetime. We can implement these methods to execute logic at certain points within a lifetime of a component. 

🔗 Lifecyle methods in stencil docs https://stenciljs.com/docs/component-lifecycle

🏃 Output to the console when the `my-alert` is fully loaded and also when it is updated using the relevant component lifecyle methods 

# Advanced components

📄 A component can have a slot within it that allows the consumer to output custom content 

🔗 Slots in stencil docs https://stenciljs.com/docs/templating-jsx#slots

🏆 Create a component called `my-tab` that has a prop `name` for the tab name and a prop `active` for whether the tab is active. The styling for the tab should be:
```
  padding: 12px 16px;
  cursor: pointer;
```
When the tab is active, it should gain the following additional styles:
```
  color: #1890ff;
  font-weight: 500;
  border-bottom: 2px solid #1890ff;
```
`my-tab` should have a slot to allow the consumer to define the tab heading. An example use of `my-tab` is below:
```
<my-tab name="tab2"><i>Tab Two</i></my-tab>
```
When `my-tab` is clicked, its `active` prop should be set to true and then styled accordingly. Clicking the tab should also raise a `tabActivate` event that includes the tab name in its argument.

📄 The `@Element()` decorator can be used within a class to get the host HTML element. The elements with the host element can then be queried and manipulated using the native DOM API.

🔗 Host element in stencil docs https://stenciljs.com/docs/host-element

🏆 Create a component called `my-tabs` that will be the container for instances of `my-tab` elements. `my-tabs` should activate the first `my-tab` if none of them have been declared as active. `my-tabs` should also ensure only one `my-tab` element is active - so as one is activated, it should deactivate the previous active `my-tab`.

📄 A prop can be watched and a method executed when its value changes. A prop can also be changed internally by the component which will cause the component to rerender

🔗 Watch decorator in stencil docs https://stenciljs.com/docs/reactive-data#watch-decorator  
🔗 Mutable props in stencil docs https://stenciljs.com/docs/properties#prop-mutability

🏆 Add an `activeTab` property to `my-tabs` which should return the active tab name. When set, the prop should activate the relevant tab. In `index.html`, set the second tab in `my-tabs` to be active in its HTML.  Create a button in `index.html` that activates the first tab in `my-tabs`


